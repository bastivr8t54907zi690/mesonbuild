project('jnijava', ['c', 'java'])

if build_machine.system() == 'cygwin'
  error('MESON_SKIP_TEST: cygwin test failures')
endif

if build_machine.system() == 'windows' and build_machine.cpu_family() == 'x86'
  error('MESON_SKIP_TEST: failing builds on 32bit Windows because a 32bit JDK is not available in the Azure Pipelines Windows images')
endif

fs = import('fs')
javamod = import('java')

java = find_program('java')

jni_dep = dependency('jni', version : '>=1.8', modules: ['jvm', 'awt'])

# generate native headers
subdir('src/com/mesonbuild')
subdir('lib')
subdir('src')