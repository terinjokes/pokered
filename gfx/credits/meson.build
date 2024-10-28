pngs = [
  'the_end',
]
foreach f : pngs
  orig = files('@0@.png'.format(f))
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), orig)
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '--interleave', '--png', orig, '-o', '@OUTPUT@', '@INPUT@'])
endforeach
