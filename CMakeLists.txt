cmake_minimum_required(VERSION 3.16)
project(snek
        VERSION 0.0.1
        DESCRIPTION "SNEK-Ultimate"
        HOMEPAGE_URL "https://github.com/MCWertGaming/snek-ultimate"
        LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)
# configure_file(src/information.hpp.in src/information.hpp)

add_executable(test snek-ultimate/main.cpp)
# target_include_directories(snek-debugFront PUBLIC ${PROJECT_BINARY_DIR}/src)
# target_link_libraries(snek-debugFront ncurses)
