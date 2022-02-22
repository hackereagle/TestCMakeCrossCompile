cmake_minimum_required(VERSION 3.10.0)
set(PROJECT_NAME TestCmakeCrossCompile)
project(${PROJECT_NAME})

if(CMAKE_CROSSCOMPILING)
	message(STATUS "cross compiling")
else()
	message(STATUS "general compiling")
endif()

aux_source_directory(. SRCS)
add_executable(${PROJECT_NAME} ${SRCS})
target_link_libraries(${PROJECT_NAME} ${CMAKE_DL_LIBS})