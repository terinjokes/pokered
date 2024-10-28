pngs = [
  'pokedex'
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '-o', '@OUTPUT@', '@INPUT@'])
endforeach
