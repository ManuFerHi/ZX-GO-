TEST1 (8-Ene-2016)

Es un port del trabajo original de David Banks (hoglet), como todo lo que tenemos de Acorn hasta el momento (fuentes originales en https://github.com/hoglet67/ElectronFpga).

Salida v�deo compuesto/RGB y VGA 50Hz seleccionables v�a teclado. Por defecto arranca en RGB/Vcomp. Tecla RePag = VGA, tecla AvPag = RGB/Vcomp. Tambi�n hay otros modos (60Hz, etc) usando combinaciones de ctrl+CapsLock+1 al 4)
Soporte SD/MMC, v�a archivos de imagen ".MMB" (BEEB.MMB, que son contenedores de im�genes de disquete). Explicado m�s abajo para que funcione correctamente (al igual que pasa con el core de BBC Micro)
Carga de software via cinta/audo por el puerto EAR del ZX-UNO.
Teclado PS/2 (mapeado a teclado ingl�s)
Sonido est�ndar.
Reset (tecla F10 y ctrl+F10)