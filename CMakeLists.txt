cmake_minimum_required(VERSION 3.22)
project(warden)

set(CMAKE_CXX_STANDARD 20)

add_executable(warden main.cpp Packet.cpp Packet.h)
