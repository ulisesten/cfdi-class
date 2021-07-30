cmake_minimum_required(VERSION 2.8...3.10)
project(CFDI)

set(SRC ${PROJECT_SOURCE_DIR}/src/cfdv33.cxx
        ${PROJECT_SOURCE_DIR}/src/catCFDI.cxx
        ${PROJECT_SOURCE_DIR}/src/tdCFDI.cxx
)

find_package(PkgConfig REQUIRED)

if(PKG_CONFIG_FOUND)
    message(STATUS "Pkg config found")
endif 	(PKG_CONFIG_FOUND )

#GTK packages
find_package(XercesC REQUIRED)
include_directories(${XercesC_INCLUDE_DIRS})
link_directories(${XercesC_LIBRARIES})

add_library(${PROJECT_NAME} SHARED ${SRC})

include_directories(${PROJECT_SOURCE_DIR}/include)
target_link_libraries(${PROJECT_NAME} XercesC::XercesC)
