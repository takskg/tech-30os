
# �f�t�H���g����

default :
	../tolset/z_tools/make.exe img

# �t�@�C�������K��

ipl.bin : ipl.nas Makefile
	../tolset/z_tools/nask.exe ipl.nas ipl.bin ipl.lst

helloos.img : ipl.bin Makefile
	../tolset/z_tools/edimg.exe   imgin:../tolset/z_tools/fdimg0at.tek \
		wbinimg src:ipl.bin len:512 from:0 to:0   imgout:helloos.img

# �R�}���h

asm :
	../tolset/z_tools/make.exe -r ipl.bin

img :
	../tolset/z_tools/make.exe -r helloos.img

run :
	../tolset/z_tools/make.exe img
	cp helloos.img ..\tolset\z_tools\qemu\fdimage0.bin
	../tolset/z_tools/make.exe -C ../tolset/z_tools/qemu

install :
	../tolset/z_tools/make.exe img
	../tolset/z_tools/imgtol.com w a: helloos.img

clean :
	rm -f ipl.bin
	rm -f ipl.lst

src_only :
	../tolset/z_tools/make.exe clean
	rm -f helloos.img