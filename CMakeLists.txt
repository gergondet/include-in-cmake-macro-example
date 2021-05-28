cmake_minimum_required(VERSION 3.1)

project(Hello)

macro(SayHello NAME)
  set(NAME ${NAME})
  include(hello.cmake)
endmacro()

SayHello("Pierre")
SayHello(${CMAKE_CURRENT_SOURCE_DIR})

message("NAME: ${NAME}")
file(READ hello.cmake HELLO_CONTENT)
set(OUT_CONTENT "${HELLO_CONTENT}")
message("OUT_CONTENT: ${OUT_CONTENT}")
file(WRITE out.cmake "${OUT_CONTENT}")

