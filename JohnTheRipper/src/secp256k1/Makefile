
CC = gcc
CXX = @CXX@
AS = gcc
LD = gcc
CPP = gcc
CFLAGS = -m64 -g -O2 -I/usr/local/include -I/usr/local/opt/openssl/include -DARCH_LITTLE_ENDIAN=1 -Wall -Wno-tautological-constant-out-of-range-compare -fno-omit-frame-pointer -Wno-deprecated-declarations -Wformat-extra-args -Qunused-arguments -std=gnu89 -Wdate-time  -Wno-unused-function
ASFLAGS = -m64  -DARCH_LITTLE_ENDIAN=1 -c  -DUNDERSCORES -DBSD -DALIGN_LOG
LDFLAGS = -m64  -L/usr/local/lib -L/usr/local/opt/openssl/lib -lssl -lcrypto
YASM = 
AR = ar
FIND = /usr/bin/find
RM = /bin/rm -f

IN = secp256k1.o

all: secp256k1.a
default: secp256k1.a

secp256k1.o: secp256k1.c
	$(CC) -DHAVE_CONFIG_H $(CFLAGS) -c secp256k1.c -o secp256k1.o

.PHONY: subdirs $(SUBDIRS)

subdirs: $(SUBDIRS)

$(SUBDIRS):
	$(MAKE) -C $@ all

secp256k1.a: $(SUBDIRS) secp256k1.o
	$(AR) -rs $@ $(IN)

clean:
	$(FIND) . -name \*.a -exec $(RM) {} \;
	$(FIND) . -name \*.o -exec $(RM) {} \;

distclean: clean
	$(RM) Makefile
