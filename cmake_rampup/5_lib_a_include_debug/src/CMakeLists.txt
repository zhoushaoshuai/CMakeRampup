ADD_EXECUTABLE(main main.c)
INCLUDE_DIRECTORIES(/usr/include/hello) #fix main.c:3:19: error: hello.h: No such file or directory
#TARGET_LINK_LIBRARIES(main hello) # fix main.c:(.text+0x16): undefined reference to `HelloFunc'
								  # link to dynamic lib
#link to hello.so
#ldd src/main
#        linux-gate.so.1 =>  (0xb7ee7000)
#        libhello.so.1 => /usr/lib/libhello.so.1 (0xb7ece000)
#        libc.so.6 => /lib/libc.so.6 (0xb7d77000)
#        /lib/ld-linux.so.2 (0xb7ee8000)

TARGET_LINK_LIBRARIES(main libhello.a)	#link to static lib
#hzrkwr@ubuntu:~/gwm/linuxrampup/cmake_rampup/3_lib_a_so_include/build$ ldd src/main 
#	linux-gate.so.1 =>  (0x00e23000)
#	libc.so.6 => /lib/tls/i686/cmov/libc.so.6 (0x0027e000)
#	/lib/ld-linux.so.2 (0x0093e000)
