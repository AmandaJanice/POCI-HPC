
CC = gcc
CXX = @CXX@
AS = gcc
LD = gcc
CPP = gcc
CFLAGS = -m64 -g -O2 -I/usr/local/include -I/usr/local/opt/openssl/include -DARCH_LITTLE_ENDIAN=1 -Wall -Wno-tautological-constant-out-of-range-compare -fno-omit-frame-pointer -Wno-deprecated-declarations -Wformat-extra-args -Qunused-arguments -std=gnu89 -Wdate-time 
ASFLAGS = -m64  -DARCH_LITTLE_ENDIAN=1 -c  -DUNDERSCORES -DBSD -DALIGN_LOG
LDFLAGS = -m64  -L/usr/local/lib -L/usr/local/opt/openssl/lib -lssl -lcrypto
YASM = 
AR = ar
FIND = /usr/bin/find
RM = /bin/rm -f
GCCV44 := $(shell expr `$(CC) -dumpversion` \>= 4.4)
USE_AESNI = darwin

AESIN = aes.o openssl/ossl_aes.o
SUBDIRS = openssl
ifeq "$(GCCV44)" "1"
	ifneq "$(YASM)" ""
		ifdef USE_AESNI
			ifdef AESNI_ARCH
				AESIN += aesni/*.o
				SUBDIRS += aesni
				AESNI_DEC = -DAESNI_IN_USE
			endif
		endif
	endif
endif

aes.o: aes.c ../aes.h aes_func.h
	$(CC) $(CFLAGS) $(AESNI_DEC) -c aes.c -o aes.o

.PHONY: subdirs $(SUBDIRS)

subdirs: $(SUBDIRS)

$(SUBDIRS):
	$(MAKE) -C $@ all

aes.a: $(SUBDIRS) aes.o
	$(AR) -rs $@ $(AESIN)

default: aes.a
all: aes.a

clean:
	$(FIND) . -name \*.a -exec $(RM) {} \;
	$(FIND) . -name \*.o -exec $(RM) {} \;

distclean: clean
	$(RM) Makefile
	$(RM) aesni/Makefile
	$(RM) openssl/Makefile
