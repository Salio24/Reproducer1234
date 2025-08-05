cmake_minimum_required(VERSION 3.31)
project(repr)

set(CMAKE_CXX_STANDARD 20)

set(BUILD_SHARED_LIBS OFF CACHE INTERNAL "")

set(SDL_SHARED OFF)
add_subdirectory(${PROJECT_SOURCE_DIR}/thirdparty/SDL3 EXCLUDE_FROM_ALL)

# SDL_mixer
#set(SDLMIXER_GME OFF)
#set(SDLMIXER_MOD_XMP OFF)
#set(SDLMIXER_OPUS OFF)
set(SDLMIXER_DEPS_SHARED OFF)
#find_package(Threads REQUIRED)
set(SDLMIXER_VENDORED ON)
add_subdirectory(${PROJECT_SOURCE_DIR}/thirdparty/SDL3_mixer EXCLUDE_FROM_ALL)

add_executable(repr main.cpp)
