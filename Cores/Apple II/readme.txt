TEST3 (06-Sep-2016)

A�adidas tarjetas de expansi�n de RAM. 128K Saturn RAM (slot 5) + 16K Language card (slot 0).
Reescrito y sustituido completamente el core de teclado ps/2. Ahora es mucho m�s estable.
A�adida combinaci�n Master Reset (Ctrl + Alt + Backspace) para volver al core de Spectrum (como estamos haciendo de foma est�ndar para todos los cores, paulatinamente)
Eliminado Reset externo para mayor estabilidad. El reset en fr�o ahora es �nicamente interno.
Reset en fr�o (tecla F12) mejorado, inicializando porci�n de SRAM (0x3F4), para que tras cada reset siempre arranque de la unidad de disco y no haya corrupciones.
A�adida funci�n de scanlines VGA, activable mediante la tecla "-" del teclado num�rico. (EXPERIMENTAL. A�n hay que ajustar timings)
A�adida funci�n de cambio de tipo de monitor Color / Blanco y negro, activable mediante la tecla "*" del teclado num�rico
Arreglado bot�n 2 del joystick, ahora funciona.
Aumentada la capacidad de arrancar desde im�genes de disco en SD (RAW), ahora se pueden insertar hasta 20 im�genes de disco distintas. Las primeras 10 pulsando de F1 a F10 y las siguientes 10, pulsando de SHIFT+F1 a SHIFT+F10.