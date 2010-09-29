CC = ../src/calcc
LDFLAGS = -L../lib -lcalc
AS = nasm
LD = ld -melf_i386

PROGRAMS = hello fib fact

all:	$(PROGRAMS)
	@echo "Build done. Try out test programs: $(PROGRAMS)"

hello:	hello.o
	$(LD) $< -o $@ $(LDFLAGS)

fib:	fib.o
	$(LD) $< -o $@ $(LDFLAGS)

fact:	fact.o
	$(LD) $< -o $@ $(LDFLAGS)

%.o:	%.asm
	nasm -f elf $< -o $@

%.asm:	%.calc
	$(CC) $< $@

clean:
	rm -f $(PROGRAMS) *.o *.asm

