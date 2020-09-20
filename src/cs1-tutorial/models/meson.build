cs1_models = ['viking_room.obj'] 

cs1_model_targets = []
foreach model_file : cs1_models
    cs1_model_targets += custom_target(
        'Model - @0@'.format(model_file),
        input : model_file, 
        output : model_file,
        command : ['cp', '@INPUT@', '@OUTPUT@']
    )
endforeach
