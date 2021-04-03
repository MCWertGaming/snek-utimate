set(FRONTEND_TARGETS)

add_executable(hello-world main.cpp)
target_link_libraries(hello-world cpp-terminal gtest folf-namespace)