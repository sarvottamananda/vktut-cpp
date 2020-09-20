cs1_textures = ['viking_room.png'] 

cs1_tx_targets = []
foreach tx_file : cs1_textures
    cs1_tx_targets += custom_target(
        'Texture - @0@'.format(tx_file),
        input : tx_file, 
        output : tx_file,
        command : ['cp', '@INPUT@', '@OUTPUT@']
    )
endforeach
