## Configuring System Setting and Basic Networking
### learning Objectives 
**After completing this lesson, you will be able to achieve these objetives:**

Después de completar esta lección, podrá lograr estos objetivos:

**1- Configure additional administrator accounts** // Configurar cuentas de administrador adicionales
**2- Configure networking interfaces** // Configurar interfaces de red
**3- Configure VLANs** // Configurar VLAN
**4- Configure static routes** // Configurar rutas estáticas
**5- Monitor static routes** // Monitorear rutas estáticas

![[Pasted image 20260304183826.png]]

### Configure addtional Administrator Accounts

**FortiGate has a default administrator account (admin) with full configuration permissions on the device.

FortiGate tiene una cuenta de administrador predeterminada (admin) con permisos de configuración completos en el dispositivo.

**Bad actors are aware of the default admin account, making it a commin target for their attacks 

Los actores maliciosos conocen la cuenta de administrador predeterminada, lo que la convierte en un objetivo común para sus ataques.

**It is best practice to create additional administratos accounts for managing your FortiGate firewalls

Se recomienda crear cuentas de administrador adicionales para administrar sus firewalls FortiGate

![[Pasted image 20260304184612.png]]

### Create an Administrator Account

**Because of their administrative roles, new administrator accounts are not created in the same way as regular users, nor do the have the same setting 

Debido a sus roles administrativos, las nuevas cuentas de administrador no se crean de la misma manera que las de los usuarios normales, ni tienen la misma configuración.

![[Pasted image 20260304185601.png]]

**Use the following steps to create an administrator account: 

![[Pasted image 20260304184946.png]]

**Go to System > Administrators > create new > Administrator.**
**Specify an account name** // Especifique un nombre de cuenta.
**specify where the account will be stored: locally or remotely.** //Especifique dónde se almacenará la cuenta: local o remotamente.
**type and then confirm a password, or the remote authentication group or both.** // Escriba y confirme una contraseña, el grupo de autenticación remota o ambos.
**select the administrator profile for the account.** // Seleccione el perfil de administrador para la cuenta.
**optionally, enable two-factor authenticcation, trusted hosts, and guest account provisioning restrictions, if applicable.** // Opcionalmente, habilite la autenticación de dos factores, los hosts de confianza y las restricciones de aprovisionamiento de cuentas de invitado, si corresponde.

### Assign Profiles to administrator Accounts

**Regardless of the options you select, you must assing and administrator profile to each account.
administrator profiles define what the administrator has permission to do when logged into FortiGate.
FortiGate includes several default profiles,
but you can create custom profiles to meet your specific requirements. For each of the configuration sections availeble, you can a assing read-only access, read-write access, or no access.

Independientemente de las opciones que seleccione, debe asignar un perfil de administrador a cada cuenta.
Los perfiles de administrador definen los permisos que el administrador tiene al iniciar sesión en FortiGate.
FortiGate incluye varios perfiles predeterminados, pero puede crear perfiles personalizados para satisfacer sus necesidades específicas. Para cada sección de configuración disponible, puede asignar acceso de solo lectura, acceso de lectura y escritura o ningún acceso.

![[Pasted image 20260304185809.png]]

### FortiGate interfaces
**Physical and virtual interfaces allow traffic
to flow between internal networks, and between the internet and internal networks.**

Las interfaces físicas y virtuales permiten que el tráfico fluya entre redes internas, y entre internet y estas.

**FortiGate has options for configuting interfaces.
that can scale as your organization grows.

FortiGate ofrece opciones para configurar interfaces que pueden escalar a medida que su organización crece.

![[Pasted image 20260304191101.png]]

**You can configure a variety of setting on FortiGate interfaces, including: 

Puede configurar una variedad de ajustes en las interfaces de FortiGate, incluidos:

**Alias: a name that identifies the interface for reference.** // Alias: un nombre que identifica la interfaz como referencia.
**IP Address: the public or private IP address user to connect to the interface.** // Dirección IP: la dirección IP pública o privada que el usuario utiliza para conectarse a la interfaz.
**Administrative access: the protocols that can be used to connect to the interface for administration purposes, such as HTTPS, PING, and SSH.** // Acceso administrativo: los protocolos que se pueden usar para conectarse a la interfaz con fines administrativos, como HTTPS, PING y SSH.
**DHCP servers: a server that dynamically assigns IP addresses to hosts on the network connected the interface.** // Servidores DHCP: un servidor que asigna dinámicamente direcciones IP a los hosts de la red conectados a la interfaz.

![[Pasted image 20260304191755.png]]

### Configuring VLANs

**¿What are virtual LANs (VLANs)?**
¿Qué son las redes LAN virtuales (VLAN)?

**They allow you to split your physical LAN into multiple logical LANs.**
Permiten dividir la LAN física en varias redes LAN lógicas.

**Each VLAN forms a separate broadcast domain.**
Cada VLAN forma un dominio de difusión independiente.

![[Pasted image 20260304192313.png]]

**Traffic is targged with the VLAN ID to identify the VLAN it belongs to.**
El tráfico se etiqueta con el ID de VLAN para identificar la VLAN a la que pertenece.

**The most popular togging protocol is the 802.1Q.**
El protocolo de etiquetado más popular es 802.1Q.

![[Pasted image 20260304192329.png]]

**FortiGate firewalls can utilize VLANs in several ways:**
Los firewalls FortiGate pueden utilizar las VLAN de varias maneras:

**To isolate devices, to reduce unnecessary traffic.**
Para aislar dispositivos y reducir el tráfico innecesario.

**Separations of traffic from different departaments, and to offer improved control over data flow within the network.**
Para separar el tráfico de diferentes departamentos y ofrecer un mejor control del flujo de datos dentro de la red.

**Segregation of traffic by type, such as data, voice, management, and others.**
Para segregar el tráfico por tipo, como datos, voz, administración, etc.

![[Pasted image 20260304193005.png]]

### VLANs and FortiGate
**FortiGate offers several ways to use VLANs depending on the mode it is running and the device model.**
FortiGate ofrece varias formas de utilizar VLAN según el modo en que se ejecuta y el modelo del dispositivo.

![[Pasted image 20260304193542.png]]

#### In NAT mode : 
**FortiGate operates as a layer 3 device, meaning it can route traffic between different VLANs and perform NAT.**
En modo NAT: FortiGate funciona como un dispositivo de capa 3, lo que significa que puede enrutar el tráfico entre diferentes VLAN y realizar NAT.
**VLANs are configured as subinterfaces on physical ports, and each subinterface is associated with a specific VLAN ID.**
Las VLAN se configuran como subinterfaces en puertos físicos, y cada subinterfaz está asociada a un ID de VLAN específico.
**Multiple VLANs can coexist on the same physical interface, if they hace different VLAN IDs.**
Varias VLAN pueden coexistir en la misma interfaz física si tienen diferentes ID de VLAN.
**FortiGate can add or remove tags from packets, depending on their direction
his mode allows FortiGate to control traffic between internal VLANs and external networks, such as the internet.**
FortiGate puede agregar o eliminar etiquetas de los paquetes, según su dirección.
Este modo permite a FortiGate controlar el tráfico entre las VLAN internas y las redes externas, como Internet.
**You can apply security to each VLAN subinterface individually, enabling granular access control and optimized traffic handling.**
Se puede aplicar seguridad a cada subinterfaz de VLAN individualmente, lo que permite un control de acceso granular y una gestión optimizada del tráfico.


![[Pasted image 20260304194346.png]]

#### In Transparent mode:

**FortiGate functions as a layer 2 bridge. inthes mode, FortiGate passes VLAN-tagged traffic while still applying security features such as antivirus scanning, web filtering, and intrusion preventions.
hawever, it does not suppert vertain services like SSL VPNs, DHCP servers, or full NAT.
Trasparent mode is ideal when network changes must be minimal,
because you can place FortiGate between two VLAN trunks whithout needing to alter the configuration of other switches.
administrators must create matching VLAN subinterfaces on both internal and external interfaces, then define security policies to allow traffic flow.

FortiGate funciona como un puente de capa 2. En este modo, FortiGate transmite el tráfico etiquetado por VLAN mientras aplica funciones de seguridad como análisis antivirus, filtrado web y prevención de intrusiones.
Sin embargo, no es compatible con ciertos servicios como VPN SSL, servidores DHCP o NAT completo.
El modo transparente es ideal cuando los cambios en la red deben ser mínimos, ya que permite colocar FortiGate entre dos troncales VLAN sin necesidad de modificar la configuración de otros switches.
Los administradores deben crear subinterfaces VLAN coincidentes en las interfaces internas y externas y, a continuación, definir políticas de seguridad para permitir el flujo de tráfico.

![[Pasted image 20260304195444.png]]

#### Virtual VLAN switch

**Some FortiGate models support a virtual VLAN switch, which allows hardware switch ports to operate as a managed layer 2 switch.
Ports can be assigned to specific VLANs or configured as trunk ports to carry multiple VLANs.
This configuration is useful in HA scenarios or for extending VLANs between devices. 

Algunos modelos FortiGate admiten un conmutador VLAN virtual, que permite que los puertos del conmutador de hardware funcionen como un conmutador de capa 2 gestionado.
Los puertos pueden asignarse a VLAN específicas o configurarse como puertos troncales para transportar múltiples VLAN.
Esta configuración es útil en escenarios de alta disponibilidad (HA) o para extender VLAN entre dispositivos.

![[Pasted image 20260304195858.png]]

### Configuring VLAN interfaces in NAT Mode

![[Pasted image 20260304200159.png]]

**Configuring a VLAN interface on FortiGates is very similar to configuring a physical interface.
To create a VLAN interface using the GUI click Network>Interfaces>Create New, then select interface.**

**Configurar una interfaz VLAN en FortiGates es muy similar a configurar una interfaz física.**
Para crear una interfaz VLAN mediante la interfaz gráfica de usuario, haga clic en Red > Interfaces > Crear nueva y seleccione la interfaz.

**In the type field, choose VLAN.
Next, select the VLAN protocol. The most common choice is 802.1Q, which supports up to 4094 VLANs and is suitable for most enviroments.
For larger networks requiring more scalability, you can opt for 802.1ad.
you must then specify the VLAN ID and the physical interface the VLAN will be associated with. keep in mid that a single port can be associated with multiple VLANs.
As with any interface, assign an IP address manually, dynamically using DHCP, or using another mothod.


En el campo de tipo, seleccione VLAN.
A continuación, seleccione el protocolo VLAN. La opción más común es 802.1Q, que admite hasta 4094 VLAN y es adecuada para la mayoría de los entornos.
Para redes más grandes que requieren mayor escalabilidad, puede optar por 802.1ad.
A continuación, debe especificar el ID de VLAN y la interfaz física a la que se asociará la VLAN. Tenga en cuenta que un solo puerto puede asociarse con varias VLAN.
Como con cualquier interfaz, asigne una dirección IP manualmente.

![[Pasted image 20260304202134.png]]

**Finally, you can configure administrative access protocols, anable the DHCP server, and adjust other optional settings, depending on your specific requirements.

Por último, puede configurar protocolos de acceso administrativo, habilitar el servidor DHCP y ajustar otras configuraciones opcionales, según sus requisitos específicos.

![[Pasted image 20260304203157.png]]![[Pasted image 20260304203211.png]]

### FortiGate DHCP Server
**A DHCP server dynamically assigns IP addresses to devices on the network connected to the interface you can configure one or more DHCP servers on any FortiGate interface.

Un servidor DHCP asigna dinámicamente direcciones IP a los dispositivos de la red conectados a la interfaz. Puede configurar uno o más servidores DHCP en cualquier interfaz de FortiGate.

![[Pasted image 20260304211119.png]]

**A DHCP server configuration includes:** // La configuración de un servidor DHCP incluye: 

**Address Range: the range of IP addresses that FottiGate assigns to devices.**
Rango de direcciones: el rango de direcciones IP que FottiGate asigna a los dispositivos.

**Netmask: the netmask of the address that FottiGate assigns to devices.**
Máscara de red: la máscara de red de la dirección que FottiGate asigna a los dispositivos.

**Default Gateway: the default gateway that FortiGate assigns to devices.
By default, this gateway is the same as the interface IP address.**
Puerta de enlace predeterminada: la puerta de enlace predeterminada que FortiGate asigna a los dispositivos.
Por defecto, esta puerta de enlace coincide con la dirección IP de la interfaz.

**DNS Server: the DNS server that FortiGate will assigns to device. By default, this is the same DNS server used by FortiGate.**
Servidor DNS: el servidor DNS que FortiGate asigna al dispositivo. De forma predeterminada, este es el mismo servidor DNS utilizado por FortiGate.

![[Pasted image 20260304211203.png]]

### Static Routing

**Static routing is the most basic way of configuring on a networl device, including firewall devices such as FortiGate. 
FortiGate has a default route to its gateway to provide internet network access. 
Even in a more complex setup, you would likely find static routes deployed.
All routes are part of the routing table, which FortiGate uses to match.

El enrutamiento estático es la forma más básica de configurar un dispositivo de red, incluyendo dispositivos de firewall como FortiGate.
FortiGate tiene una ruta predeterminada a su puerta de enlace para proporcionar acceso a la red de internet.
Incluso en una configuración más compleja, es probable que se implementen rutas estáticas.
Todas las rutas forman parte de la tabla de enrutamiento, que FortiGate utiliza para la correspondencia.

![[Pasted image 20260304212426.png]]

### Features of Static Routing
A static route includes: 

**Destination : FortiGate uses the destinations to match incoming traffic to the correct route.**
Destino: FortiGate utiliza los destinos para asignar el tráfico entrante a la ruta correcta.

**Gateway Address: This is the IP address that FrotiGate forwards traffic to**
Dirección de puerta de enlace: Esta es la dirección IP a la que FrotiGate reenvía el tráfico.

**Interface : This is the interface that FortiGate uses to forward towards its destination.**
Interfaz: Esta es la interfaz que FortiGate utiliza para reenviar el tráfico a su destino.

![[Pasted image 20260304212912.png]]

### The Default Route

**The default route tells FortiGate where to send traffic when packets do not include an exact match for the destination address in the FortiGate routing table.
Usually, all the users that are behind FortiGate need a default route in order to have internet access.
in the default route, the destination address is set to 0.0.0.0
The gateway address is typically the address of another router, either a device in your network that is between FortiGate and the network edge, or part of ISP network if FortiGate is located on the network edge. Finally, the interface is the Fortigate port that connects to that router, typically the WAN interface**

La ruta predeterminada indica a FortiGate dónde enviar el tráfico cuando los paquetes no coinciden exactamente con la dirección de destino en la tabla de enrutamiento de FortiGate.
Normalmente, todos los usuarios que se encuentran detrás de FortiGate necesitan una ruta predeterminada para tener acceso a internet.
En la ruta predeterminada, la dirección de destino se establece en 0.0.0.0.
La dirección de la puerta de enlace suele ser la dirección de otro enrutador, ya sea un dispositivo de su red que se encuentra entre FortiGate y el borde de la red, o parte de la red del ISP si FortiGate se encuentra en el borde de la red. Finalmente, la interfaz es Fortigate que se conecta a ese enrutador, generalmente la interfaz WAN.

![[Pasted image 20260304213744.png]]

### Monitoring Static Routes
**Every static route you create becomes part of the FortiGate configuration and you can verify this in the GUI under network > Static Routes. 
These static routes that you create will remain in the configuration until you delete them.**

Cada ruta estática que crees formará parte de la configuración de FortiGate y puedes verificarlo en la interfaz gráfica de usuario, en Red > Rutas estáticas.
Estas rutas estáticas que crees permanecerán en la configuración hasta que las elimines.

**Several conditions can prevent a configured route from being added to the routing table and consequently, not being used to forward traffic.**
Varias condiciones pueden impedir que una ruta configurada se agregue a la tabla de enrutamiento y, en consecuencia, no se utilice para reenviar tráfico.

**The most common of these conditions are:** Las condiciones más comunes son:
**The route is misconfigured.** // La ruta está mal configurada.
**The port associated with the route is down or disabled.** // El puerto asociado a la ruta está inactivo o deshabilitado.
**There is a better route to use to forwaed traffic to that destination.** // Existe una ruta mejor para redirigir el tráfico a ese destino.


![[Pasted image 20260304215241.png]]

### Routing Table

**In the scrren capture, you can see that there is a static route with destination 172.16.30.0/24 
However, since port6 is disable, this route is no included in the routing table that is also shown. 
To display the routing table, and check if an expected route is missing, you can go to Dashboard > Network > Static and Dynamic Routing.**

En la captura de pantalla, se puede ver que hay una ruta estática con destino 172.16.30.0/24.
Sin embargo, dado que el puerto 6 está deshabilitado, esta ruta no se incluye en la tabla de enrutamiento que también se muestra.
Para ver la tabla de enrutamiento y comprobar si falta una ruta esperada, puede ir a Panel de Control > Red > Enrutamiento estático y dinámico.

**Checking the routing table is often one of the firts steps you will take when troubleshooting network connectivity issues.**

Revisar la tabla de enrutamiento suele ser uno de los primeros pasos al solucionar problemas de conectividad de red.

![[Pasted image 20260304220640.png]]

### Lab Simulation 

Let's put these concepts into practice by completing the following lab simulation. 

**You need to configure FortiGate to allow clients to connect to the Internet. Clients must receive their network settings using DHCP.
You must first configure an interface facing the local area network with the correct IP address and to act as a DHCP server. Then, you will configure an interface facing the WAN. Finally, you must create a default route that uses WAN interface to forward all internet traffic to your ISP.

Debe configurar FortiGate para que los clientes puedan conectarse a Internet. Los clientes deben recibir su configuración de red mediante DHCP.
Primero, debe configurar una interfaz orientada a la red de área local con la dirección IP correcta y que actúe como servidor DHCP. A continuación, configurará una interfaz orientada a la WAN. Finalmente, debe crear una ruta predeterminada que utilice la interfaz WAN para reenviar todo el tráfico de Internet a su proveedor de servicios de Internet (ISP).

![[Pasted image 20260304221432.png]]
![[Pasted image 20260304221535.png]]
![[Pasted image 20260304222242.png]]