cmake_minimum_required(VERSION 3.12)

project(CMakeExampleProject)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY         ${CMAKE_SOURCE_DIR}/build                    )
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/release/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG   ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/debug/bin  )

# if (MSVC)
#    add_compile_options(/W4 /WX)
# else()
#    add_compile_options(-pedantic-errors -Wall -Wextra -Werror)
# endif()


include(FetchContent)
FetchContent_Declare(fmt
  GIT_REPOSITORY https://github.com/fmtlib/fmt.git
  GIT_TAG master
)
FetchContent_MakeAvailable(fmt)

add_subdirectory(examples)

# include_directories(${CMAKE_SOURCE_DIR}/../libraries/fmt/include)


# include_directories(${CMAKE_SOURCE_DIR}/include)

# add_subdirectory(src)
