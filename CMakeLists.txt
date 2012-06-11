cmake_minimum_required(VERSION 2.6)
project(z)

# Ensure we are building against Emscripten.
if(NOT DEFINED EMSCRIPTEN_ACTIVE)
	message("Please run cmake with the -C $EMSCRIPTEN_ROOT/Emscripten.cmake option." FATAL_ERROR)
endif(NOT DEFINED EMSCRIPTEN_ACTIVE)

# Define project.
add_library(z
	src/adler32.c
	src/crc32.c
	src/gzlib.c
	src/gzwrite.c
	src/inffast.c
	src/inftrees.c
	src/trees.c
	src/zutil.c
	src/compress.c
	src/deflate.c
	src/gzclose.c
	src/gzread.c
	src/infback.c
	src/inflate.c
	src/uncompr.c
)
set_target_properties(z PROPERTIES SUFFIX ".js")
