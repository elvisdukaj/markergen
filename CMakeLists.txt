cmake_minimum_required(VERSION 3.11)

project(markergen LANGUAGES CXX)

file(GLOB HEADERS_FILES "include/*.h*")
file(GLOB SOURCE_FILES "src/*.cpp")
set(SOURCES ${HEADERS_FILES} ${SOURCE_FILES} ${RESOURCES_FILES})

add_executable(${PROJECT_NAME} "${SOURCES}")

find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED)

target_include_directories(${PROJECT_NAME} PRIVATE include)

target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_17)

target_link_libraries(${PROJECT_NAME}
PUBLIC
    Boost::boost
    ${OpenCV_LIBS}
    )
