cmake_minimum_required(VERSION 3.12)
project(hellocmake LANGUAGES CXX)

if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

# 可以在根目录调用该文件夹下的CMakeLists.txt
add_subdirectory(stbiw) 

add_executable(main main.cpp rainbow.cpp mandel.cpp)

# 将stbiw库链接到 main 可执行文件上   与子目录下的add_library()对应
target_link_libraries(main PUBLIC stbiw)
