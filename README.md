# cfdi-class

Clases de C++ para fatura electronica SAT México, obtenidas de los archivos xsd.

Clases generadas con xsdcxx

Puedes añadirlas como submódulo git y construirlas con cmake

    cd una_carpeta
    git submodule add https://github.com/ulisesten/cfdi-class.git

CMake:

    add_subdirectory(cfdi-class carpeta_de_compilacion)
    find_package(XercesC REQUIRED)

    include_directories(
        ${XercesC_INCLUDE_DIRS}
        ${PROJECT_SOURCE_DIR}/una_carpeta/cfdi-class/include
    )

    link_directories(
        ${XercesC_LIBRARIES}
    )
    
    target_link_directories(
        ${PROJECT_NAME}
            PUBLIC
                ${PROJECT_SOURCE_DIR}/carpeta_de_compilacion
    )

# Notas (TODO list)

Los archivos son extremadamente grandes. Será necesario borrar los catálogos y cambiarlos por una base de datos para reducir el tamaño y el tiempo de compilación.

Estas clases son usadas en el repositorio [facturacion-electronica](https://github.com/ulisesten/facturacion-electronica)

No han sido probadas en Windows aún


# Dependencias

[XercesC](https://xerces.apache.org/xerces-c/)
