cmake_minimum_required(VERSION 3.16)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Nombre del proyecto y configuración
project(plantilla VERSION 1.0)

# Estander c++
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
# Incluye directorios de encabezados
include_directories(include)

# Busca raylib (asegúrate de que esté disponible)
find_package(raylib REQUIRED)

# Recopila automáticamente todos los archivos fuente y cabecera
# si decea agradae otra carpera puede hacer como carpeta/*.cpp
# o crearla dentro de otra asi resource/carpeta/*.cpp
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS
    src/*.cpp
    resource/*.cpp
)

# Crea el ejecutable con todos los archivos fuente encontrados
add_executable(${PROJECT_NAME} ${SOURCES})

# Enlaza raylib
target_link_libraries(${PROJECT_NAME} PRIVATE raylib)

# Enlazar bibliotecas necesarias en sistemas UNIX
if(UNIX)
    target_link_libraries(${PROJECT_NAME} PRIVATE c pthread dl)
endif()

