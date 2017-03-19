TEST1 (8-Ene-2016)

Es un port del trabajo original de David Banks (hoglet), como todo lo que tenemos de Acorn hasta el momento (fuentes originales en https://github.com/hoglet67/ElectronFpga).

Ya est� subido el fuente para el ZX-UNO y el .bit tanto para v2 como v3 (vale para ambos puesto que no usa la SRAM) en el repositorio SVN habitual.

Funciones actuales:

- Salida v�deo compuesto/RGB y VGA 50Hz seleccionables v�a teclado. Por defecto arranca en RGB/Vcomp. Tecla RePag = VGA, tecla AvPag = RGB/Vcomp. Tambi�n hay otros modos (60Hz, etc) usando combinaciones de ctrl+CapsLock+1 al 4)
- Soporte SD/MMC, v�a archivos de imagen ".MMB" (BEEB.MMB, que son contenedores de im�genes de disquete). Explicado m�s abajo para que funcione correctamente (al igual que pasa con el core de BBC Micro)
- Carga de software via cinta/audo por el puerto EAR del ZX-UNO.
- Teclado PS/2 (mapeado a teclado ingl�s)
- Sonido est�ndar.
- Reset (tecla F10 y ctrl+F10)

El core usa una rom (Smart SPI) que lee de la SD un archivo normalmente grande, que contiene im�genes de disquete, que debe tener el nombre de BEEB.MMB en el directorio ra�z. Este archivo lo pod�is crear vosotros mismos con una utilidad incluida (MMBImager.exe) o bien descargar uno preparado con software y juegos, de los que hay por la red para Acorn Electron (por ejemplo, este, ajeno a este foro: https://mega.nz/#!ZE8FxQSC!EN89saPfSfO0 ... SAOvhdbGJA)

Pero no basta con copiarlo directamente a la SD si ya hay cosas dentro, y seguramente al 99% que no lea correctamente dando corrupciones. Por tanto para que funcione 100% bien:

1- Formatear una SD (si no es muy grande, mejor) en FAT o FAT32, pero NO en formato r�pido (en Windows, desmarcar la casilla de formato r�pido). Esto es muy importante.
2- Copiar a la SD el archivo BEEB.MMB, de modo que este sea el PRIMER archivo que se copia a la SD.
3- Si se desea, ya se pueden copiar otros archivos a la SD para usar con otros cores, pero SIEMPRE debe mantenerse el BEEB.MMB como el primero que se copi� a la SD. Es muy importante.

Una vez metida la SD en el ZX-UNO y arrancado el core, si el archivo de antes (BEEB.MMB) est� bien grabado y reconoce bien la SD. Al arrancar deber�a aparecer:

C�DIGO: SELECCIONAR TODO
Acorn Electron
Smart SPI
BASIC
>


Autom�ticamente se automonta el disco 0 de la imagen, podemos ver su contenido tecleando *CAT
Por alg�n motivo que desconozco, a diferencia de lo que pasa en el core de BBC micro que autoarranca si el disco tiene Boot al pulsar shift+F10 y tampoco van los comandos de carga de binarios (como *RUN) pero s� podemos cargar cargadores BASIC sin problemas:

Para cargar el men� de juegos que viene en la imagen precargada que comentaba antes, tecleamos: CHAIN"MENU"

Para cargar desde cassete/Entrada de audio EAR, he incluido en la carpeta "varios" el programa FreeUEF.exe que sirve para reproducir cintas en formato UEF en el PC. Viene una de ejemplo de una revista. Tambi�n las convierte a WAV para reproducirlos luego desde otro dispositivo como el m�vil.

Para cargar de cinta: Tecleamos primero: *TAPE
Y despu�s: CHAIN"" y pulsamos PLAY.

Y eso es todo. Para resetear, en este caso es F10 o ctrl+F10.
