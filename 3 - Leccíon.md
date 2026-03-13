## Firewall Polices
**After completing this lesson, you will be able to achieve these objectives:** // Después de completar esta lección, podrá lograr estos objetivos:

**Describe what firewall policies are** // Describir qué son las políticas de firewall

**Understand how firewall policies work** // Comprender cómo funcionan las políticas de firewall

**Describe how inspection modes work** // Describir cómo funcionan los modos de inspección

**Configure firewall policies** // Configurar las políticas de firewall

### Firewall Policies 
**Firewall policies are sets of rules that you use to control whether traffic in you network is accepted by FortiGate and, if it is accepted, how FortiGate processes it.**
Las políticas de firewall son conjuntos de reglas que se utilizan para controlar si FortiGate acepta el tráfico en su red y, si lo acepta, cómo lo procesa FortiGate.

![[Pasted image 20260305092613.png]]

### Matching Network Traffic to a Firewall Policy

**Firewall policies define what traffic matches them and what FortiGate does when traffic does match.**
Las políticas de firewall definen qué tráfico coincide con ellas y qué hace FortiGate cuando coincide.

**Each policy has match criteria, which you can define using the following objects:**
Cada política tiene criterios de coincidencia, que se pueden definir mediante los siguientes objetos:

**Incoming and outgoing interfaces** // Interfaces de entrada y salida
**Source: IP address or user** // Dirección IP o usuario
**Destination: IPaddress or internet Service** // Dirección IP o servicio de Internet
**Service: Destination port** // Puerto de destino
**Schedule** // Horario

![[Pasted image 20260305093320.png]]

### Firewall Polocy Configured Actions
**When traffic matches a firewall policy, FortiGate applies the action configured in that firewall policy. 
if the Action is set to DENY, FortiGate drops the session
If the Action is set to ACCEPT, FortiGate accepts the session

Cuando el tráfico coincide con una política de firewall, FortiGate aplica la acción configurada en dicha política.
Si la acción está configurada como DENEGAR, FortiGate cierra la sesión.
Si la acción está configurada como ACEPTAR, FortiGate acepta la sesión.


![[Pasted image 20260305093638.png]]

### Defining the Source and Destination Fields

**The Source field Both the Source field and the destination fielf of a firewall policy can match two different criteria: 
IP Subnet or internet servicces.

El campo Origen Tanto el campo Origen como el campo Destino de una política de firewall pueden coincidir con dos criterios diferentes: IP, subred o servicios de Internet.

![[Pasted image 20260305093952.png]]

### IP Subnet
**To use an IP subnet as the source or destination, you must first create a firewall address that corresponds to that subnet.
To create a policy that allows internal users to access the internet, you must configure a firewall address that matches the IP subnet of the internal network and use it as the source in the firewall policy.

Para usar una subred IP como origen o destino, primero debe crear una dirección de firewall que corresponda a esa subred.
Para crear una política que permita a los usuarios internos acceder a Internet, debe configurar una dirección de firewall que coincida con la subred IP de la red interna y usarla como origen en la política de firewall.

![[Pasted image 20260305094439.png]]

### Firewall Address for the IP Subnet
**You can also create a firewall address for the IP address of a specific divece, such as a web server.
You would use this address as the destination in any firewall policies 
that you want to allow to the server.

También puede crear una dirección de firewall para la dirección IP de un dispositivo específico, como un servidor web.
Esta dirección se usará como destino en cualquier política de firewall que desee permitir al servidor.

![[Pasted image 20260305094840.png]]

### Source and Destination
**A default ALL option is available for both source and destination IP addresses. The option matches all possible IP addresses.
To set a source user, you configure firewall authentication and then select either specific users or user groups. 

La opción "TODOS" predeterminada está disponible tanto para las direcciones IP de origen como de destino. Esta opción coincide con todas las direcciones IP posibles.
Para establecer un usuario de origen, configure la autenticación del firewall y luego seleccione usuarios o grupos de usuarios específicos.

![[Pasted image 20260305095313.png]]

### Internet Services
**To use an internet services as a source or destination, select the appropriate service from the internet service database (ISDB). 
The ISDB is a list that includes the IP subnets od commonly used web service providers, such as Meta, YouTube, and so on.
The FortiGate administrator is also able to add custom services to the list.

Para utilizar un servicio de Internet como origen o destino, seleccione el servicio adecuado en la base de datos de servicios de Internet (ISDB).
La ​​ISDB es una lista que incluye las subredes IP de los proveedores de servicios web más utilizados, como Meta, YouTube, etc.
El administrador de FortiGate también puede añadir servicios personalizados a la lista.

![[Pasted image 20260305095625.png]]

### The Policy Table
**The FortiGate policy table contains all firewall policies.
When matching traffic, FortiGate checks the policy table from top to bottom and processes traffic using the first policy that marches. if there is no match, FortiGate drops the traffic by applying the default implicit Deny firewall policy, located at the bottom of the table.
Because the first match is used, it is best practice to haave the most specific policies located at the top of the table, and the more general policies lower in the table.

La tabla de políticas de FortiGate contiene todas las políticas de firewall.
Al comparar el tráfico, FortiGate revisa la tabla de políticas de arriba a abajo y procesa el tráfico utilizando la primera política que se aplica. Si no hay coincidencia, FortiGate descarta el tráfico aplicando la política de firewall implícita predeterminada "Denegar", ubicada en la parte inferior de la tabla.
Dado que se utiliza la primera coincidencia, se recomienda tener las políticas más específicas ubicadas en la parte superior de la tabla y las políticas más generales en la parte inferior.

![[Pasted image 20260305100144.png]]

### Accepted Traffic 
**After acceoting traffic, FortiGate may apply other features and senttings to that traffic based on the firewall policy configuration.
This can include security scanning, such as antibirus, application control, and web filtering. 
Scanning cloud block the traffic if, for example, FortiGate discovers ir contains a virus. 
FortiGate also applies network address translation and logs traffic besed on the firewall policy settings.

Tras aceptar el tráfico, FortiGate puede aplicar otras funciones y envíos a dicho tráfico según la configuración de la política del firewall.
Esto puede incluir análisis de seguridad, como antivirus, control de aplicaciones y filtrado web.
El análisis bloquea el tráfico si, por ejemplo, FortiGate detecta que contiene un virus.
FortiGate también aplica la traducción de direcciones de red y registra el tráfico según la configuración de la política del firewall.

![[Pasted image 20260305100922.png]]

### inspection Modes
**When you configure a firewall policy, you must select one of two inspection modes: Flow-based inspection mode and proxy-based inspection mode. 

Al configurar una política de firewall, debe seleccionar uno de dos modos de inspección: modo de inspección basado en flujo y modo de inspección basado en proxy.

![[Pasted image 20260305102049.png]]

**Flow-based inspection mode examines the traffic as it through FortiGate, without any buffering. 
As each paket arrives, it is processed and forwarded without for the complete file or web page. 
FortiGate does not alter the original, wich means that any features that modify content, such as safe search enforccement, are not supported in this mode.

El modo de inspección basado en flujo examina el tráfico a medida que pasa por FortiGate, sin almacenamiento en búfer.
A medida que llega cada paquete, se procesa y reenvía sin necesidad de completar el archivo o la página web.
FortiGate no altera el contenido original, lo que significa que este modo no admite funciones que modifiquen el contenido, como la búsqueda segura.

![[Pasted image 20260305101858.png]]

**In proxy-base inspection mode, FortiGate buffers traffic and examines it as a whole before determining an action.
Because FortiGate examines the data as a whole, it can examine more points of data than it does when using flow-based inspection, bur using this mode does add latency to the overall transmission speed.
Proxy-based inspection is more thorough than flow-based inspection, yielding fewer false positives and negative results

En el modo de inspección basado en proxy, FortiGate almacena el tráfico en un búfer y lo examina en su conjunto antes de tomar una decisión.
Dado que FortiGate examina los datos en su conjunto, puede examinar más puntos de datos que con la inspección basada en flujo; sin embargo, este modo añade latencia a la velocidad de transmisión general.
La inspección basada en proxy es más exhaustiva que la inspección basada en flujo, lo que genera menos falsos positivos y resultados negativos.

![[Pasted image 20260305101816.png]]

### Lab Simulation

**Lab Simulation**

**Let's put these concepts into practice by completing the following lab simulation.
In order for network users to access the internet, you need to configure FortiGate device to allow this traffic.
For this lab simulation, the following information is provided to you:

- **The internal subnet is:** 10.0.1.0/24
    
- **The network user connects to:** Port 3
    
- **The internet facing interface is:** Port 1
    

**To achieve this configuration, you will complete three tasks to create a firewall policy that allows traffic from internal users to reach the internet.

Pongamos en práctica estos conceptos con la siguiente simulación de laboratorio.
Para que los usuarios de la red accedan a internet, debe configurar el dispositivo FortiGate para permitir este tráfico.
Para esta simulación de laboratorio, se proporciona la siguiente información:

- **La subred interna es:** 10.0.1.0/24

- **El usuario de la red se conecta a:** Puerto 3

- **La interfaz de acceso a internet es:** Puerto 1

Para lograr esta configuración, deberá completar tres tareas para crear una política de firewall que permita el acceso a internet del tráfico de los usuarios internos.

![[Pasted image 20260305102108.png]]

![[Pasted image 20260305103028.png]]