# include cmake modules
include(FetchContent)

# disable cpp-terminal library targets
set(CPPTERMINAL_BUILD_EXAMPLES OFF CACHE BOOL "don't build examples" FORCE)
set(CPPTERMINAL_ENABLE_INSTALL OFF CACHE BOOL "disable install" FORCE)
set(CPPTERMINAL_ENABLE_TESING OFF CACHE BOOL "disable testing of folf" FORCE)

# disable not required FOLF targets
set(FOLF_BUILD_EXAMPLES OFF CACHE BOOL "don't build examples" FORCE)
set(FOLF_ENABLE_INSTALL OFF CACHE BOOL "disable install" FORCE)
set(FOLF_ENABLE_TESTING OFF CACHE BOOL "disable testing of folf" FORCE)

# disable google-test targets
set(INSTALL_GTEST OFF CACHE BOOL "disable gtest install" FORCE)
set(BUILD_GMOCK OFF CACHE BOOL "disable gmock" FORCE)

add_subdirectory(cpp-terminal)
add_subdirectory(googletest)
# add_subdirectory(folf-namespace)
