############################################################################
#                                                                          #
#  file: CMakeLists.txt                                                    #
#  Copyright (C) 2016                                                      #
#      Enrico Bertolazzi                                                   #
#      Dipartimento di Ingegneria Industriale                              #
#      Universita` degli Studi di Trento                                   #
#      email: enrico.bertolazzi@ing.unitn.it                               #
#                                                                          #
############################################################################

set( TARGET embedFiglet )

project(embedFiglet C CXX)

file(GLOB SOURCES ./src/*.cc)
file(GLOB HEADERS ./src/*.hh)

include_directories(src)

add_library(embedFiglet STATIC ${HEADERS} ${SOURCES})

add_executable(example examples/example.cc ${HEADERS})
target_link_libraries(example embedFiglet)