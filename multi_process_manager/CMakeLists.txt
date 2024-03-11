cmake_minimum_required(VERSION 3.0)
project(multi_process_manager)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_COMPILER clang++)

add_library(multi_process_manager SHARED
    src/new_popen.cpp
)

# .so
install(TARGETS multi_process_manager
    DESTINATION lib
)

target_include_directories(multi_process_manager
    PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)


# demo
add_executable(demo src/demo.cpp)
target_link_libraries(demo multi_process_manager)
install(TARGETS demo
DESTINATION lib
)
