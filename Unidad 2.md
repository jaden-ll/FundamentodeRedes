

### Actividad 2.1
##### Red de Area personal (PAN)

conecta dispositivos que pertenecen a una sola persona y estan a una muy corta distancia entre si, normalmente unos pocos metros

tienen un alcance de hasta 10 metros, bajo consumo de energia y con frecuencia usa tecnologias inalambricas como bluetooth en lugar de cable

##### Red de area local (LAN)

conecta dispositivos dentro de un espacio fisico unico: una casa, una oficina, un salon de clases o un solo edificio

Es la red que una sola organizaciion controla y administra por completo; suele tener alta velocidad y bajo costo por su alcance limitado

##### Red inalambrica de area local (WLAN)
es una LAN que usa un espectro radioelectronico en lugar de cables para conectar dispositivos dentro del mismo espacio

El acceso se hace atraves de uno o mas puntos de acceso AP; a cambio de movilidiad, el medio es compartido y mas sensible a interferencia 

##### Wifi analyzer

es una CAN conecta varias LAN de distintos edificios que pertenecen a la misma organizacion y estan proximos entre si 

los edificios suelen enlazarse con fibra optica para soportar mayor distancia y trafico; toda la red sigue bajo una sola administracion

##### Red de area amplia (WAN)

conecta redes que estan geograficamente distantes, a veces en distintas ciudades, paises o continentes

ya no la administra una sola organizacion; suele depender de proveedores de telecomunicaciones y su costo, latencia son mayores que en una LAN 

comparacion por alcance de menor a mayor cobertura: PAN (una persona) - > LAN / WLAN ( un edificio) -> Campus Area Network (varios edificios de una organizacion) -> WAN (distintas ciudades o paises)

la pregunta que las distingue no es la tecnologia que usan, es quien la administra y que tan lejos llega: eso es lo que determina si es una red LAN, CAN o WAN.


#### Actividad 2.2

| Estándar (Nombre comercial) | Año  | Frecuencia          | Velocidad Máxima Teórica               | Definición y Avance Técnico Clave                                                                                                                                                                                                                                                                    |
| :-------------------------- | :--- | :------------------ | :------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **802.11b** (Wi-Fi 1)       | 1999 | 2.4 GHz             | 11 Mbps                                | Primer estándar de adopción masiva. Usa modulación DSSS. Ofrecía buen alcance, pero era extremadamente susceptible a interferencias (microondas, Bluetooth).                                                                                                                                         |
| **802.11a** (Wi-Fi 2)       | 1999 | 5 GHz               | 54 Mbps                                | Estándar simultáneo al "b". Introduce OFDM para lidiar mejor con el trayecto múltiple (multipath). Su uso en 5 GHz redujo las interferencias, pero sacrificó alcance y penetración de muros.                                                                                                         |
| **802.11g** (Wi-Fi 3)       | 2003 | 2.4 GHz             | 54 Mbps                                | Híbrido que lleva la modulación OFDM del "a" a la banda de 2.4 GHz del "b". Su principal valor fue lograr altas velocidades manteniendo el alcance de 2.4 GHz y la retrocompatibilidad con 802.11b.                                                                                                  |
| **802.11n** (Wi-Fi 4)       | 2009 | 2.4 y 5 GHz         | 600 Mbps                               | **Salto arquitectónico.** Introduce **MIMO** (Multiple Input, Multiple Output). Usa múltiples antenas para enviar/recibir flujos de datos espaciales simultáneos. Introduce el soporte formal de banda dual.                                                                                         |
| **802.11ac** (Wi-Fi 5)      | 2014 | 5 GHz (exclusivo)   | ~3.5 Gbps (Wave 1) / 6.9 Gbps (Wave 2) | Escala el rendimiento en 5 GHz aumentando el ancho de canal hasta 160 MHz. Introduce **MU-MIMO** (Multi-User MIMO) en el enlace descendente, permitiendo al AP transmitir a múltiples clientes al mismo tiempo, en lugar de uno por uno.                                                             |
| **802.11ax** (Wi-Fi 6 / 6E) | 2019 | 2.4, 5 y 6 GHz (6E) | 9.6 Gbps                               | **Cambio de enfoque:** prioriza eficiencia y latencia sobre velocidad bruta. Introduce **OFDMA** para dividir los canales en subportadoras (Resource Units) y servir a múltiples dispositivos en la misma transmisión (subiendo y bajando). Wi-Fi 6E (2020) expande el estándar a la banda de 6 GHz. |


* El **throughput real (TCP/IP)** que se ve en una prueba de rendimiento en la capa de aplicación será, en el mejor de los escenarios, entre el **40% y el 60%** de la velocidad teórica.
*
* Alcanzar las velocidades máximas de **n**, **ac** o **ax** requiere que el cliente también tenga múltiples antenas (3x3 o 4x4 MIMO), canales contiguos libres de interferencia y estar a corta distancia del punto de acceso. La mayoría de smartphones y laptops están limitados a hardware 2x2 MIMO.

##### Que es el internet?

son millones de redes LAN y WLAN conectadas entre si, ninguna empresa ni gobierno lo administra, cada red que la compone es administrada de manera independiente y se conecta a las demas por acuerdo mutuo 

##### Que es TCP/IP?
protocolo que dice como tienen que ir los datos 

##### Como se conectan las redes entre si?

a traves de proveedores de servicios de internet (ISP), organizados en niveles: los ISP locales se conectan a otros mas grandes, y estos entre si, hasta formar la red global

##### Que son los (IXP) ?

puntos de intercambio (IXP) sitios fisicos donde distintos ISP conectan su trafico directamente entre si, en lugar de inviarlo por una ruta mas larga. Reducen latencia y costo de transito.

##### Los IXP crean rutas mas cortas para el trafico del internet?
si, es una alternativa mas accesible al envio del trafico local de internet al extranjero, ofrecen ,as estabilidad, eficiencia y mejora la calidad, todos estos beneficios a un costo menor.

#### Que es el modelo TCP/IP

modelo de cuatro capas que describe como se comunican los dispositivos en una red social

nacio del proyecto ARPANET en los anos setenta, antes del modelo OSI, por eso es el modelo practico


#### El viaje de los datos:


```mermaid 
flowchart LR
    %% Nodos principales del flujo
    A["💻 **Dispositivo Final**<br><i>El Punto de Origen</i>"] --> B["🔌 **Red de Área Local (LAN)**<br><i>El Primer Salto</i>"]
    B --> C["🌐 **Proveedores de Servicios (ISP)**<br><i>De la Local a la Regional</i>"]
    C --> D["⚡ **Backbone Internacional**<br><i>La Autopista Global de Internet</i>"]
    D --> E["🖥️ **Procesamiento en Destino**<br><i>Respuesta del Servidor</i>"]
    
    %% Flujo Inverso
    E ==>|Flujo Inverso Jerárquico| A
```
