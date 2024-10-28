pngs = [
  'red_slots_1',
  'red_slots_2',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '--trim-whitespace', '-o', '@OUTPUT@', '@INPUT@'])
endforeach
