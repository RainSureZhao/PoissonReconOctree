cmake_minimum_required(VERSION 3.28)
project(PoissonReconOctree)

set(CMAKE_CXX_STANDARD 17)
if (MSVC)
    # add_compile_definitions(RELEASE)
    add_compile_definitions(NOMINMAX)
    add_compile_definitions(WIN32_LEAN_AND_MEAN)
    add_compile_options(/bigobj)
endif ()



add_subdirectory(PoissonRecon)

add_executable(PoissonReconOctree main.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE PoissonRecon/Src)
target_link_libraries(${PROJECT_NAME} PoissonRecon)
