# CMakeList.txt: CMakeProject1 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
cmake_minimum_required (VERSION 3.8)

project ("JLang")

# 查找LLVM环境
find_package(LLVM REQUIRED CONFIG)

# 打印信息
message(STATUS "Found LLVM ${LLVM_PACKAGE_VERSION}")
message(STATUS "Using LLVMConfig.cmake in: ${LLVM_DIR}")
message(STATUS "Include in: ${LLVM_INCLUDE_DIRS}")
message(STATUS "DEF in: ${LLVM_DEFINITIONS}")

# 添加头文件包含路径
include_directories(${LLVM_INCLUDE_DIRS})
add_definitions(${LLVM_DEFINITIONS})

# 将源代码添加到此项目的可执行文件。
add_executable (JLang "main.cpp" "main.h")
