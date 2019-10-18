cmake_minimum_required(VERSION 3.8)
project(hello)


add_subdirectory( src )


set(SOURCE_LIB foo.cpp)
#set(SOURCE foo.cpp foo.h)

#find_package(Qt5Widgets REQUIRED)
#include_directories(${Qt5Widgets_INCLUDES})
add_library(foo SHARED ${SOURCE_LIB})

set(SOURCE_EXE main.cpp)
add_executable(main ${SOURCE_EXE})
target_link_libraries(main foo)
#target_link_libraries(main Qt5::Widgets)

