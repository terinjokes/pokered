pngs = [
  'gengar',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f), columns: true)
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '--remove-duplicates', '--preserve=0x19,0x76', '-o', '@OUTPUT@', '@INPUT@'])
endforeach

pngs = [
  'red_nidorino_1',
  'red_nidorino_2',
  'red_nidorino_3',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f), columns: true)
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '-o', '@OUTPUT@', '@INPUT@'])
endforeach
