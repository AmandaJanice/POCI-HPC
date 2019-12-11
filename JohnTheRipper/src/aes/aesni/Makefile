
CC = gcc
ASM_DIR = asm/x$(AESNI_ARCH)
IAES = $(ASM_DIR)/iaesx$(AESNI_ARCH).s
RDTSC = $(ASM_DIR)/do_rdtsc.s
YASM = 

iaesx.o: $(IAES)
	$(YASM) -D__darwin__ --prefix=_ -f macho64 $(IAES) -o $@

rdtsc.o: $(RDTSC)
	$(YASM) -D__darwin__ --prefix=_ -f macho64 $(RDTSC) -o $@

aesni.o: iaes_asm_interface.h  iaesni.h  intel_aes.c
	$(CC) $(CFLAGS) -Wall -Wno-tautological-constant-out-of-range-compare -fno-omit-frame-pointer -Wno-deprecated-declarations -Wformat-extra-args -Qunused-arguments -std=gnu89 -Wdate-time -m64 -c intel_aes.c -o $@

all: iaesx.o rdtsc.o aesni.o

default: all

clean:

distclean: clean
	$(RM) Makefile
