cs0_sources = ['cs0-triangle.cpp']

cs0_exe = executable('cs0-triangle', cs0_sources, dependencies : [glfw_dep, vulkan_dep]) 

test('cs0', cs0_exe, is_parallel : false, workdir : meson.current_build_dir())

subdir('shaders')
