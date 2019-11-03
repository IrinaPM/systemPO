cmake_minimum_required(VERSION 3.8)
project(prg)
set(SOURCE_EXE myApp.cpp)
set(SOURCE_LIB simple.cpp)
find_package(wxWidgets REQUIRED)
include_directories(${wxWidgets_INCLUDE_DIRS})
link_libraries(${wxWidgets_LIBRARY_DIRS})
add_library(simple SHARED ${SOURCE_LIB})
add_executable(MyApp ${SOURCE_EXE})
add_definitions(-D__WXGTK__)
target_link_libraries(myApp simple)
target_link_libraries(myApp ${wxWidgets_LIBRARIES})




