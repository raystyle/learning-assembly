MACOSX := 10.11
OUT := out

PROGS := $(addprefix out/,cpuid.o cli.o cli_lea.o loop.o, 64bit.o, jump.o, jne.o, jz.o)

$(OUT)/%.o : %.s
	as -g -W -arch x86_64 -o $@ $<
	ld -e _main -macosx_version_min $(MACOSX) -lc -lSystem -arch x86_64 $@ -o $(OUT)/$*

all: $(PROGS)

$(PROGS): | out

out:
	mkdir $(OUT)

.PHONY: clean

clean: 
	@rm -fr $(OUT)
