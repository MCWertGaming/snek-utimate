# configure about file
configure_file(info.hpp.in info.hpp)

set(snek_targets sneklib)

# # make chess a library
# add_library(sneklib snek.cpp)
# # target_link_libraries(NAMElib PRIVATE -lib-)
# target_include_directories(sneklib INTERFACE ${PROJECT_SOURCE_DIR} ${PROJECT_BINARY_DIR})
# set_target_properties(sneklib PROPERTIES
#         PUBLIC_HEADER "snek/snek.hpp;snek/info.hpp")
