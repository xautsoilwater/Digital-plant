cmake_minimum_required(VERSION 3.15)
project(DigitalCrop VERSION 0.1.0 LANGUAGES CXX)

# 设置CMake策略
if(POLICY CMP0074)
  cmake_policy(SET CMP0074 NEW)
endif()

# 设置输出目录
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# 添加项目根目录到模块路径
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

# 编译核心库
add_subdirectory(src/core)

# 为测试启用CTest
option(BUILD_TESTING "Build the testing tree." ON)
if(BUILD_TESTING)
    enable_testing()
    add_subdirectory(tests)
endif()

# 安装Python模块
install(DIRECTORY src/python/
        DESTINATION ${CMAKE_INSTALL_PREFIX}/lib/python/digitalcrop
        FILES_MATCHING PATTERN "*.py")

# 安装文档
install(FILES README.md LICENSE
        DESTINATION ${CMAKE_INSTALL_PREFIX}/share/doc/digitalcrop)

# 包装配置
include(CPack)
set(CPACK_PACKAGE_VENDOR "Digital Crop Team")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Digital Crop - 新一代作物精细仿真平台")
set(CPACK_PACKAGE_VERSION_MAJOR ${PROJECT_VERSION_MAJOR})
set(CPACK_PACKAGE_VERSION_MINOR ${PROJECT_VERSION_MINOR})
set(CPACK_PACKAGE_VERSION_PATCH ${PROJECT_VERSION_PATCH})
set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_CURRENT_SOURCE_DIR}/LICENSE")
set(CPACK_RESOURCE_FILE_README "${CMAKE_CURRENT_SOURCE_DIR}/README.md") 