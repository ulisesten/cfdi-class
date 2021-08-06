cmake_minimum_required(VERSION 2.8...3.10)
project(CFDI)

#Project CFDI

set(SRC ${PROJECT_SOURCE_DIR}/src/cfdv33.cxx
        ${PROJECT_SOURCE_DIR}/src/catCFDI.cxx
        ${PROJECT_SOURCE_DIR}/src/tdCFDI.cxx
)

find_package(PkgConfig REQUIRED)

if(PKG_CONFIG_FOUND)
    message(STATUS "Pkg config found")
    endif 	(PKG_CONFIG_FOUND )
    
add_library(${PROJECT_NAME} SHARED ${SRC})

include_directories(${PROJECT_SOURCE_DIR}/../xerces-c/src)
target_link_directories(${PROJECT_NAME}
                            PUBLIC
                                ${PROJECT_SOURCE_DIR}/../lib/xerces-c-lib/src
)


include_directories(${PROJECT_SOURCE_DIR}/include)
target_link_libraries(${PROJECT_NAME} xerces-c-3.2)
