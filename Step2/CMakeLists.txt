cmake_minimum_required(VERSION 3.10)
project(Tutorial VERSION 21.2)
add_subdirectory(MathFunctions)
add_executable(tutorialApp tutorial.cxx)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

configure_file(TutorialConfig.h.in TutorialConfig.h)


target_link_libraries(tutorialApp PUBLIC MathFunctions)
target_include_directories(tutorialApp PUBLIC ${PROJECT_BINARY_DIR} ${PROJECT_SOURCE_DIR}/MathFunctions)

