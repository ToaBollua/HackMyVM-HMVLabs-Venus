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

Así que simplemente tomamos eso y cambiamos de usuario...

angela@venus:~$ su emma

## 4) Mia
________________________|
user: mia               |
pass: iKXIYg0pyEH2Hos   |
________________________|

Desde Emma, sabremos al leer el archivo mission.txt que tenemos la contraseña de Mia en el archivo '-'. Pero aparentemente no podemos mover ni renombrar el archivo. El unico lugar donde podemos hacer modificaciones es el directorio '/tmp/'. Así que mandaremos el output de '-' a '/tmp/'

Así que:

emma@venus:~$ cp - /tmp/emmaPass.md   >>    Copiamos el archivo hacia /tmp/ y le ponemos un nombre que podamos ver con alguna aplicacion.

emma@venus:~$ cat /tmp/emmaPass.md  >>  Para leer el contenido del archivo. Que será la contraseña de Mia.

Así que simplemente cambiamos de usuario...

## 5) Camila
________________________|
user: camila            |
pass: F67aDmCAAgOOaOc   |
________________________|

Desde Mia, vemos en el archivo de mission.txt que la contraseña de Camila está escondida en una carpeta llamada 'hereiam'.

Así que buscamos la carpeta!

mia@venus:~$ find / -readable -type d -name hereiam  >> Para buscar cualquier directorio con es nombre y que sea accesible por nosotros en la máquina.

Veremos la ruta /opt/hereiam/

mia@venus:~$ ls -a /opt/hereiam/  >> Para ver todos los archivos del directorio.

mia@venus:~$ cat /opt/hereiam/.here >>  Leemos el contenido del archivo encontrado.

Y simplemente seguimos avanzando con el siguiente usuario!


## 6) Luna
________________________|
user: luna              |
pass: j3vkuoKQwvbhkMc   |
________________________|

Desde Camila, veremos que la contraseña de Luna está escondida en el directorio 'muack', que está lleno de subcarpetas, lo que hace dificil navegar por ellas.

Así que usamos el comando find de nuevo para buscar el archivo

camila@venus:~$ find muack/ -type f >> Con este buscamos todos los archivos dentro de 'muack/' y sus subcarpetas.

cat muack/111/111/muack >> Luego simplemente leemos el contenido del archivo.

Y cambiamos de usuario para seguir adelante!

## 7) Eleanor
________________________|
user: eleanor           |
pass: UNDchvln6Bmtu7b   |
________________________|

Desde Luna, veremos que la contraseña de Eleanor está escondida y solo sabemos que el archivo pesa 6969 bytes.

Así que debemos buscar un archivo con esas caracteristicas:

luna@venus:~$ find / -type f -size 6969c    >>  Con este comando buscamos archivos por tamaño.

Luego, al encontrarlo solo lo leemos:
luna@venus:~$ cat /usr/share/moon.txt

E iniciamos sesión con eleanor...


## 8) Victoria
________________________|
user: victoria          |
pass: pz8OqvJBFxH0cSj   |
________________________|

Podremos ver desde la cuenta de Eleanor que la contraseña de Victoria está escondida, está vez en un archivo del cual el duaño es el usuario 'violin'.

Así que debemos buscar el archivo con eso en cuenta:

eleanor@venus:~$ find / -type f -user violin    >>  Con este parametro '-user' podemosdefinir el propietario del archivo que estemos buscando.

Al encontrarlo, simplemente lo leemos y continuamos:

eleanor@venus:~$ cat /usr/local/games/yo    >>  Aquí está la contraseña de victoria.

Cambiamos de usuario!


## 9) Isla
________________________|
user: isla              |
pass: D3XTob0FUImsoBb   |
________________________|

Desde Victoria veremos que tenemos la contraseña de isla en un archivo .zip, simplemente debemos unzipearlo en donde podamos. En este caso, la carpeta /tmp/ como vimos en puntos pasados:

victoria@venus:~$ unzip passw0rd.zip -d /tmp/   >>  Con esto le decimos que queremos unzipear passw0rd.zip dentro de la carpeta tmp, que es la unica donde podemos escribir archivos.

Luego simplemente lo leemos:

victoria@venus:~$ cat /tmp/pwned/victoria/passw0rd.txt

Y seguimos!


## 10) Violet
________________________|
user: violet            |
pass: WKINVzNQLKLDVAc   |
________________________|

Veremos desde el usuario de Isla que la contraseña de Violet está en el archivo passy. Y que su contraseña está en la linea que empieza con 'a9HFX' (Sin ser estos 5 caracteres parte de la contraseña).

Así que hacemos simplemente grep:

isla@venus:~$ grep a9HFX -a passy   >>  Buscamos todas las lineas de texto que tengan estos caracteres, buscamos el que si es y ponemos la contraseña!

WKINVzNQLKLDVAca9HFX
dWeFra9HFXzNQLKLDVAc
kfRgNa9HFXzNQLKLDVAc
zNQa9HFXfEtrgLKLDVAc
WKINVzNQLa9HFXDwErfc
WKINVa9HFXzDcceWeTfd
a9HFXWKINVzNQLKLDVAc <<<    Esta es

su violet   >> Y seguimos (Resto en siguiente archivo!)
