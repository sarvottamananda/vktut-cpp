cs1_sources = ['cs1-tutorial.cpp']

cs1_exe = executable('cs1-tutorial', cs1_sources, dependencies : [glfw_dep, vulkan_dep]) 

test('cs1', cs1_exe, is_parallel : false, workdir : meson.current_build_dir())

subdir('shaders')
subdir('models')
subdir('textures')

