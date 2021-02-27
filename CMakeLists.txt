project(easylogging++)
cmake_minimum_required(VERSION 3.1.3)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED on)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

set(INSTALL_PATH_LIB lib)
set(INSTALL_PATH_INCLUDE include)

aux_source_directory(log SRC_LIST)
add_compile_options(-Wfatal-errors)

add_library(${CMAKE_PROJECT_NAME}_static STATIC ${SRC_LIST})

include_directories(log)
add_subdirectory(test)

#add_subdirectory(test)