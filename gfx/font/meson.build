pngs = [
  'AB',
  'font_battle_extra',
  'font_extra',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '-o', '@OUTPUT@', '@INPUT@'])
endforeach

pngs = [
  'ED',
  'P',
  'font'
]

foreach f : pngs
  gen = rgbds.gfx('@0@_conv.1bpp'.format(f), '@0@.png'.format(f), depth: 1)
  gfx += custom_target(output: '@0@.1bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '--depth', '1', '-o', '@OUTPUT@', '@INPUT@'])
endforeach
