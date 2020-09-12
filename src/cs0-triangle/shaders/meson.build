cs0_glsl_srcs = ['tri-vs.vert', 'tri-fs.frag'] 

cs0_glsl_targets = []
foreach glsl_file : cs0_glsl_srcs
    cs0_glsl_targets += custom_target(
        'Shader - @0@'.format(glsl_file),
        command : [glsllang, '-V', '@INPUT@', '-o',  '@OUTPUT@'],
        input : glsl_file, 
        output : '@BASENAME@.spv',
        build_by_default : true,
        install : true,
        install_dir : '.'
    )
endforeach
