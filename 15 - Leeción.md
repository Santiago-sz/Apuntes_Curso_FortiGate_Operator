# Configuring FotiLink
![[Pasted image 20260313155532.png]]

## What is FortiLink? // ¿Qué es FortiLink?

**FortiLink is a proprietary Fortinet protocol that allows administrators to manage FortiSwitches directly through the FortiGate interface without requiring an additional license.** // FortiLink es un protocolo propietario de Fortinet que permite a los administradores gestionar los FortiSwitches directamente a través de la interfaz del FortiGate sin necesidad de una licencia adicional.

**FortiLink simplifies network management by centralizing control on FortiGate for both security and switching.** // FortiLink simplifica la gestión de la red al centralizar el control en el FortiGate, tanto para la seguridad como para el switching.

**This enables LAN devices to become part of the security infrastructure, effectively enhancing the Fortinet Security Fabric.** // Esto permite que los dispositivos de la LAN pasen a formar parte de la infraestructura de seguridad, mejorando eficazmente el "Security Fabric" de Fortinet.

**Once implemented, you can configure all the desired switch settings on FortiGate and have them automatically sent to the FortiSwitches that it manages.** // Una vez implementado, puedes configurar todos los ajustes deseados del switch en el FortiGate y hacer que se envíen automáticamente a los FortiSwitches que este gestiona.

**The number of FortiSwitch units supported depends on the FortiGate model, ranging from 8 on the lower end to 300 on the higher end.** // El número de unidades FortiSwitch admitidas depende del modelo de FortiGate, variando desde 8 en la gama baja hasta 300 en la gama alta.

### Información Adicional y Análisis de la Imagen

- **Centralized Management:** In the image, the dashed line around the FortiGate and FortiLink icons symbolizes that the FortiGate acts as the "brain." You don't need to log in to each switch individually; you do everything from the FortiGate's GUI. // Gestión centralizada: En la imagen, la línea discontinua alrededor de los iconos de FortiGate y FortiLink simboliza que el FortiGate actúa como el "cerebro". No necesitas iniciar sesión en cada switch individualmente; haces todo desde la interfaz gráfica (GUI) del FortiGate.
    
- **Security Fabric Integration:** By using FortiLink, your switch ports become "secure ports." You can apply security policies, VLANs, and even quarantine infected devices directly at the switch port level from the firewall. // Integración con el Security Fabric: Al usar FortiLink, los puertos de tus switches se convierten en "puertos seguros". Puedes aplicar políticas de seguridad, VLANs e incluso poner en cuarentena dispositivos infectados directamente en el puerto del switch desde el firewall.
    
- **CAPWAP Protocol:** Under the hood, FortiLink often uses a modified version of the CAPWAP protocol (the same one used for Access Points) to communicate between the FortiGate and the switches. // Protocolo CAPWAP: Internamente, FortiLink suele utilizar una versión modificada del protocolo CAPWAP (el mismo que se usa para los Access Points) para comunicarse entre el FortiGate y los switches.
    
- **Scalability:** As the video mentions, the limit of switches depends on the hardware. For example, a FortiGate 60F (small office) will support fewer switches than a 1000F (data center). // Escalabilidad: Como menciona el video, el límite de switches depende del hardware. Por ejemplo, un FortiGate 60F (oficina pequeña) soportará menos switches que un 1000F (centro de datos).


![[Pasted image 20260313155724.png]]

## Why Use FortiLink? // ¿Por qué usar FortiLink?

**FortiLink provides several key benefits, including: centralized management, simplified deployment, enhanced security, and scalability.** // FortiLink proporciona varios beneficios clave, que incluyen: gestión centralizada, implementación simplificada, seguridad mejorada y escalabilidad.

### Desglose de beneficios (según la imagen):

- **Centralized Management** // Gestión Centralizada: **All switch configurations and monitoring are done from a single interface: the FortiGate.** // Todas las configuraciones y el monitoreo de los switches se realizan desde una única interfaz: el FortiGate.
    
- **Simplified Deployment** // Implementación Simplificada: **New FortiSwitches are automatically discovered and provisioned when connected to a FortiLink-enabled port.** // Los nuevos FortiSwitches se descubren y aprovisionan automáticamente cuando se conectan a un puerto habilitado para FortiLink.
    
- **Enhanced Security** // Seguridad Mejorada: **Security policies can be extended down to the individual switch port, allowing features like quarantine or VLAN assignment based on device identity.** // Las políticas de seguridad pueden extenderse hasta el puerto individual del switch, permitiendo funciones como la cuarentena o la asignación de VLAN basada en la identidad del dispositivo.
    
- **Scalability** // Escalabilidad: **Easily add more switches to the network as needed, with the FortiGate managing the entire stack or fabric.** // Agregue fácilmente más switches a la red según sea necesario, con el FortiGate gestionando todo el stack o fabric.

### Información Adicional y Análisis de la Imagen

- **Central Icon (Link):** The red and grey link icon in the middle represents the logical connection between the "brain" (FortiGate) and the "muscles" (FortiSwitches). // Icono Central (Enlace): El icono del enlace en rojo y gris en el medio representa la conexión lógica entre el "cerebro" (FortiGate) y los "músculos" (FortiSwitches).
    
- **The "Single Pane of Glass":** Fortinet uses this term often to describe **Centralized Management**. It means you can see your entire network (Firewall, Switches, APs) from one window. // El "panel de control único" (Single Pane of Glass): Fortinet usa este término a menudo para describir la **Gestión Centralizada**. Significa que puedes ver toda tu red (Firewall, Switches, APs) desde una sola ventana.
    
- **Security Fabric:** By using FortiLink, the switches are no longer "dumb" devices; they become an extension of the firewall's security. If a virus is detected on a PC, the FortiGate can tell the FortiSwitch to shut down that specific port automatically. // Security Fabric: Al usar FortiLink, los switches dejan de ser dispositivos "tontos"; se convierten en una extensión de la seguridad del firewall. Si se detecta un virus en una PC, el FortiGate puede ordenarle al FortiSwitch que cierre ese puerto específico automáticamente.
    
- **Scalability Limit:** Remember that while FortiLink is scalable, each FortiGate model has a maximum number of FortiSwitches it can manage (e.g., a FortiGate 40F can manage fewer switches than a 200F). // Límite de Escalabilidad: Recuerda que, aunque FortiLink es escalable, cada modelo de FortiGate tiene un número máximo de FortiSwitches que puede gestionar (por ejemplo, un FortiGate 40F puede gestionar menos switches que un 200F).

![[Pasted image 20260313160047.png]]

## How Does FortiLink Work? // ¿Cómo funciona FortiLink?

**FortiGate uses several management protocols to control FortiSwitch.** // FortiGate utiliza varios protocolos de gestión para controlar el FortiSwitch.

### Protocolos Principales

- **FortiLink:**
    
    - **Default FortiSwitch discovery method** // Método de descubrimiento de FortiSwitch por defecto.
        
    - **Used for heartbeats between FortiGate and FortiSwitch** // Utilizado para los "heartbeats" (latidos de salud) entre FortiGate y FortiSwitch.
        
    - **Discovery frames include the switches’ serial numbers and port information** // Las tramas de descubrimiento incluyen los números de serie de los switches e información de los puertos.
        
- **Link Layer Discovery Protocol (LLDP):**
    
    - **Alternative method for FortiSwitch discovery** // Método alternativo para el descubrimiento de FortiSwitch.
        
    - **Automatically enables links in a switch stack as trunks** // Habilita automáticamente los enlaces en un stack de switches como "trunks" (troncales).
        
- **Control and Provisioning of Wireless Access Points (CAPWAP):**
    
    - **Switch authentication and authorization** // Autenticación y autorización de switches.
        
    - **Also used for heartbeats** // También se utiliza para los "heartbeats".
        
    - **Alternative (legacy) firmware upgrade method** // Método alternativo (heredado) para la actualización de firmware.
        
    - **Sends FortiSwitch logs to FortiGate** // Envía los logs (registros) del FortiSwitch al FortiGate.

### Protocolos de Soporte

- **HTTPS:**
    
    - **Default protocol for sending firmware images during upgrades** // Protocolo por defecto para enviar imágenes de firmware durante las actualizaciones.
        
    - **REST API** // Interfaz de programación REST.
        
- **Others like DHCP, DNS, NTP, and SSH:**
    
    - **Assist with management tasks.** // Asisten en las tareas de gestión.

### Información Adicional y Análisis de las Imágenes

- **CAPWAP for Switches:** It’s interesting that Fortinet adapted **CAPWAP** (originally for WiFi) to create a secure tunnel between the FortiGate and the Switch. This tunnel is where the management data travels securely. // CAPWAP para Switches: Es interesante que Fortinet adaptara **CAPWAP** (originalmente para WiFi) para crear un túnel seguro entre el FortiGate y el Switch. Por este túnel viajan los datos de gestión de forma segura.
    
- **LLDP and Trunks:** When you connect multiple switches together, **LLDP** is what allows them to say "Hey, I'm a FortiSwitch too!" and automatically form a trunk (Aggregated Link) without manual configuration. // LLDP y Trunks: Cuando conectas varios switches entre sí, **LLDP** es lo que les permite decir "¡Oye, yo también soy un FortiSwitch!" y formar automáticamente un trunk (enlace agregado) sin configuración manual.
    
- **Firmware via HTTPS:** Modern FortiOS uses **HTTPS** for firmware upgrades because it's faster and more reliable than the older CAPWAP-based method. // Firmware por HTTPS: El FortiOS moderno utiliza **HTTPS** para las actualizaciones de firmware porque es más rápido y confiable que el método antiguo basado en CAPWAP.
    
- **The Role of DHCP:** When you connect a new FortiSwitch, it usually gets an internal IP address from the FortiGate via **DHCP** (using a special option) to start the FortiLink communication. // El rol del DHCP: Cuando conectas un FortiSwitch nuevo, este suele obtener una IP interna del FortiGate mediante **DHCP** (usando una opción especial) para iniciar la comunicación FortiLink.
![[Pasted image 20260313160119.png]]
![[Pasted image 20260313160056.png]]

## Configure FortiLink on FortiGate // Configurar FortiLink en FortiGate

**To configure FortiLink, start by enabling the switch controller feature on the FortiGate device.** // Para configurar FortiLink, comience habilitando la función de "switch controller" (controlador de switch) en el dispositivo FortiGate.

**Then, create a FortiLink interface under the WiFi & Switch Controller > FortiLink Interface menu.** // Luego, cree una interfaz FortiLink en el menú WiFi & Switch Controller > FortiLink Interface.

**This interface must be assigned to one or more FortiGate ports used for switch management. It is recommended to assign more than one port for redundancy.** // Esta interfaz debe asignarse a uno o más puertos del FortiGate utilizados para la gestión del switch. Se recomienda asignar más de un puerto para redundancia.

**After selecting the appropriate ports, you must configure an IP address for the FortiLink interface.** // Después de seleccionar los puertos adecuados, debe configurar una dirección IP para la interfaz FortiLink.

**Depending on the network design, you can also enable options like the DHCP server, automatic switch authorization, or a FortiLink split interface.** // Según el diseño de la red, también puede habilitar opciones como el servidor DHCP, la autorización automática de switches o una interfaz dividida (split interface) de FortiLink.

**Split interface is used when you need to connect a FortiLink aggregate interface to more than one FortiSwitch.** // La interfaz dividida se utiliza cuando necesita conectar una interfaz agregada de FortiLink a más de un FortiSwitch.

**After setting up FortiLink, connect FortiSwitch to the FortiGate port configured for FortiLink. After a few seconds, verify that the FortiSwitches were discovered by FortiGate, under WiFi & Switch Controller > Managed FortiSwitches.** // Después de configurar FortiLink, conecte el FortiSwitch al puerto del FortiGate configurado para FortiLink. Tras unos segundos, verifique que los FortiSwitches hayan sido descubiertos por el FortiGate en WiFi & Switch Controller > Managed FortiSwitches.

**If automatic authorization is not enabled, manually authorize the FortiSwitches. Once authorized, the switches become visible and manageable directly from the FortiGate interface.** // Si la autorización automática no está habilitada, autorice manualmente los FortiSwitches. Una vez autorizados, los switches se vuelven visibles y gestionables directamente desde la interfaz del FortiGate.

**It is important to note that newer FortiSwitch models broadcast FortiLink discovery frames on all ports by default, simplifying the connection process. However, older models may require connecting through specific dedicated ports to initiate FortiLink communication.** // Es importante tener en cuenta que los modelos de FortiSwitch más nuevos transmiten tramas de descubrimiento de FortiLink en todos los puertos de forma predeterminada, simplificando el proceso de conexión. Sin embargo, los modelos más antiguos pueden requerir la conexión a través de puertos específicos dedicados para iniciar la comunicación FortiLink.

### Información Adicional y Análisis de las Imágenes

- **802.3ad Aggregate:** In the first image, notice the "Type" is `FortiLink (802.3ad Aggregate)`. This is a standard for **Link Aggregation (LAG)**, which combines multiple physical ports (like Port3 and Port4) into one logical link to increase bandwidth and provide redundancy. // 802.3ad Aggregate: En la primera imagen, observa que el "Type" es `FortiLink (802.3ad Aggregate)`. Este es un estándar para la **Agregación de Enlaces (LAG)**, que combina múltiples puertos físicos (como Port3 y Port4) en un solo enlace lógico para aumentar el ancho de banda y brindar redundancia.
    
- **Split Interface:** The "FortiLink split Interface" toggle is crucial when connecting to a stack of switches. If enabled, it allows the FortiGate to connect to different switches in a stack as if they were one, preventing loops without needing Spanning Tree on those specific links. // Split Interface: El interruptor "FortiLink split Interface" es crucial al conectarse a un stack de switches. Si está habilitado, permite que el FortiGate se conecte a diferentes switches en un stack como si fueran uno solo, evitando bucles sin necesidad de Spanning Tree en esos enlaces específicos.
    
- **Authorization Status:** In the second image, you see some switches as **"Offline"** (orange) and one as **"Online"** (green). A common issue is forgetting to **Authorize** the switch; until you click "Authorize", the FortiGate will see it but won't send any configuration to it. // Estado de autorización: En la segunda imagen, ves algunos switches como **"Offline"** (naranja) y uno como **"Online"** (verde). Un problema común es olvidar **Autorizar** el switch; hasta que no hagas clic en "Authorize", el FortiGate lo verá pero no le enviará ninguna configuración.
    
- **Default IP:** The address `10.0.13.254/24` is used for the management network between the firewall and switches. Clients shouldn't be on this subnet. // IP por defecto: La dirección `10.0.13.254/24` se utiliza para la red de gestión entre el firewall y los switches. Los clientes no deben estar en esta subred.

![[Pasted image 20260313160533.png]]
![[Pasted image 20260313160559.png]]

## FortiLink Topologies // Topologías de FortiLink

**FortiLink offers flexible deployment options, allowing FortiGate to manage Fortiswitches in a variety of topologies suited to different network environments.** // FortiLink ofrece opciones de implementación flexibles, lo que permite que FortiGate gestione FortiSwitches en una variedad de topologías adecuadas para diferentes entornos de red.

### 1. Single FortiGate unit managing a stack of several FortiSwitch units // Una sola unidad FortiGate gestionando un "stack" de varias unidades FortiSwitch.

**Switches are connected in a daisy-chain or ring topology, with the lead switch directly connected to the FortiGate via FortiLink.** // Los switches se conectan en una topología de "cadena de margarita" (daisy-chain) o de anillo, con el switch principal conectado directamente al FortiGate a través de FortiLink.

**The diagram also shows the option of connecting a standby FortiLink connection to the last FortiSwitch unit. For this configuration, you enable FortiLink Split-Interface with an aggregate interface that contains one active link and one standby link.** // El diagrama también muestra la opción de conectar una conexión FortiLink de reserva (standby) a la última unidad FortiSwitch. Para esta configuración, se habilita la "Interfaz Dividida" de FortiLink con una interfaz agregada que contiene un enlace activo y uno de reserva.


### 2. HA-mode FortiGate units managing a stack of several FortiSwitch units // Unidades FortiGate en modo HA gestionando un "stack" de varias unidades FortiSwitch.

**In the case of a FortiGate A-P HA cluster, both FortiGate units connect to the first FortiSwitch unit in the stack. Optionally, they can also connect to the last FortiSwitch unit, in which case, you must enable FortiLink Split Interface to avoid loops in the network.** // En el caso de un clúster HA de FortiGate en modo Activo-Pasivo (A-P), ambas unidades FortiGate se conectan a la primera unidad FortiSwitch del stack. Opcionalmente, también pueden conectarse a la última unidad, en cuyo caso se debe habilitar la "Interfaz Dividida" de FortiLink para evitar bucles en la red.


### 3. FortiLink mode over a layer-3 network // Modo FortiLink a través de una red de Capa 3.

**Allows FortiSwitch islands, each with one or more FortiSwitch units, to operate in FortiLink mode across routed networks, even though they are not directly connected to the FortiGate acting as the switch-controller.** // Permite que "islas" de FortiSwitch, cada una con una o más unidades, operen en modo FortiLink a través de redes enrutadas, incluso si no están conectadas directamente al FortiGate que actúa como controlador del switch.


### 4. Standalone FortiGate unit with dual-homed FortiSwitch access // Unidad FortiGate independiente con acceso a FortiSwitch de "doble residencia" (dual-homed).

**The standalone FortiGate unit with dual-homed FortiSwitch access topology provides high port density with two tiers of FortiSwitch units. This example includes the use of a multichassis link aggregation (MCLAG) peer group between FortiSwitch 1 and FortiSwitch 2. FortiGate sees only one logical FortiSwitch.** // La topología de unidad FortiGate independiente con acceso de doble residencia proporciona una alta densidad de puertos con dos niveles de unidades FortiSwitch. Este ejemplo incluye el uso de un grupo de agregación de enlaces de chasis múltiple (MCLAG) entre el FortiSwitch 1 y el FortiSwitch 2. El FortiGate solo ve un FortiSwitch lógico.


### Información Adicional y Análisis de las Imágenes

- **Daisy-chain vs. Ring:** En la topología 1, conectar el último switch de vuelta al FortiGate (formando un anillo) es una **Best Practice** para que, si un cable intermedio falla, los switches sigan siendo gestionados por la otra vía. // Connecting the last switch back to the FortiGate (forming a ring) is a **Best Practice** so that if an intermediate cable fails, the switches are still managed through the other path.
    
- **L3 FortiLink:** Esta es la solución ideal para sucursales. El FortiGate está en la oficina central y gestiona los switches de las sucursales a través de una VPN o enlace enrutado. // This is the ideal solution for branch offices. The FortiGate is at the headquarters and manages the branch switches through a VPN or routed link.
    
- **MCLAG (Multi-Chassis Link Aggregation):** Es una tecnología avanzada donde dos switches físicos actúan como uno solo para el equipo que se conecta a ellos (en este caso, el FortiGate). Esto permite redundancia total sin que el Spanning Tree bloquee enlaces. // This is an advanced technology where two physical switches act as a single one for the device connecting to them (in this case, the FortiGate). This allows for full redundancy without Spanning Tree blocking links.


![[Pasted image 20260313162436.png]]
![[Pasted image 20260313162530.png]]![[Pasted image 20260313162544.png]]![[Pasted image 20260313162600.png]]
![[Pasted image 20260313162619.png]]



![[Pasted image 20260313162658.png]]

![[Pasted image 20260313162813.png]]

![[Pasted image 20260313162840.png]]
![[Pasted image 20260313162908.png]]

