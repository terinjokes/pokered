pngs = [
  'balls',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '-o', '@OUTPUT@', '@INPUT@'])
endforeach

pngs = [
  'move_anim_0',
  'move_anim_1',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.2bpp'.format(f), '@0@.png'.format(f))
  gfx += custom_target(output: '@0@.2bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '--trim-whitespace', '-o', '@OUTPUT@', '@INPUT@'])
endforeach

pngs = [
  'battle_hud_1',
  'battle_hud_2',
  'battle_hud_3',
]
foreach f : pngs
  gen = rgbds.gfx('@0@_conv.1bpp'.format(f), '@0@.png'.format(f), depth: 1)
  gfx += custom_target(output: '@0@.1bpp'.format(f),
                       input: gen,
                       command: [tools_gfx, '--depth', '1', '-o', '@OUTPUT@', '@INPUT@'])
endforeach

pngs = [
  'oldmanb',
  'ghost',
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
