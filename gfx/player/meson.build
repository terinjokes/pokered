pngs = [
  'red',
  'redb',
  'shrink1',
  'shrink2',
]

foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gen = custom_target(output: '@0@.2bpp'.format(f),
                     input: gen,
                     command: [tools_gfx, '-o', '@OUTPUT@', '@INPUT@'])
  gfx += custom_target(output: '@0@.pic'.format(f),
                      input: gen,
                      command: [tools_pkmncompress, '@INPUT@', '@OUTPUT@'])
endforeach
