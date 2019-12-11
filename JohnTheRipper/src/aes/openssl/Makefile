
CC = gcc
CXX = @CXX@
AS = gcc
LD = gcc
CPP = gcc
CFLAGS = -m64 -g -O2 -I/usr/local/include -I/usr/local/opt/openssl/include -DARCH_LITTLE_ENDIAN=1 -Wall -Wno-tautological-constant-out-of-range-compare -fno-omit-frame-pointer -Wno-deprecated-declarations -Wformat-extra-args -Qunused-arguments -std=gnu89 -Wdate-time 
ASFLAGS = -m64  -DARCH_LITTLE_ENDIAN=1 -c  -DUNDERSCORES -DBSD -DALIGN_LOG
LDFLAGS = -m64  -L/usr/local/lib -L/usr/local/opt/openssl/lib -lssl -lcrypto

ossl_aes.o: ossl_aes.c ossl_aes.h
	$(CC) $(CFLAGS) -c ossl_aes.c -o $@

default: ossl_aes.o
all: ossl_aes.o

clean:

distclean: clean
	$(RM) Makefile
