cmake_minimum_required(VERSION 3.23)
project(clean_startup)

if (UNIX)
    # Add file textension *.bin to all executables on Unix (Linux, OSX, BSD ...)
    set(CMAKE_EXECUTABLE_SUFFIX ".bin")
endif ()

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(PROJECT_DIR ${CMAKE_SOURCE_DIR})
set(PROJECT_MAIN_DIR ${PROJECT_DIR}/src)

set(PROJECT_SOURCE_DIR ${PROJECT_MAIN_DIR}/sources)
set(PROJECT_HEADER_DIR ${PROJECT_MAIN_DIR}/headers)
set(PROJECT_LIBS_DIR ${PROJECT_MAIN_DIR}/libs)
set(PROJECT_RESOURCE_DIR ${PROJECT_DIR}/resources)


set(
        PROJECT_HEADERS

)

set(
        PROJECT_SOURCE
        ${PROJECT_SOURCE_DIR}/main.cpp
)

find_package(Qt6 COMPONENTS
        Core
        Gui
        Widgets
        REQUIRED)

add_executable(${PROJECT_NAME} ${PROJECT_SOURCE})
target_link_libraries(clean_startup
        Qt::Core
        Qt::Gui
        Qt::Widgets
        )

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_HEADER_DIR})
