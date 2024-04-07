cmake_minimum_required(VERSION 3.12)
project(bwa)

set(CMAKE_CXX_STANDARD 11)
add_compile_options(-g -Wall -Wno-unused-function -Wno-unused-variable -Wno-sign-compare)

### add extra (third-party) include directories
# include_directories(include)
### add extra (third-party) lib directories
# link_directories(lib)

### add all source file to the SRC_LIST *variable*
set(SRC_LIST bwa.c bamlite.c bwamem.c fastmap.c bwashm.c bwamem_pair.c bwamem_extra.c
        bwt.c bwtindex.c bwt_lite.c bwtaln.c bwt_gen.c bwtgap.c bwtsw2_aux.c
        bwtsw2_main.c bwtsw2_chain.c bwtsw2_pair.c bwtsw2_core.c
        kopen.c kstring.c ksw.c bntseq.c bwaseqio.c is.c maxk.c rle.c rope.c
        bwase.c bwape.c pemerge.c kthread.c malloc_wrap.c QSufSort.c utils.c)

add_executable(bwa main.c ${SRC_LIST})
target_link_libraries(bwa m z pthread)
