cmake_minimum_required(VERSION 2.8...3.10)
project(CFDI)

#Project CFDI

set(SRC ${PROJECT_SOURCE_DIR}/src/cfdv33.cxx
        ${PROJECT_SOURCE_DIR}/src/catCFDI.cxx
        ${PROJECT_SOURCE_DIR}/src/tdCFDI.cxx
)

find_package(PkgConfig REQUIRED)
find_package(XercesC   REQUIRED)

if(PKG_CONFIG_FOUND)
    message(STATUS "Pkg config found")
endif 	(PKG_CONFIG_FOUND )
    
add_library(${PROJECT_NAME} STATIC ${SRC})

include_directories(
    ${PROJECT_SOURCE_DIR}/include
    ${XercesC_INCLUDE_DIRS}
)
target_link_directories(${PROJECT_NAME}
                            PUBLIC
                            ${XercesC_LIBRARIES}
)

target_link_libraries(${PROJECT_NAME} XercesC::XercesC)
