cmake_minimum_required(VERSION 3.10)
project(Tutorial VERSION 11.25)
#指定c++标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(tutorialApp tutorial.cxx)

# message(STATUS "This is a status message")
# message(STATUS "project Turorial's version major:${Tutorial_VERSION_MAJOR}")
# message(STATUS "project Tutorial's version minor:${Tutorial_VERSION_MINOR}")
# message(STATUS "PROJECT_BINARY_DIR is ${PROJECT_BINARY_DIR}")

target_include_directories(tutorialApp PUBLIC ${PROJECT_BINARY_DIR})
configure_file(TutorialConfig.h.in TutorialConfig.h)





