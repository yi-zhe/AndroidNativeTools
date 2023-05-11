cmake_minimum_required(VERSION 3.10.2)
project("AndroidNativeTools")

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_library(pagemap
        STATIC
        libpagemap/pm_kernel.c
        libpagemap/pm_map.c
        libpagemap/pm_memusage.c
        libpagemap/pm_process.c)

add_executable(procmem procmem/procmem.c)
target_link_libraries(procmem pagemap)

add_executable(procrank procrank/procrank.c procrank/strlcpy.c)
target_link_libraries(procrank pagemap)

# Android 9更新了procrank代码
# base库的代码是从Android 9源码复制出来并做了简单修改
add_library(base
        STATIC
        procrank/android-base/file.cpp
        procrank/android-base/stringprintf.cpp
        procrank/android-base/strings.cpp)

add_executable(procrank-9 procrank/procrank.cpp procrank/strlcpy.c)
target_link_libraries(procrank-9 pagemap base)
