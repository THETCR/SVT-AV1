#
# Copyright(c) 2019 Intel Corporation
# SPDX - License - Identifier: BSD - 2 - Clause - Patent
#
# Common/Codec Directory CMakeLists.txt

# Include Encoder Subdirectories
include_directories (${PROJECT_SOURCE_DIR}/Source/API/)
include_directories (${PROJECT_SOURCE_DIR}/Source/Lib/Common/Codec/)
include_directories (${PROJECT_SOURCE_DIR}/Source/Lib/Common/C_DEFAULT/)
include_directories (${PROJECT_SOURCE_DIR}/Source/Lib/Common/ASM_SSE2/)
include_directories (${PROJECT_SOURCE_DIR}/Source/Lib/Common/ASM_SSSE3/)
include_directories (${PROJECT_SOURCE_DIR}/Source/Lib/Common/ASM_SSE4_1/)
include_directories (${PROJECT_SOURCE_DIR}/Source/Lib/Common/ASM_AVX2/)

if(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
    SET(CMAKE_C_FLAGS "/MP")
endif(${CMAKE_SYSTEM_NAME} MATCHES "Windows")

file(GLOB all_files
    "*.h"
    "*.c")

add_library(COMMON_CODEC OBJECT ${all_files})
