cmake_minimum_required(VERSION 3.10)
project(Tutorial VERSION 21.2)
add_subdirectory(MathFunctions)
add_executable(tutorialApp tutorial.cxx)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

configure_file(TutorialConfig.h.in TutorialConfig.h)

option(USE_MYMATH "control sqrt algorithm" TRUE)

if(USE_MYMATH)
    list(APPEND EXTRA_LIBS MathFunctions)
    list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")
endif()

target_link_libraries(tutorialApp PUBLIC ${EXTRA_LIBS})
target_include_directories(tutorialApp PUBLIC ${PROJECT_BINARY_DIR} ${EXTRA_INCLUDES})

