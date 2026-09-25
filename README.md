# Programacion PLC
Simulador diagramas eléctricos: CADe_Simu<br><br>
Codigo Acceso: 4962 <br><br>
Programa de PLC: TIA Portal 13 <br><br>
Documento con detalles: Programacion PLC.docx<br><br>

# Índice
<!-- [Texto visible clickeable](#anchor-que-funciona-como-enlace) El anchor en lugar de espacios, se separa por "-" -->
- [Clase 1 - Introduccion](#clase-1---introduccion)
- [Clase 2 - Armado de arranque directo motor trifasico](#clase-2---armado-de-arranque-directo-motor-trifasico)
- [Clase 3 - Arranque directo e inversion de giro](#clase-3---arranque-directo-e-inversion-de-giro)
- [Clase 4 - Arranque estrella triangulo](#clase-4---arranque-estrella-triangulo)
- [Clase 5 - PLC Arranque directo](#clase-5---plc-arranque-directo)
- [Clase 6 - Utilizacion de Memoria,Flancos,Set y Reset](#clase-6---utilizacion-de-memoria,flancos,set-y-reset)
- [Clase 7 - Temporizadores](#clase-7---temporizadores)
- [Clase 8 - Machine Expert Basic - Schneider](#clase-8---schneider)
- [Clase 9 - Contadores](#clase-9---contadores)
- [Clase 10 - Variador de velocidad](#clase-10---variador-de-velocidad)

## Clase 1 - Introduccion
<strong>Contactor:</strong><br>
Es interruptor electromagnético accionado por medio de bobina. Campo magnético atrae a núcleo y cierra los contactos. Posee contactos de control. Al desenergizarse desaparece campo magnético y resorte devuelve núcleo a posición inicial.
<br>
<p align="center"><img src="imagenes/1-introduccion/contactor.jpg" alt="Contactor" height="250"></p>
<br><br>

<strong>Contactos Auxiliares:</strong><br>
Ayudan con la lógica del contactor. Se encuentran dentro del propio contactor. Sirven para auto-retemcion y aplicar lógica de enclavamiento. Pueden ser NC (normal cerrado) o NA (normal abierto).
<br>
<p align="center"><img src="imagenes/1-introduccion/contactos_auxiliares_nc_na.jpg" alt="Contactos auxiliares" height="250"></p>
<br><br>

<strong>Interruptor Automatico:</strong><br>
Es un elemento que protege contra cortocircuitos.
- Protección térmica (sobrecarga): Actúa cuando circula corriente superior a la nominal durante tiempo largo.
Dentro de interruptor hay lámina bimetálica con diferente dilatación termica que se deforma al calentarse y acciona el mecanismo.<br>
- Protección magnética: Cuando la corriente es muy alta el campo magnético también lo es. Se atrae núcleo móvil y se dispara el mecanismo. Los contactos se abren repentinamente en milisegundos.<br>
Ejemplo: fase y neutro entran en contacto o aparece una corriente muy alta.
No se destruye al actuar. Se rearma al levantar la palanca.
<br>
<p align="center"><img src="imagenes/1-introduccion/interruptor_automatico.jpg" alt="Interruptor Automatico" height="250"></p>
<br><br>

<strong>Pulsador:</strong><br>
Cierra o abre el circuito mientras se mantenga pulsado. Puede ser NC o NA. 
<br>
<p align="center"> <img src="imagenes/1-introduccion/pulsador.jpg" alt="Pulsador" height="250"> </p>
<br><br>

<strong>Relé Térmico:</strong><br>
Protege al motor de sobrecargas al detectar sobrecorriente y abre el circuito de control. Si el motor está consumiendo más corriente que la debería puede calentarse y dañarse. Utiliza láminas bimetálicas que se calientan y deforman lentamente, accionando el mecanismo de disparo.
<br>
<p align="center"> <img src="imagenes/1-introduccion/rele_termico.jpg" alt="rele_termico" height="250"> </p>
<br><br>

<strong>Contacto auxiliar rele termico:</strong><br>
<p align="center"> <img src="imagenes/1-introduccion/contacto_auxiliar_rele_termico.jpg" alt="Contacto auxiliar rele termico" height="250"> </p>
<br><br>

<strong>Bobina:</strong><br>
Asociada a contactores, al energizarse lo cerrará.
<br>
<p align="center"> <img src="imagenes/1-introduccion/bobina.jpg" alt="Bobina" height="250"> </p>
<br><br>

## Clase 2 - Armado de arranque directo motor trifasico
<strong>Esquematico arranque directo:</strong><br>
[Programa: CADe_Clase1_arranque_directo](Programas/)<br><br>
<img src="imagenes/2-arranque_directo/arranque_directo_y_parada_motor_trifasico.svg" alt="Arranque directo motor trifasico" width="120%"><br>
<br><br>

## Clase 3 - Arranque directo e inversion de giro
<strong>Esquematico arranque directo e inversion de giro:</strong><br>
[Programa: CADe_Clase3_arranque_directo_e_inversion_giro](Programas/)<br><br>
<img src="imagenes/3-arranque_directo_e_inversion/esquema_arranque_trifasico_directo_e_inversion_de_giro.svg" alt="Arranque directo motor trifasico" width="120%"><br>
<br><br><br><br>

## Clase 4 - Arranque estrella triangulo

El motor trifásico es de marca SIEMENS, Modelo: 1MJ6133-4CA60 (trifásico asíncrono) de 85 kg.<br>
Potencia de motor: 4 kW.<br>
Frecuencia: 50 Hz.<br>
Velocidad nominal: 945 rpm (motor de 6 polos)<br>
Factor de potencia cos(phi): 0,76.<br>
Tensión nominal: 400/690 V (triangulo/estrella) o rango de 380-420V/660-725 V (triangulo/estrella).<br>
Corriente nominal: 9,6 A en triangulo / 5,5 A en estrella para 400/690V (y hasta 10 A / 5,8 A en el rango de voltaje extendido).<br>
<br>
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

### Lenguajes Programación PLC (IEC 61131-3)
- Diagrama Ladder (LD)
- Diagrama Bloques Funcionales (FBD)
- GRAFCET: Graficos Funcionales Secuenciales (SFC: Sequential Function Charts)
- Texto Estructurado (ST)
- Lista de Instrucciones (IL)

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

## Clase 6 - Utilizacion de Memoria,Flancos,Set y Reset

Ejercicio simple con Set y Reset:
<br><br>
<img src="imagenes/6-mem-set-reset/ej_simple_set_reset.jpg" alt="ladder_mem_set_reset" width="60%"><br>
<br><br>


Puede contruirse un "interruptor" con estos elementos:<br>

Efecto interruptor: Con un pulsador normal al pulsar y soltar, la señal vuelve a 0. Esta implementación puede "recordar" si el motor debe encender o apagar usando bit "M10.1", que guarda el último estado del motor.<br>

<a href="imagenes/4-estrella_triangulo/video-mem-set-reset.mp4">Ver video demostración</a>
<br>


Esquema CADe SIMU de conexión PLC físico con Set y Reset

<br><br>
<img src="imagenes/6-mem-set-reset/diagrama_set_reset_mem_con_plc.jpg" alt="ladder_mem_set_reset" width="60%">
<br>

Rung 1 y 2: Decide si hacer SET o RESET.<br>
Rung 1: Flanco & (M_P = 0) entonces SET Motor.
Rung 2: Flanco & (M_P = 1) entonces SET Motor. <br>

Rung 3: Detectar motor encendido: Cuando MOTOR = 1 se ejecuta SET M_P, entonces M_P = 1 <br>
Rung 4: Detectar motor apagado: Cuando MOTOR = 0 se ejecuta RESET M_P, entonces M_P = 0 <br>

## Clase 7 - Temporizadores

TON: Time On Delay <br>

<img src="imagenes/7-timers/TON.jpg" alt="TON_diagram" width="60%">

<br>

TOF: Time Off Delay <br>

<img src="imagenes/7-timers/TOF.jpg" alt="TOF_diagram" width="60%">

<br>

TP: Time Pulse <br>

<img src="imagenes/7-timers/TP.jpg" alt="TP_diagram" width="60%">

<br>

En esta clase también se realiza ejercicio de montacargas en TIA Portal: <br>
El ejercicio consiste en que un motor sube y baja un montacarga entre 3 pisos (SS, PB, 1er piso) utilizando 3 sensores y 3 pulsadores
un sensor y un pulsador por cada piso.

<br>

## Clase 8 - Machine Expert Basic - Schneider

Utilizacion de Machine Expert - Basic (Schneider Electric) para programar y simular Ladder. En este caso ejercicio de semáforo con timers. <br>

<img src="imagenes/8-schneider/semaforo_con_enclav_ladder_schneider.jpg" alt="Simulacion ladder semaforo" width="60%">

Utilizacion de Veijeo para programar pantallas HMI (HMIGXU3512X 800x480) <br>

<img src="imagenes/8-schneider/hmi_sim_leds.jpg" alt="Simulacion LEDs HMI" width="60%">

<img src="imagenes/8-schneider/hmi_sim_semaforo.jpg" alt="Simulacion semaforo HMI" width="60%">

## Clase 9 - Contadores
Introducción a contadores en Schneider y Siemens (ascendentes, descendentes, ambos).<br>

<img src="imagenes/9-contadores/diagrama_contador_ctud.jpg" alt="Diagrama contadores CTUD" width="60%">

Aplicación en ejercicio de cintas transportadoras.<br>
<img src="imagenes/9-contadores/ladder_cintas_contadores.jpg" alt="Ladder Cintas transportadoras con Contadores" width="60%">

Cintas transportadoras con Veijeo<br>
<img src="imagenes/9-contadores/veijeo_cintas_transportadoras_contadores_mejorado.jpg" alt="Veijeo cintas transportadoras mejoradas" width="60%">

## Clase 10 - Variador de velocidad
Para sistemas trifásicos, mejora las condiciones de arranque.<br>
El variador utilizado es de marca Synamics G120. Consiste en 3 modulos: Potencia, Control y Operacion.<br>
Utiliza parametros para ser configurados.<br>
p700 = BORNES
p701 = CON/DES
p702 = SENTIDO GIRO
p703 = BIT0
p704 = BIT1
p705 = BIT2
p1000 = CONSIGUE VELOCIDAD
p1001 = VELOCIDAD FIJA 1
<br>
Combinando los BIT tenés 2^3 = 8 posibles velocidades.
<img src="imagenes/10-variador-velocidad/control_variador_velocidad.jpg" alt="Prueba variador velocidad" width="60%">

Secuencia temporizada para aumentar velocidad de variador:
<img src="imagenes/10-variador-velocidad/secuencia_variador_velocidad.jpg" alt="Equipos para secuencia variador velocidad" width="60%">

El programa de control activa salidas %Qx.x de forma progresiva hasta que los 3 bits estén activos para alcanzar máxima velocidad y detiene el motor.<br>
<img src="imagenes/10-variador-velocidad/programa_secuencia_variador_vel.jpg" alt="Programa Secuencia Variador Velocidad" width="60%">

## Clase 11 - HMI Siemens
Utilizamos Switch CSM1277 Simatic para tener conexión Ethernet en simultaneo con PLC S7-1200 y KTP600.<br>
<img src="imagenes/11-hmi-siemens/switch_siemens_csm1277_simatic.jpg" alt="Switch Ethernet CSM1277 Simatic" width="60%">

Configuración de pantalla HMI de 6 pulgadas KTP600 SIMATIC por comunicación Ethernet.<br>
<img src="imagenes/11-hmi-siemens/redes_hmi_siemens.jpg" alt="Conexion redes switch plc y hmi" width="60%">
<br>

Programa básico para activar salidas e indicarlas con un "led" (circulo) verde o rojo si está activada o no.<br>
<img src="imagenes/11-hmi-siemens/hmi-ktp600-prueba.jpg" alt="HMI KTP600 Prueba" width="60%">

