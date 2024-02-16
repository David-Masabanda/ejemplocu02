cmake_minimum_required(VERSION 3.26)
project(ejemplocu02 CUDA)

set(CMAKE_CUDA_STANDARD 17)

enable_language(CXX CUDA)

find_package(fmt)
find_package(SFML)



add_executable(ejemplocu02
        main.cpp
        kernel.cu)

target_include_directories(ejemplocu02
        PRIVATE
            ${CMAKE_CUDA_TOOLKIT_INCLUDE_DIRECTORIES}
)

target_link_libraries(
        ejemplocu02 fmt::fmt sfml::sfml
        ${CUDART_LIBRARY}
)

set_target_properties(ejemplocu02 PROPERTIES
        CUDA_SEPARABLE_COMPILATION ON)
