# Programacion PLC
Simulador diagrmas eléctricos: CADe_Simu<br><br>
Codigo Acceso: 4962 <br><br>
Programa de PLC: TIA Portal 13 (ver a partir de Clase 4)<br><br>
Documento con detalles: Programacion PLC.docx<br><br>

# Índice
<!-- [Texto visible clickeable](#anchor-que-funciona-como-enlace) El anchor en lugar de espacios, se separa por "-" -->
- [Clase 1 - Introduccion](#clase-1---introduccion)
- [Clase 2 - Armado de arranque directo motor trifasico](#clase-2---armado-de-arranque-directo-motor-trifasico)
- [Clase 3 - Arranque directo e inversion de giro](#clase-3---arranque-directo-e-inversion-de-giro)
- [Clase 4 - Arranque estrella triangulo](#clase-4---arranque-estrella-triangulo)
- [Clase 5 - PLC Arranque directo](#clase-5---plc-arranque-directo)


## Clase 1 - Introduccion
<strong>Contactor:</strong><br>
<p align="center"><img src="imagenes/1-introduccion/contactor.jpg" alt="Contactor" height="250"></p>
<br><br><br><br>

<strong>Contactos Auxiliares:</strong><br>
<p align="center"><img src="imagenes/1-introduccion/contactos_auxiliares_nc_na.jpg" alt="Contactos auxiliares" height="250"></p>
<br><br><br><br>

<strong>Interruptor Automatico:</strong><br>
<p align="center"><img src="imagenes/1-introduccion/interruptor_automatico.jpg" alt="Interruptor Automatico" height="250"></p>
<br><br><br><br>

<strong>Pulsador:</strong><br>
<p align="center"> <img src="imagenes/1-introduccion/pulsador.jpg" alt="Pulsador" height="250"> </p>
<br><br><br><br>

<strong>Relé Térmico:</strong><br>
<p align="center"> <img src="imagenes/1-introduccion/rele_termico.jpg" alt="rele_termico" height="250"> </p>
<br><br><br><br>

<strong>Contacto auxiliar rele termico:</strong><br>
<p align="center"> <img src="imagenes/1-introduccion/contacto_auxiliar_rele_termico.jpg" alt="Contacto auxiliar rele termico" height="250"> </p>
<br><br><br><br>

<strong>Bobina:</strong><br>
<p align="center"> <img src="imagenes/1-introduccion/bobina.jpg" alt="Bobina" height="250"> </p>
<br><br><br><br>

## Clase 2 - Armado de arranque directo motor trifasico
<strong>Esquematico arranque directo:</strong><br>
[Programa: CADe_Clase1_arranque_directo](Programas/)<br><br>
<img src="imagenes/2-arranque_directo/arranque_directo_y_parada_motor_trifasico.svg" alt="Arranque directo motor trifasico" width="120%"><br>
<br><br><br><br>

## Clase 3 - Arranque directo e inversion de giro
<strong>Esquematico arranque directo e inversion de giro:</strong><br>
[Programa: CADe_Clase3_arranque_directo_e_inversion_giro](Programas/)<br><br>
<img src="imagenes/3-arranque_directo_e_inversion/esquema_arranque_trifasico_directo_e_inversion_de_giro.svg" alt="Arranque directo motor trifasico" width="120%"><br>
<br><br><br><br>

## Clase 4 - Arranque estrella triangulo

<strong>Temporizador retardo a conexion:</strong><br>
<img src="imagenes/4-estrella_triangulo/timer_retardo_conexion.jpg" alt="Temporizador con retardo a conexion" width="60%"><br>
<br><br><br><br>
<strong>Contactores estrella y triangulo:</strong><br>
<img src="imagenes/4-estrella_triangulo/contactor_triangulo.jpg" alt="Contactor triangulo" width="60%"><br>
<img src="imagenes/4-estrella_triangulo/contactor_estrella.jpg" alt="Contactor triangulo" width="60%"><br>
<a href="imagenes/4-estrella_triangulo/video_conexion_triangulo_estrella.mp4">Ver video demostración</a>
<br>

<strong>Conexion arranque estrella triangulo:</strong><br>
<img src="imagenes/4-estrella_triangulo/conexion_arranque_triangulo_estrella.jpg" alt="Arranque estrella triangulo" width="60%"><br>
<br><br><br><br>
<strong>Esquematico arranque estrella triangulo:</strong><br>
[Programa: CADe_Clase_4_Estrella_Triangulo](Programas/)<br><br>
<img src="imagenes/4-estrella_triangulo/esquema_arranque_estrella_triangulo.svg" alt="Esquema arranque estrella triangulo" width="100%"><br>
<br><br><br><br>

## Clase 5 - PLC Arranque directo
### Configuracion de PLC Siemens 1200
1) Crear Proyecto > Seleccionar Nombre y Ruta
2) Dispositivos y Redes > Agregar dispositivos > S7-1200 el nuestro es CPU 1214ACDCRly > Ver cual es el equipo 6E17 214BE30-0XB0
3) Sobre la imagen del PLC, para bajar los datos hacer doble click en el puerto Profinet y ajustar dirección IP y máscara subred según dispositivo: 
El último dígito depende el dispositivo que use en la red, Ejemplo: 192.168.0.1. Conectar el cable Ethernet.
4) Variables PLC > Tabla de variables: Crear las variables que utilizaré en el proyecto.
<img src="imagenes/6-mem-set-reset/tabla_de_variables.jpg" alt="tabla_de_variables_plc" width="100%"><br>
6) Barra de Herramientas > Cargar dispositivo > Tipo interfaz PN/IE. Cargar información cuando esté en STOP.<br>
<img src="imagenes/6-mem-set-reset/config_run_error.jpg" alt="config run error" width="100%"><br>
7) Crear los bloques del programa > Main [OB1]. Siempre tener detenido programa antes de cargarlo. Utilizar "ícono de lentes" para ver ejecución de programa.
<br><br>

### PLC Arranque directo
<strong>PLC S7-1200:</strong><br>
<img src="imagenes/5-clase_plc1/PLC_equipamento.jpg" alt="PLC_equipamento" width="60%"><br>
<img src="imagenes/5-clase_plc1/PLC_equipamento_lateral.jpg" alt="PLC_equipamento_lateral" width="60%"><br>
<img src="imagenes/5-clase_plc1/PLC_arranque_directo.jpg" alt="PLC_arranque_directo" width="60%"><br>
<br><br><br><br>

### Funciones Lógicas
Para optimizar diseños también es recomendable utilizar los mapas de Karnaugh.
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_SI.svg" alt="ladder_si" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_NOT.svg" alt="ladder_not" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_AND.svg" alt="ladder_and" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_OR.svg" alt="ladder_or" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_NOR.svg" alt="ladder_nor" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_NAND.svg" alt="ladder_nand" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_XOR.svg" alt="ladder_xor" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_FUNCION.svg" alt="ladder_funcion" width="60%"><br>
<img src="imagenes/5-clase_plc1/ladder_funcion_logica_FUNCION_KARNAUGH.svg" alt="ladder_funcion_karnaugh" width="60%"><br>

## Clase 6 - Utilizacion de Memoria, Flancos, Set y Reset
Puede contruirse un "interruptor" con estos elementos:
<a href="imagenes/4-estrella_triangulo/video-mem-set-reset.mp4">Ver video demostración</a>

Esquema CADe SIMU de conexión PLC físico con Set y Reset <br>
Ejercicio simple con Set y Reset:<br>
<img src="imagenes/6-mem-set-reset/ej_simple_set_reset.jpg" alt="ladder_mem_set_reset" width="60%"><br>
<br>
Ejercicio SET y RESET utilizando memoria:<br>
<img src="imagenes/6-mem-set-reset/diagrama_set_reset_mem_con_plc.svg" alt="ladder_mem_set_reset" width="60%"><br>
