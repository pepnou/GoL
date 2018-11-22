cmake_minimum_required (VERSION 3.9.0)
project (GameOfLife 	VERSION 1.0
						DESCRIPTION "the game of life"
						LANGUAGES C)





set (SRC main.c)
set (SDL_INCLUDE /usr/include/SDL/)
set (COMPILATION_OPTION "-O3" "-Wall" "-g")



add_executable(GoL ${SRC})



INCLUDE(FindPkgConfig)
PKG_SEARCH_MODULE(SDL REQUIRED sdl)

target_include_directories(GoL PUBLIC ${SDL_INCLUDE_DIRS} )
target_link_libraries (GoL ${SDL_LIBRARIES})

target_compile_options(GoL PUBLIC ${COMPILATION_OPTION})
