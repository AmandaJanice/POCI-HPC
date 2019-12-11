
CC = gcc
CXX = @CXX@
AS = gcc
LD = gcc
CPP = gcc
CPPFLAGS =  -I/usr/local/include -I/usr/local/opt/openssl/include -DCL_SILENCE_DEPRECATION
CFLAGS = -m64 -g -O2 -I/usr/local/include -I/usr/local/opt/openssl/include -DARCH_LITTLE_ENDIAN=1 -Wall -Wno-tautological-constant-out-of-range-compare -fno-omit-frame-pointer -Wno-deprecated-declarations -Wformat-extra-args -Qunused-arguments -std=gnu89 -Wdate-time  -Wno-unused-function
ASFLAGS = -m64  -DARCH_LITTLE_ENDIAN=1 -c  -DUNDERSCORES -DBSD -DALIGN_LOG
LDFLAGS = -m64  -L/usr/local/lib -L/usr/local/opt/openssl/lib -lssl -lcrypto
YASM = 
AR = ar
FIND = /usr/bin/find
RM = /bin/rm -f

IN = ed25519-donna.o

all: ed25519-donna.a
default: ed25519-donna.a

ed25519-donna.o: ed25519-donna.c
	$(CC) -DHAVE_CONFIG_H $(CFLAGS) $(CPPFLAGS) -c ed25519-donna.c -o ed25519-donna.o

.PHONY: subdirs $(SUBDIRS)

subdirs: $(SUBDIRS)

$(SUBDIRS):
	$(MAKE) -C $@ all

ed25519-donna.a: $(SUBDIRS) ed25519-donna.o
	$(AR) -rs $@ $(IN)

clean:
	$(FIND) . -name \*.a -exec $(RM) {} \;
	$(FIND) . -name \*.o -exec $(RM) {} \;

distclean: clean
	$(RM) Makefile
