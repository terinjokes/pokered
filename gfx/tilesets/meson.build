pngs = [
    'overworld',
    'house',
    'mansion',
    'ship_port',
    'interior',
    'plateau',
    'gym',
    'pokecenter',
    'gate',
    'forest',
    'facility',
    'cemetery',
    'cavern',
    'lobby',
    'ship',
    'lab',
    'club',
    'underground',
]

foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                     input: gen,
                     command: [tools_gfx, '--trim-whitespace', '-o', '@OUTPUT@', '@INPUT@'])
endforeach

pngs = [
    'reds_house',
]

foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                     input: gen,
                     command: [tools_gfx, '--trim-whitespace', '--preserve=0x48', '-o', '@OUTPUT@', '@INPUT@'])
endforeach
