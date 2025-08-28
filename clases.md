# Clase 2. Viernes 22/08

https://www.youtube.com/watch?v=SoocbjAmnnI&list=PLgjTEtKoGsVoxJIuvWQH-HLS33xVZTQj_&index=1&t=1895s

## Introduccion a las telecomunicaciones y redes.

Las telecomunicaciones han sufridos grandes cambios a partir del esquema telefónico (capacidad de digitalización de la voz). 

```
64kb/s se lo conoce como la trama o canal de voz sin compresion (dato a chequear)
```

La tecnologia y las telecomunicaciones han sido el motor de la economía mundial desde fines de los 90 hasta nuestros dias. Han cambiado la forma de hacer negocios.

Los cables trasatlanticos permitieron las priemras comunicaciones entre continentes.

### ¿Como nos conectamos a internet?

A traves de una **red de acceso**! 

Nosotros tenemos un router (dispositivo de capa 3), que nos permite conectarnos hacia otro router, que está en el **borde de la red de transporte** (**Hostings center**).

```
🔹 1. Red de acceso

Es la primera parte del camino que hace tu conexión a Internet.

Tu casa/empresa: tenés un router (CPE = Customer Premises Equipment), que suele ser el módem-router que te da tu ISP.

Ese router se conecta con un router de borde del proveedor, que ya pertenece a la red de transporte.
👉 O sea, la red de acceso es el “puente” entre vos (usuario final) y la infraestructura del proveedor.

🔹 2. Red de transporte

Una vez que salís de la red de acceso, entrás en la red de transporte del ISP.

Ahí está lo que muestra el diagrama como IP/MPLS Backbone.

El backbone es la “columna vertebral” de la red: routers muy potentes interconectados con fibra óptica de alta capacidad.

MPLS (Multiprotocol Label Switching): es una tecnología que mejora el enrutamiento clásico IP, permitiendo crear “circuitos virtuales” para dar calidad de servicio (QoS), priorizar tráfico (ej: voz sobre datos), o armar VPNs de manera eficiente.

🔹 3. ¿Qué representa la diapositiva?

A la izquierda ves distintos tipos de acceso posibles: IP nativo, Frame Relay, ATM, IPSec, dial-up… (algunos son más históricos que actuales).

Todo eso termina en el backbone IP/MPLS del operador.

Desde ese backbone se puede:

Llegar a Internet.

Conectarse con otras sucursales (VPN).

Acceder a servicios de hosting.

O incluso integrar la red de voz clásica (PSTN).

🔹 4. Analogía

Imaginá la red como un sistema de rutas:

Red de acceso: es tu calle de barrio → conecta tu casa con la avenida principal.

Red de transporte (backbone): son las autopistas → conectan ciudades y países.

Routers de borde: son los peajes/entradas → controlan quién entra y cómo circula el tráfico.

👉 En conclusión: lo que dijo tu profesor encaja perfecto con la diapositiva. Vos con tu router (CPE) te conectás a la red de acceso, y de ahí a un router de borde que te mete en la red de transporte (backbone IP/MPLS).
```

---
 
Por ejemplo: 

Nosotros tenemos un acceso telecom. Telecom usa las redes de acceso (una fibra que llega al hogar, FTTH; un servicio de cable modem, un servicio de ADSL utilizando el par de cobre). Una vez que ese paquete IP llega al borde de la red, la red tiene la suficiente inteligencia para ir routeando ese paquete a su destino. 

Si estoy buscando una pagina web, voy a estar buscando una direccion ip en algun servidor en donde la red que hace el routeo de ese paquete, conoce la direccion; conoce el camino a ese paquete.

```
🔹 1. Red de acceso (lo que tenés en tu casa)

FTTH (Fiber To The Home): la fibra óptica llega directamente a tu casa.

Cablemódem: usa la red de TV por cable para darte Internet.

ADSL: usa el par de cobre telefónico tradicional.

Todos estos son métodos de acceso, diferentes “caminos” físicos por los que tu paquete IP llega al proveedor (Telecom, en tu ejemplo).

🔹 2. Llegada al borde de la red

Una vez que el paquete IP entra en la red de Telecom, llega al router de borde del ISP.

Ese router pertenece a la red de transporte (backbone IP/MPLS), que tiene inteligencia de enrutamiento (protocolos como OSPF, BGP, MPLS).

👉 Ahí se decide cuál es la mejor ruta para enviar tu paquete hacia su destino.

🔹 3. Ejemplo: buscar una página web

Vos pedís www.google.com.

Tu router local envía el paquete IP hacia el ISP (red de acceso).

El backbone de Telecom consulta sus tablas de enrutamiento y sabe cómo llegar a la IP de Google (gracias a BGP y otras rutas aprendidas).

El paquete viaja por distintas redes interconectadas hasta llegar al servidor de Google, y la respuesta vuelve por el mismo camino o uno distinto.

📌 En palabras simples:

La red de acceso es “el camino para salir de tu casa y llegar a la autopista”.

La red de transporte (el backbone) es “la autopista inteligente” que sabe cómo llegar a cualquier destino (otra red, otro país, otro servidor).
```

---

- **Pudding**: La "interconexión entre backbones" se refiere a cómo las principales redes troncales de datos se conectan entre sí para formar una infraestructura de red más grande, como Internet, utilizando puntos de intercambio de datos (Nodos) y cables de alta capacidad para transportar el tráfico de redes más pequeñas.

Este es el concepto subyacente de las redes WAN (Wide Area Network) en cualquier comunicación de internet de hoy dia (ya sea de datos, video o voz). 

```
🔹 1. Pudding / Interconexión entre backbones

Cada ISP grande (Telecom, Claro, Movistar, etc.) tiene su propio backbone (su red troncal IP/MPLS de alta capacidad).

Pero Internet no es una sola red gigante, sino la interconexión de muchos backbones.

Esa interconexión se hace en:

IXPs (Internet Exchange Points): nodos donde diferentes ISPs intercambian tráfico. Ejemplo en Argentina: CABASE.

Cables submarinos y enlaces de alta capacidad: conectan continentes y grandes regiones.

👉 Este “tejido” de backbones interconectados es lo que hace posible que un cliente de Telecom pueda acceder a un servidor que está, por ejemplo, en AWS (Amazon) o en Google, aunque estén en otra red/otro país.

Esto es la esencia de una WAN (Wide Area Network) global.
```

- **LAN**: Local area network. 

Antes, todos los servicios eran separados. Si querias pasar voz, contratabas un servicio de voz. Si querias video, un servicio de video, y asi con cada dato que se deseaba pasar. 

La evolución, a nivel de redes, se fue dando a traves de la integración (Dato y voz consolidados sobre una red IP). Todo tipo de trafico, se da por una unica red: IP (Internet Protocol, capa 3). 

```
🔹 2. LAN (Local Area Network)

Antes, cada servicio iba por su propia red:

Telefonía fija → red PSTN.

Televisión → red de cable o satélite.

Datos (computadoras) → otra red (X.25, Frame Relay, etc.).

Con el tiempo se dio la integración:

Hoy todo viaja sobre IP (capa 3).

Voz → VoIP (ejemplo: WhatsApp, Zoom).

Video → streaming IP (YouTube, Netflix).

Datos → web, apps, archivos.

👉 En una LAN (hogar o empresa), todo esto ya está integrado: tu PC, tu celular, tu SmartTV, tu consola, todo habla IP sobre Ethernet o WiFi.

📌 En resumen:

WAN/backbones: interconectan las grandes redes a nivel global, haciendo posible Internet.

LAN: es la red local (oficina, casa, facultad). Hoy todo está consolidado en IP, lo que simplifica y unifica servicios.
```

### Tipos de VPN.

- [Sucursal] VPN para Intranet: Conexiones de bajo costo (túneles), provista de nutridos servicios (Menores costos y nuevos servicios).
- [Partner de negocios] VPN para Extranets: Extiende la WAN a los partners. Nuevos modelos de negocios
- [Usuario movil] VPN de Acceso Remoto: Túneles encriptados, escalables, sobre una red pública. Menores costos y nuevos servicios.

```
🔹 ¿Qué es una VPN?

Una Virtual Private Network (VPN) es básicamente un “túnel lógico y seguro” que viaja sobre una red pública (Internet).
Sirve para extender redes privadas de manera segura y de bajo costo.

👉 En lugar de alquilar líneas privadas carísimas para conectar sucursales, se usan túneles encriptados por Internet.

🔹 Tipos que aparecen en la diapositiva:

VPN para Intranet (empresa interna)

Conecta sucursales de una misma empresa con la casa central.

Ejemplo: un banco conecta sus sucursales a la red central usando túneles VPN en lugar de alquilar circuitos dedicados.

Ventaja: menor costo, mismo servicio.

VPN para Extranet (con socios/partners)

Extiende la red de la empresa a partners de negocios (proveedores, distribuidores, clientes grandes).

Ejemplo: un supermercado conecta a sus proveedores para compartir inventario en tiempo real.

Ventaja: habilita nuevos modelos de negocio (colaboración más directa).

VPN de Acceso Remoto (usuarios individuales)

Permite que un empleado desde su casa, o viajando (usuario móvil), se conecte a la red corporativa.

Se hace con un cliente VPN en la notebook o celular.

Ejemplo: vos trabajando desde tu casa te conectás a la red de la UBA o de una empresa como si estuvieras dentro del campus/oficina.

Ventaja: flexibilidad + seguridad (túneles encriptados).

🔹 Otros conceptos de la diapositiva

POP (Point of Presence): punto de acceso a la red VPN del proveedor. Es donde te conectás a entrar al túnel seguro.

Casa Central, Sucursal, Partner, Trabajo en casa, Usuario móvil: distintos casos de uso conectados al “mismo núcleo” (la nube de VPN).

📌 Resumen rápido:

Intranet VPN: conecta sucursales → casa central.

Extranet VPN: conecta empresa → partners.

Acceso Remoto VPN: conecta empleados remotos → empresa.
```

"Si yo quiero armar una red de datos entre dos locaciones cualquiera, puedo utilizar la red IP (red publica de capa 3 de datos) pero haciendo routeo con direcciones privadas, permitiendome generar esa red de datos privada sobre una red publica que tiene mucha capacidad de transporte". 

No solamente a nivel local, tambien se puede a nivel mundial. Dada con -> **Cables submarinos**.


- VPN: La IP es una dirección **PUBLICA**. Cada proovedor de servicio cuando conecta a un usuario, le entrega una dirección publica. Vos podes montar una red privada dentro de esa red publica ip con un direccionamiento privado(tabla de routeo con direcciones privadas protegida por firewalls, inutilizadas. Tuneles que se generan arriba de la red publica), que solamente lo ve el origen y el destino. 

### Concepto de RED.

#### Ej: Servicio de acceso a internet.

- Las redes se pueden separar en dos tipos: 
    - Redes de acceso: La que llega al domicilio del cliente (empresa o usuario particular)
    - Redes de transporte

```
toda red se puede pensar en esas dos partes.

🔹 1. Red de acceso

Es la que conecta a los clientes finales (usuarios residenciales o empresas) con la red del proveedor.

Ejemplos:

ADSL → sobre par de cobre telefónico.

Cablemódem → sobre coaxial de TV.

FTTH → fibra óptica hasta el hogar.

En empresas → también pueden usar líneas dedicadas, MetroLAN, SDH, ATM (que no se comparten con otros).

👉 Es como la “última milla” que une tu casa/oficina con la autopista de la red.

🔹 2. Red de transporte

Una vez que el cliente está conectado, sus datos entran a la red troncal del ISP.

Está formada por enlaces de alta capacidad (fibra óptica, cables submarinos, radioenlaces) y routers de backbone.

Función: mover grandes volúmenes de tráfico entre ciudades, países, continentes.

👉 Es la “autopista central” que conecta todos los barrios y ciudades.

🔹 3. Lo que muestra la diapositiva

Contenidos (ej: servidores de Google, Netflix, UBA, etc.) → también se conectan primero a una red de acceso (con enlaces dedicados de alta capacidad).

Clientes (vos en tu casa, o una empresa) → igual, se conectan por su red de acceso (ADSL, fibra, etc.).

Una vez dentro, todo se mueve por la red de transporte hasta encontrarse cliente ↔ servidor.

📌 Resumiendo:

Red de acceso = conecta puntualmente usuarios/servidores al ISP.

Red de transporte = mueve los datos a gran escala dentro y entre ISPs.
```

"La red LAN es la que se utiliza en un mismo edificio (Local Area Network). Son los cables UTP que conecta cualquier PC con el cable de red. Ese cable transporta un protocolo ETHERNET. Eso es una red local.
Las redes que salen de los edificios, son redes WAN (WIDE AREA NETWORK), donde la conexion de datos se realiza en una zona geografica amplia."

---

Las redes WAN - WIDE AREA NETWORK - (Red de área amplia) son un tipo de red que permite la
conexión de dispositivos en una zona geográfica extensa, incluso a nivel global utilizando FO
submarina.
Su función principal es la interconexión de dispositivos y redes de distintas ubicaciones geográficas,
permitiendo la transferencia de datos, voz y video, tal como explicamos anteriormente.
A diferencia de las redes LAN, que cubren un área geográfica reducida, las redes WAN utilizan
tecnologías de transmisión de datos que les permiten abarcar grandes distancias.

---

- Los componentes de infraestructura de red son los siguientes:
    - **Redes de transporte**: Las redes de transporte son las conexiones físicas que se utilizan para conectar los dispositivos en la red WAN. Estas redes pueden incluir líneas de teléfono, cables de fibra óptica y enlaces por satélite.
    - **Redes de Acceso**: El acceso a la red WAN puede ser a través de una conexión de línea dedicada o una conexión a través de Internet. Las conexiones de línea dedicada son más seguras y confiables, ya que se utilizan líneas dedicadas para conectar los dispositivos. Las conexiones a través de Internet son menos seguras y confiables, ya que se utilizan las mismas líneas de Internet que se utilizan para el tráfico de Internet público. Por supuesto dependerá del tipo de servicio, la red de acceso a utilizarse. Para conexiones domiciliarias utilizaremos soluciones de ADSL, Cablemodem o FTTH. Para soluciones corporativas se pueden utilizar líneas dedicadas bajo diferentes protocolos, TDM, ATM, Frame Relay, etc., o también a través de redes públicas TCP/IP con direccionamiento privado (VPN IP).

### ADSL

![ADSL](img/ADSL.png)

```
🔹 1. Línea telefónica tradicional

El par de cobre telefónico se usaba sólo para voz.

La voz humana útil ocupa entre 300 Hz y 3400 Hz (por eso ves en la diapositiva el rango 0,3 – 3,4 kHz).

Eso es lo que usan los teléfonos convencionales de la red PSTN.

🔹 2. ¿Qué descubrieron con ADSL?

Ese mismo cable de cobre puede transportar frecuencias mucho más altas que las usadas para voz.

Entonces:

La parte baja del espectro (0,3 – 3,4 kHz) → reservada para voz.

La parte alta (desde 26 kHz hasta ~1,1 MHz) → usada para datos digitales (Internet).

👉 Así podías hablar por teléfono y navegar Internet al mismo tiempo sin interferencias.

🔹 3. Cómo se hace la separación

Se usan filtros (splitters) para dividir la señal:

El teléfono toma la parte de voz.

El módem ADSL toma la parte de datos.

En la central telefónica del ISP también hay filtros/módems para separar lo que va a la red de voz y lo que va a la red de datos (Internet).

🔹 4. Técnicas usadas

Modulación multicanal (DMT – Discrete MultiTone): divide el rango de frecuencias en muchos canales pequeños (subportadoras).

DSP (Digital Signal Processor): chips que permiten comprimir, modular y manejar los datos eficientemente.

📌 En resumen:

Antes: el cobre solo llevaba voz (0,3 – 3,4 kHz).

Con ADSL: se aprovecha el rango de frecuencias altas (26 kHz – 1,104 MHz) para enviar datos → Internet.

Así se multiplicó la capacidad sin cambiar el cableado físico.
```

### CABLEMODEM

![CABLEMODEM](img/CABLEMODEM.png)

"En el cablemodem esta el usuario conectado a un router, donde ese router está conectado con un cable rg45 (cable ethernet) al cable modem de telecentro(por ejemplo). Yo entro con un cable ethernet y salgo con un cable coaxial (se usa para video, pero al igual que la tecnologia ADSL con el par de cobre, le saca ancho de banda al video para poder mandar datos). Es una red activa. En un edificio cuando nos quedamos sin luz, el amplificador de la azotea que está alimentado, pierde energia y se cae el servicio. En cambio en un ADSL si yo tengo un generador en mi casa y le doy energia al modem, el servicio seguiria activo por lo que tendria internet pero no luz."

```
🔹 1. Cómo funciona el cablemódem

Tu PC/Router hogareño se conecta al cablemódem por Ethernet (RJ-45).

El cablemódem se conecta al proveedor por coaxial (el mismo cable que se usa para TV por cable).

Ese coaxial va hasta un nodo del proveedor de cable, donde hay un dispositivo llamado CMTS (Cable Modem Termination System) que concentra a muchos usuarios y conecta con Internet.

👉 Es parecido a ADSL: aprovechar un medio existente (la red de TV por cable) para transportar datos digitales además de video.

🔹 2. Reparto del ancho de banda

El coaxial originalmente se usaba solo para video analógico/digital (canales de TV).

Con cablemódem, se “roban” parte de esas frecuencias para datos.

Así, por el mismo cable coaxial puede viajar TV + Internet.

🔹 3. Diferencia con ADSL (que dijo tu profe)

ADSL (sobre par de cobre):

La red de acceso es pasiva: no hay elementos que requieran energía en el camino hasta la central.

Si en tu casa tenés luz (ej: con un generador), el servicio sigue funcionando aunque el barrio esté sin electricidad.

Cablemódem (sobre coaxial):

La red es activa: el coaxial necesita amplificadores intermedios (en la azotea del edificio, postes, gabinetes de barrio).

Si se corta la luz en esos equipos y no tienen backup, el servicio se cae aunque vos tengas energía en tu casa.

🔹 4. Resumen visual de la diapositiva

Usuario → Router → Cablemódem → (Ethernet ↔ coaxial) → Proveedor de cable → CMTS → Internet.

Todo el tráfico de muchos usuarios se concentra en el CMTS, que es la “puerta de entrada” a Internet para esa red de acceso.

📌 En síntesis:

Cablemódem = Internet por coaxial, compartiendo espectro con TV.

Ventaja: mucho más ancho de banda que el ADSL clásico.

Desventaja: red activa → si un amplificador del edificio/barrio se queda sin energía, todos los usuarios de ese nodo pierden conexión.
```

### RED TRANSPORTE

![REDTRANSPORTE](img/REDTRANSPORTE.png)

Red inalambrica, la transmicion de los datos van por el aire.

Red de Transporte Inalámbrica con acceso RAN (Radio Access Network).

```
🔹 1. Acceso (RAN = Radio Access Network)

Los celulares no se conectan por cable como en ADSL o cablemódem, sino por aire (radiofrecuencia).

El acceso está dado por las antenas 5G → llamadas gNB (next generation Node B).

Cada gNB cubre un área (celda), y tus datos llegan primero a esa antena.

👉 Esto es la red de acceso inalámbrica (5G RAN).

🔹 2. Transporte (Backhaul)

La antena gNB necesita mandar esos datos al resto de la red.

Lo hace a través del backhaul, que puede ser:

Fibra óptica (lo más común).

Radioenlaces de microondas (cuando no se puede tirar fibra).

Este backhaul lleva la info desde la antena al Core Network.

👉 Esto es la red de transporte: mover la info de todas las antenas hacia el corazón de la red.

🔹 3. Core Network (núcleo de la red 5G)

Ahí están las funciones inteligentes:

Autenticación del usuario (SIM, identidad).

Asignación de direcciones IP.

Conexión hacia Internet o servicios internos del operador.

👉 Es como el “cerebro” que une las antenas con Internet.

🔹 4. Internet

Una vez que el paquete pasó por el core, se conecta a la red pública (Internet), igual que en ADSL o cablemódem.

📌 Resumen de la diapositiva:

5G RAN: acceso radio (celular ↔ antena).

5G Backhaul: transporte de la antena al core.

5G Core Network: núcleo de la red del operador.

Internet: salida al mundo.

👉 La frase que anotaste “Red inalámbrica, la transmisión de los datos van por el aire” aplica al acceso (RAN).
Pero ojo: el transporte (backhaul) casi siempre es fibra óptica o radioenlace, no va por el aire como el acceso entre celular y antena.
```
