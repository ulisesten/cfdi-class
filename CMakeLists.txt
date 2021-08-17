cmake_minimum_required(VERSION 2.8...3.10)
project(CFDI)

#Project CFDI

set(SRC ${PROJECT_SOURCE_DIR}/src/cfdv33.cxx
        ${PROJECT_SOURCE_DIR}/src/catCFDI.cxx
        ${PROJECT_SOURCE_DIR}/src/tdCFDI.cxx
)

#find_package(PkgConfig REQUIRED)

#if(PKG_CONFIG_FOUND)
#    message(STATUS "Pkg config found")
#    endif 	(PKG_CONFIG_FOUND )
    
add_library(${PROJECT_NAME} STATIC ${SRC})

include_directories(
    ${PROJECT_SOURCE_DIR}/include
    "../xerces-c/src"
    "../lib/xerces-lib/src"
    "c:/XSD/include"
)
link_directories(${PROJECT_NAME}
                            PUBLIC
                                "../lib/xerces-lib"
)

target_link_libraries(${PROJECT_NAME} xerces-c-3.2)
