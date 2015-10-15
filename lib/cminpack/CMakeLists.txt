# The name of our project is "CMINPACK". CMakeLists files in this project can
# refer to the root source directory of the project as ${CMINPACK_SOURCE_DIR} and
# to the root binary directory of the project as ${CMINPACK_BINARY_DIR}.
#cmake_minimum_required (VERSION 2.6)
#project (cminpack)

#http://devernay.free.fr/hacks/cminpack.html

file(GLOB sources "*.c")
file(GLOB headers "*.h")
add_library(cminpack ${sources} ${headers})
include_directories("../f2c/")
