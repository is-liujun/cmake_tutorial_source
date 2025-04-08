cmake_minimum_required(VERSION 3.10)
project(Tutorial VERSION 11.25)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

configure_file(TutorialConfig.h.in TutorialConfig.h)

option(USE_MYMATH "Use My math ?" TRUE)
if(USE_MYMATH)
    add_subdirectory(MathFunctions)
    list(APPEND  EXTRA_LIBS MathFunctions)
endif()

add_executable(tutorialApp tutorial.cxx)

target_link_libraries(tutorialApp PUBLIC ${EXTRA_LIBS})
target_include_directories(tutorialApp PUBLIC ${PROJECT_BINARY_DIR})


