

Actividad 1.1 Glosario

**Capa física**

- Bit: la unidad de datos minima 0-1
- Señal: representacion de los datos enviados de un disp a otro
- Ancho de banda: capacidad de transferencia de datos
- Rendimiento (throughput):tasa de datos transferidos correctament
- Latencia: tiempo que tarda en transferir los datos
- Medio de transmisión: canal por donde viaja la informacion

**Cables y medios**

- Par trenzado (UTP / STP): cables con hilos de cobre entrelazados que disminuyen las interferencias, el UTP no tiene blindaje y el STP si tiene 
- Conector RJ-45: interfaz estandar de 8 pines se utiliza para los cables ethernet
- Cable directo y cable cruzado: el directo conecta dispositivos dif, el cruzado dispositivos iguales pc-pc
- Fibra óptica: medio de transmision que envia impulsos de luz a traves de vidrio
- Fibra monomodo y multimodo: monomodo: usa un solo haz de luz para largas distancias, multimodo: usa multiples haces para cortas distancias
- Interferencia electromagnética (EMI): distorsion de senal causada por campos externos
- Wi-Fi (IEEE 802.11): estandar de redes locales inalambricas (WLAN)
- Bandas de 2.4 GHz y 5 GHz: 2.4: ofrece mayor alcance pero poca velocidad, 5g: ofrece mucha velocidad pero poco alcance
- Bluetooth: protocolo de intercambio de datos mediante campos electromagneticos (PAN)

**Señalización**

- Codificación: proceso para convertir datos digitales en patrones de senales electricas
- Señalización: metodo fisico que se utiliza para representar los valores binarios en el medio de transmision
- Sincronización: es la alineacion del reloj entre el emisor y el receptor para interpretar los datos correctamente, inicio y fin de cada bit
- Código Manchester: es un metodo de codificacion donde cada bit tiene una transicion de voltaje a mitad del intervalo para mantener la sincronizacion

**Ethernet y LAN**

- Ethernet (IEEE 802.3): estandar para redes de cable LAN
- Tarjeta de red (NIC): hardware que permite la conexion al internet
- Switch: dispositivo de capa 2 que reenvia tramas exclusivamente al puerto del destino, utilizando direcciones MAC
- Hub: dispositivo de capa 1 obsoleto que retransmite todas las senales a los puertos de recepcion
- Tabla de direcciones MAC: registro en el switch que asocia direcciones MAC especificos con sus respectivos puertos fisicos
- Dúplex (half y full): half envia y recibe datos por turno, full envia y recibe datos simultaneamente
- Colisión: impacto producido entre dos dispositivos cuando comparten datos al mismo tiempo en un medio-duplex compartido

**Direccionamiento**

- Dirección MAC: identificador fisico de 48 bits
- OUI: primeros 24 bits de una direccion Mac que identifican al fabricante del dispositivo
- Hexadecimal: sistema numerico en base de 16 digitos (0-9, A-F) usado para representar direcciones MAC
- Unicast: trafico enviado de un unico emisor a un unico destinatario 
- Multicast: trafico enviado de un unico emisor a un grupo especifico de destinatarios
- Broadcast: trafico enviado de un emisor a todos los dispositivos de la red local

**Enlace de datos**

- Trama (frame): unidad de datos de protocolos (PDU) de la capa 2 que empaqueta los paquetes de red con encabezado y trailer.
- Encabezado y tráiler: controladores anadidos al inicio y fin de datos; contienen direcciones MAC e informcion de control de errores
- FCS / CRC: secuencia de verificacion en el trailer (FCS) que utiliza un calculo matematico (CRC) para detectar errores en la trama 
- Subcapa LLC: subcapa inferior de capa 2 que gestiona la comunicacion con la capa 3 e identifica el protocola de red
- Subcapa MAC: subcapa inferior de capa 2 que controla el acceso al medio fisico y el direccionamiento del hardware
- CSMA/CD: protocolo de acceso al medio para redess cableadas half-duplex que detecta colisiones y retransmisiones
- CSMA/CA: protocolo de acceso al medio para redes inalámbricas que evita colisiones reservando el canal antes de transmitir.

### Actividad 3.1

![[CableLAN.pdf]]


#### Principios:

Componentes: 

Parametros: su desempeno se mide con tres parametros, ancho de banda(capacidad maxima), rendimiento(lo que realmente se transfiere) y latencia(el retardo en llegar)


Porque los puntos de intercambio reducen la latencia?

Tipos de cables:

Cobre: el cable de par trenzado (UTP) transmite senales electricas con conector RJ-45, alcanza hasat 100 metros. y es el mas usado en latam

##### UTP: 
Los 8 hilos del UTP forman 4 pares trenzados.
Cada par envía la señal con polaridad opuesta en sus dos hilos; la interferencia afecta a ambos por igual y el receptor la cancela al comparar los dos.
Cada par tiene un trenzado distinto para reducir la diafonía entre pares vecinos.



##### Fibra optica:
 transmite pulsos de luz; llega a mayores distancias y es inmune a la interferencia electromagnetica, pero es mas costosa y delicada de instalar


##### Medios inalambricos: 
transmiten por ondas de radio(WIFI, Bluetooth, celular); dan movilidad, pero el medio es compartido, sufre interferencias y requiere medidas de seguridad

##### La capa fisica: senales de comunicacion

una senal es una variacion de una propiedad fisica que representa bits: cambios de voltaje en cobre, pulsos de luz en fibra u ondas de radio en el aire

##### Senalizacion y codificacion fisica

La codificacion convierte los bits en un patron predefinido que facilita la sincronia y la deteccion de errores; la senalizacion define como se representa ese patron en el medio.

##### Medios fisicos; conexion de la comunicacion

Un dispositivo se conecta mediante su tarjeta de red (NIC), un puerto, un conector y el medio; la NIC convierte los bits en la senal que el medio puede representar y transportar.

##### Ethernet capa 1 y 2 
es el estandar dominante en LAN y trabaja en dos capas; capa 1, define medios y senalizacion y en la capa 2 define las tramas y las direcciones MAC.
##### ARP: direccion ip a direccion de MAC

el protocolo ARP permite descrubir la direccion MAC de un dispositivo a partir de su direccion IP, envia una peticion por broadcast ; solo el dueno de esa IP respode por UNICAST y el resultado se guarda en la tabla ARP

##### Envenenamiento ARP 

ARP no verifica quien responde; un atacante envia respuestas ARP falsas para que otros equipos asocien su MAC con la IP de otro dispositivo, por ejemplo la del router, y asi intercepta el trafico (ataque de intermediario)

se mitiga con inspeccion dinamica ARP (DAI) en el switch con entradas ARP estaticas en los equipos criticos.

-----------------------------------------------------------
Nombre: Braulio Ledesma

Campo 1
Dato de ejemplo: 10101010 10101010 10101010 10101010 10101010 10101010 10101010 10101011 (8 bytes)
Nombre del campo: preambulo y delimitador de inicio de trama
Para qué sirve: sirve para sincronizar el reloj del receptor con el emisor mediante esa secuencia de bits.

Campo 2
Dato de ejemplo: FFFF.FFFF.FFFF (6 bytes)
Nombre del campo: Direcciones MAC de destino
Para qué sirve: Sirve para especificar la red, siendo una dirección de difusión por lo que reciben todos los dispositivos de esa red.

Campo 3
Dato de ejemplo: 0001.4321.ABCD (6 bytes)
Nombre del campo: Direcciones MAC de origen
Para qué sirve: identifica el origen unico de la tarjeta física de red del dispositivo emisor.

Campo 4
Dato de ejemplo: 0x0806 (2 bytes)
Nombre del campo: Tipo de protocolo
Para qué sirve: Indica la capa de red del receptor y dice que protocolo encapsula la carga util, dando el 0x0806 identifican específicamente al protocolo ARP.

Campo 5
Dato de ejemplo: ¿Quién tiene la IP 192.168.1.2? Responde a 192.168.1.1 (entre 46 y 1500 bytes)
Nombre del campo: Carga util (payload)
Para qué sirve: transporta la información util entregada por las capas superiores, puede ser un mensaje de solicitud ARP que va mareando una IP de destino corresponiente a su MAC, posee un tamaño mínimo de rellenado (46 bytes).

Campo 6
Dato de ejemplo: 0x3A7F91C2 (4 bytes)
Nombre del campo: Secuencia de verificación de trama
Para qué sirve: permite que al receptor detecte errores de transmisión a nivel físico, aplicando un algoritmo de redundancia cíclica (CRC-32) sobre la misma trama. Si el calculo no coincide con el valor, la trama se descarta por corrupción de datos.
#### ACTIVIDAD 3.3

|**¿Qué cambia?**|**Switch Capa 2**|**Switch Capa 3**|
|---|---|---|
|**¿En qué se fija?**|Solo en la dirección MAC (física).|En la MAC y en la IP (lógica).|
|**¿Manda datos entre redes/VLANs?**|No. Ocupa un router a fuerza para eso.|Sí, lo hace él solo directamente.|
|**¿Para qué sirve?**|Conectar PCs, impresoras o cámaras en la misma red.|Conectar varios switches, segmentar la red y manejar tráfico pesado.|
|**¿Dónde se pone?**|En el borde (donde conectas los cables de la oficina o salón).|En el centro o cuarto principal de servidores.|

---------------------------------------------------------------
##### Manual - Fibra optica

