cmake_minimum_required(VERSION 3.16)

project(thread_test LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Core)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Core)

add_executable(thread_test
  main.cpp
  thread_object.h thread_object.cpp
  thread_call.h thread_call.cpp
)
target_link_libraries(thread_test Qt${QT_VERSION_MAJOR}::Core)

include(GNUInstallDirs)
install(TARGETS thread_test
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
