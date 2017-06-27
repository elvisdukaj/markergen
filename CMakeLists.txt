cmake_minimum_required(VERSION 3.5)

set (CMAKE_CXX_STANDARD 14)
project(markergen LANGUAGES CXX)

find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED)

include_directories(include)
include_directories(${Boost_INCLUDE_DIRS})

file(GLOB HEADERS_FILES "include/*.h*")
file(GLOB SOURCE_FILES "src/*.cpp")
set(SOURCES ${HEADERS_FILES} ${SOURCE_FILES} ${RESOURCES_FILES})

add_executable(${PROJECT_NAME} "${SOURCES}")

target_link_libraries(${PROJECT_NAME}
    ${OpenCV_LIBS}
    )
