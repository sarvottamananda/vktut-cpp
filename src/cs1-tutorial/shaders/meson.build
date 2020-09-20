cs1_shaders = ['tut-vs.vert', 'tut-fs.frag'] 

cs1_glsl_targets = []
foreach glsl_file : cs1_shaders
    cs1_glsl_targets += custom_target(
        'Shader - @0@'.format(glsl_file),
        command : [glsllang, '-V', '@INPUT@', '-o',  '@OUTPUT@'],
        input : glsl_file, 
        output : '@BASENAME@.spv',
        build_by_default : true
    )
endforeach
