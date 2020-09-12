GLSLCOMP = glslangValidator

glsl_files = $(shell find . -name *.vert -or -name *.frag)
spv_files = $(addsuffix .spv,$(basename $(glsl_files)))

.PHONY : all

all : $(spv_files)

%.spv : %.vert
		$(GLSLCOMP) -V -o $@ $<

%.spv : %.frag
		$(GLSLCOMP) -V -o $@ $<

clean :
		rm $(spv_files)
