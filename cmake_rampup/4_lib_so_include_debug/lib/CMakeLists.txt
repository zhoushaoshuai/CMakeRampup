SET(LIBHELLO_SRC hello.c)

#ADD_LIBRARY(hello STATIC ${LIBHELLO_SRC}) # created libhello.a
#MESSAGE("created libhello.a")

ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC}) # create libhello.so
MESSAGE("created libhello.so")

#ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC}) #create libhello_static.a
#MESSAGE("created libhello_static.a")

#SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")


#GET_TARGET_PROPERTY(OUTPUT_VALUE hello_static OUTPUT_NAME)
#MESSAGE(STATUS “This is the hello_static OUTPUT_NAME:”${OUTPUT_VALUE})

#SET_TARGET_PROPERTIES(hello PROPERTIES VERSION 1.2 SOVERSION 1)

#install lib and *.h to path
#INSTALL(TARGETS hello hello_static 
#		LIBRARY DESTINATION lib 
#		ARCHIVE DESTINATION lib) #静态库要使用ARCHIVE关键字
INSTALL(TARGETS hello
		LIBRARY DESTINATION lib)
INSTALL(FILES hello.h DESTINATION include/hello)

#compile command list
#cmake -DCMAKE_INSTALL_PREFIX=/usr ..
#make
#make install

#hzrkwr@ubuntu:~/gwm/linuxrampup/cmake_rampup/2_lib_a_so_create/lib/build$ sudo make install
#[ 50%] Built target hello
#[100%] Built target hello_static
#Install the project...
#-- Install configuration: ""
#-- Installing: /usr/lib/libhello.so.1.2
#-- Installing: /usr/lib/libhello.so.1
#-- Installing: /usr/lib/libhello.so
#-- Installing: /usr/lib/libhello.a
#-- Installing: /usr/include/hello/hello.h
