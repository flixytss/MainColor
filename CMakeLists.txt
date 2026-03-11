cmake_minimum_required(VERSION 3.10)
project(MainColor C)

set(CMAKE_C_COMPILER clang)

find_package(PNG REQUIRED)
find_package(JPEG REQUIRED)

add_executable(main-color src/main.c)

target_include_directories(main-color PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

target_link_libraries(main-color PRIVATE 
    PNG::PNG 
    ${JPEG_LIBRARIES} 
    m
)

install(TARGETS main-color RUNTIME DESTINATION /usr/bin)