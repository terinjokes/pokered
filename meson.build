project('pokered', 'c', 'rgbds')

if meson.get_compiler('rgbds').version().version_compare('<0.7.0')
  error('minimum supported rgbds version is 0.7.0')
endif

rgbds = import('rgbds')
tools_gfx = executable('tools_gfx', 'tools/gfx.c', native: true, c_args: ['-std=c11'])
tools_pkmncompress = executable('tools_pkmncompress', 'tools/pkmncompress.c', native: true, c_args: ['-std=c11'])

gfx = []

subdir('gfx/battle/')
subdir('gfx/credits/')
subdir('gfx/emotes/')
subdir('gfx/font/')
subdir('gfx/icons/')
subdir('gfx/intro/')
subdir('gfx/overworld/')
subdir('gfx/player/')
subdir('gfx/pokedex/')
subdir('gfx/pokemon/back')
subdir('gfx/pokemon/front')
subdir('gfx/sgb')
subdir('gfx/slots')
subdir('gfx/splash/')
subdir('gfx/sprites')
subdir('gfx/tilesets')
subdir('gfx/tilesets/flower/')
subdir('gfx/title/')
subdir('gfx/town_map/')
subdir('gfx/trade/')
subdir('gfx/trainer_card/')
subdir('gfx/trainers')

layout = files('layout.link')

pokered = executable('pokered', [
  'audio.asm',
  'home.asm',
  'main.asm',
  'maps.asm',
  'ram.asm',
  'text.asm',
  'gfx/pics.asm',
  'gfx/sprites.asm',
  'gfx/tilesets.asm',
  gfx
],
           rgbds_args : ['-P', 'includes.asm', '-D_RED', '-Q8'],
           link_language: 'rgbds',
           link_args: ['-d', '-l', layout[0].full_path()])

rgbds = import('rgbds')
rom = rgbds.fix('pokered.gbc', pokered,
                title: 'POKEMON RED',
                new_licensee: '01',
                mbc_type: 'MBC3+RAM+BATTERY',
                ram_size: '03',
                fix_spec: 'lhg',
                pad: '0x00',
                extra_args: ['--sgb-compatible'])
