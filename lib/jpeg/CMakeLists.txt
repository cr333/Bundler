PROJECT(jpeg)

#SET(LIBJPEG_SYSDEP src/jmemnobs.c)
#
#SET(LIBJPEG_COMMON src/jaricom.c src/jcomapi.c src/jutils.c src/jerror.c src/jmemmgr.c)
#
#SET(LIBJPEG_CLIB
#  src/jcapimin.c src/jcapistd.c src/jcarith.c  src/jctrans.c  src/jcparam.c 
#  src/jdatadst.c src/jcinit.c   src/jcmaster.c src/jcmarker.c src/jcmainct.c 
#  src/jcprepct.c src/jccoefct.c src/jccolor.c  src/jcsample.c src/jchuff.c 
#  src/jcdctmgr.c src/jfdctfst.c src/jfdctflt.c src/jfdctint.c
#)
#
#SET(LIBJPEG_DLIB
#  src/jdapimin.c src/jdapistd.c src/jdarith.c  src/jdtrans.c  src/jdatasrc.c 
#  src/jdmaster.c src/jdinput.c  src/jdmarker.c src/jdhuff.c   src/jdmainct.c 
#  src/jdcoefct.c src/jdpostct.c src/jddctmgr.c src/jidctfst.c src/jidctflt.c 
#  src/jidctint.c src/jdsample.c src/jdcolor.c  src/jquant1.c  src/jquant2.c 
#  src/jdmerge.c
#)

IF(WIN32)
  ADD_DEFINITIONS( -DJPEG_STATIC -D_CRT_SECURE_NO_WARNINGS)
  # TODO(keir): CMake ignores this, but it should disable the following:
  # C:\...\basetsd.h(78): warning C4142: benign redefinition of type
  SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4142")
ENDIF(WIN32)

FILE(GLOB sources "src/*.c")
FILE(GLOB headers "src/*.h")

ADD_LIBRARY(jpeg STATIC ${headers} ${sources})

