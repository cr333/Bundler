PROJECT(jpeg)

IF(WIN32)
  ADD_DEFINITIONS( -DJPEG_STATIC -D_CRT_SECURE_NO_WARNINGS)
  # TODO(keir): CMake ignores this, but it should disable the following:
  # C:\...\basetsd.h(78): warning C4142: benign redefinition of type
  SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4142")
ENDIF(WIN32)

FILE(GLOB sources "src/*.c")
FILE(GLOB headers "src/*.h")

ADD_LIBRARY(jpeg STATIC ${headers} ${sources})

