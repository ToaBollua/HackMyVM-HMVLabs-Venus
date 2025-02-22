## 0) Intro
________________|
user: hacker    |
pass: havefun!  |
________________|

Tienes que hacer ssh a la máquina de HMV usando el puerto 5000:

ssh hacker@venus.hackmyvm.eu -p 5000
_____________________________________|

## 1) Sophia
________________________|
user: sophia            |
pass: Y1o645M3mR84ejc   |
________________________|

Desde hacker, al leer mission.txt, sabrás que debes buscar en un archivo oculto:

hacker@venus:~$ ls -a   >>  Para ver todos los archivos en la carpeta en la que estés.
hacker@venus:~$ cat .myhiddenpazz >> Para ver el archivo oculto.

Luego solo debes copiar la contraseña e iniciar sesión como sophia:

su sophia   >>  Para iniciar sesión como sophia.

## 2) Angela
________________________|
user: angela            |
pass: oh5p9gAABugHBje   |
________________________|

Desde sophia, al leer mission.txt, sabremos que debemos encontrar el archivo llamado 'whereismypazz.txt':

sophia@venus:~$ find / -readable -name whereismypazz.txt    >>  Para encontrar cualquier archivo legible para nosotros que se llame 'whereismypazz.txt'.

Encontraremos la siguiente ruta: "/usr/share/whereismypazz.txt".

cat /usr/share/whereismypazz.txt    >> Para leer el archivo que encontramos.

Cambiamos de usuario:

su angela   >>  Iniciamos sesión como angela.

## 3) Emma
________________________|
user: emma              |
pass: fIvltaGaq0OUH8O   |
________________________|

Desde Angela, al leeer el mission.txt, vemos que la contraseña está en la línea 4069 del archivo findme.txt.

Lo que yo hice fue un poco extraño:

angela@venus:~$ cat -n findme.txt | grep -a 4069  >>    Hice que cat me diera las lineas de cada texto ennumeradas, y tomé la 4069 con grep.


