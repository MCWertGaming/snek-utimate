cmake_minimum_required(VERSION 3.16)
project(snek_ultimate
        VERSION 0.0.1
        DESCRIPTION "SNEK Utimate - a Snake clone with new game modes and nice extras"
        HOMEPAGE_URL "https://github.com/MCWertGaming/snek-utimate"
        LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)

#inlcude sub directories
add_subdirectory(tests)
add_subdirectory(snek-menu)
add_subdirectory(snek)
add_subdirectory(snek-frontends)
add_subdirectory(dependencies)

set(target_list ${snek_targets} ${snek_menu_targets} ${snek_frontend_targets})

# enable warnings and set compile features
foreach(target ${target_list})
        # Force Microsoft Visual Studio to decode sources files in UTF-8
        if (MSVC)
                target_compile_options(${target} PUBLIC "/utf-8")
        endif()
        # Add as many warning as possible:
        if (WIN32)
                if (MSVC)
                        target_compile_options(${target} PRIVATE "/W4")
                        target_compile_options(${target} PRIVATE "/WX")
                        target_compile_options(${target} PRIVATE "/wd4244")
                        target_compile_options(${target} PRIVATE "/wd4267")
                        target_compile_options(${target} PRIVATE "/D_CRT_SECURE_NO_WARNINGS")
                endif()
                # Force Win32 to UNICODE
                target_compile_definitions(${target} PRIVATE UNICODE _UNICODE)
        else()
                target_compile_options(${target} PRIVATE "-Wall")
                target_compile_options(${target} PRIVATE "-Wextra")
                target_compile_options(${target} PRIVATE "-pedantic")
                target_compile_options(${target} PRIVATE "-Werror")
                target_compile_options(${target} PRIVATE "-Wno-sign-compare")
        endif()
endforeach(target ${target_list})
