target ?= cs0-triangle

build_dir ?= ./build
src_dirs ?= .
inc_dirs := $(shell find $(src_dirs) -type d -name include)

subdirs := shaders 

mkdir_p ?= mkdir -p

srcs := $(shell find $(src_dirs) -name *.cpp -or -name *.c -or -name *.s)
objs := $(srcs:%=$(build_dir)/%.o)
deps := $(objs:.o=.d)

inc_flags := $(addprefix -I,$(inc_dirs))

CPPFLAGS =  $(inc_flags)
CFLAGS = -std=c18 -O2
CXXFLAGS = -std=c++17 -O2

LDFLAGS = -lglfw -lvulkan -lm -lstb -ltinyobjloader -lstdc++

.PHONY: all $(subdirs) test clean

all : $(target)
		for dir in $(subdirs); do \
				$(MAKE) -C $$dir all; \
		done

$(subdirs):
		$(MAKE) -C $@


test : $(target)
		./$(target)

clean : 
		$(RM) -r $(build_dir) $(target)
		for dir in $(subdirs); do \
				$(MAKE) -C $$dir clean; \
		done

$(target) : $(objs)
		$(CXX) $(objs) -o $@ $(LDFLAGS)

# assembly
$(build_dir)/%.s.o: %.s
		$(mkdir_p) $(dir $@)
		$(AS) $(ASFLAGS) -c $< -o $@

# c source
$(build_dir)/%.c.o: %.c
		$(mkdir_p) $(dir $@)
		$(CC) $(CPPFLAGS) $(CFLAGS) -c $< -o $@

# c++ source
$(build_dir)/%.cpp.o: %.cpp
		$(mkdir_p) $(dir $@)
		$(CXX) $(CPPFLAGS) $(CXXFLAGS) -c $< -o $@

-include $(deps)




