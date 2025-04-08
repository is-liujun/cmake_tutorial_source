cmake_minimum_required(VERSION 3.10)
project(CmakeTutorial)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(tutorialApp tutorial.cxx)
add_subdirectory(MathFunctions)
target_link_libraries(tutorialApp PUBLIC MathFunctions)
target_include_directories(tutorialApp PUBLIC "${PROJECT_BINARY_DIR}"
                                       "${PROJECT_SOURCE_DIR}/MathFunctions")



