R=../rz_gg

all:
	${MAKE} hello
	#${MAKE} foo

foo:
	rz_bin -c mach0:`rz_asm -a x86.nz -f hello.s` a.out

bla:
	${MAKE} hello

hello:
	rm -f a.out
	$R -s hello.r -o hello.s
	cat hello.s
	$R -x hello.r
	$R -F -o a.out hello.r
	#-./a.out ; RET=$$? ; if [ $$RET = 0 ]; then echo It Works ; else echo Oops.. Fail ; fi

hi:
	rm -f a.out
	$R -s hi.r
	$R -F -o a.out hi.r
	-./a.out ; RET=$$? ; if [ $$RET = 0 ]; then echo It Works ; else echo Oops.. Fail ; fi

customsyscall:
	rm -f a.out
	$R -s customsyscall.r
	$R -F -o a.out customsyscall.r
	-./a.out ; RET=$$? ; if [ $$RET = 2 ]; then echo It Works ; else echo Oops.. Fail ; fi

exithello:
	rm -f a.out
	$R -s exithello.r
	$R -F -o a.out exithello.r
	-./a.out ; RET=$$? ; if [ $$RET = 2 ]; then echo It Works ; else echo Oops.. Fail ; fi
