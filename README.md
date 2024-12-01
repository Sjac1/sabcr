# sabcr

## Simple-and-bad-cmake-raylib

Este es un, témplate que estoy usando en este momento
puede tener fallos e inconsistencias pero, quería una
plantilla simple y fácil para mi entender que estoy
haciendo.

Si le es útil a otros, sería genial.

## dependencias

- CMake 3.10+
- raylib

No he probado como funcionaria en un IDE u otros editores
de texto como vscode el que estoy usando es Neovim y por
y estoy usando un dotfile perteneciente a <https://github.com/Gentleman-Programming>
puede intentar usar ese dotfile porque implementa muchas
cosas y no he tenido problemas con nada.

Por el momento solo contiene tres carpetas y el archivo cmake

- include: todos los archivos de cabecera que se están
haciendo uso
- resouce: las implementaciones de los archivos de cabecera y
otros recursos que se hagan uso en el proyecto.
- src: solo contiene el archivo main.
- CMakeLists.txt

Para compilar el programa recomiendo eliminar la carpeta
build y crearla nuevamente, si encuentra una carpeta (.cache)
borrarla también. Como el servidor de lenguaje que uso es
clang el archivo CMake habilita un archivo compile_commands.json
para que clang encuentre los archivos y para usar esta
configuracion es:

~~~bash
git clone git@github.com:Sjac1/sabcr.git 
cd sabcr
rm -rf build/ compile_commands.json
mkdir build && cd build
cmake -S .. -B . && make && ln -sf compile_commands.json ../compile_commands.json
~~~

Otra manera es que uso más, crear un alias y no tener que
escribir todo el comando puede agregar la siguiente línea
al archivo .zshrc o .bashrc y recargar.

~~~bash
# Agregar a .zshrc o .bashrc
alias makecpp='cmake -S .. -B . && make && ln -sf compile_commands.json ../compile_commands.json'
# recargar
source .zshrc
~~~

Aún hay cosas que mejorar pero por el momento para cosas simples
no ha habido problema, lo iré cambiando con el tiempo.

Estas notas son más para mí, como recordatorio si les es
Útil muy bien.

Bye ^-^.
