#message(FATAL_ERROR "请修改 stbiw/CMakeLists.txt！要求生成一个名为 stbiw 的库")

# 静态库  动态：SHARED
add_library(stbiw STATIC stb_image_write.cpp)

# 将当前目录添加到使用stbiw库的目标的包含路径中（省略了前缀，直接include文件名即可）
# 并且等价为系统路径，可以使用#include<>
# PUBLIC：任何引用stbiw库的可执行文件都会自动包含当前目录
target_include_directories(stbiw PUBLIC .)