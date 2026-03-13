Configuring FortiGate SSL VPN

## Learning Objectives // Objetivos de Aprendizaje

- **Describe what SSL VPN is and its benefits // Describir qué es SSL VPN y sus beneficios.**
    
- **Describe how Fortigate SSL VPN works // Describir cómo funciona la SSL VPN de FortiGate.**
    
- **Configure FortiGate SSL VPN // Configurar la SSL VPN de FortiGate.**
    
- **Apply general best practices when using SSL VPN // Aplicar las mejores prácticas generales al usar SSL VPN.**
![[Pasted image 20260312233100.png]]

## Secure Socket Layer VPN // VPN de Capa de Sockets Seguros

- **Secure Sockets Layer Virtual Private Network (SSL VPN) is a type of VPN that uses SSL encryption to create a secure and encrypted connection between a client device and a device acting as a VPN server.** // La Red Privada Virtual de Capa de Sockets Seguros (SSL VPN) es un tipo de VPN que utiliza el cifrado SSL para crear una conexión segura y cifrada entre un dispositivo cliente y un dispositivo que actúa como servidor VPN.

### Video Transcript // Transcripción del Video

- **Secure Sockets Layer Virtual Private Network, SSL VPN, is a type of VPN that uses SSL encryption to create a secure and encrypted connection between a client device and a device acting as a VPN server.** // La Red Privada Virtual de Capa de Sockets Seguros, SSL VPN, es un tipo de VPN que utiliza el cifrado SSL para crear una conexión segura y cifrada entre un dispositivo cliente y un dispositivo que actúa como servidor VPN.
    
- **Although SSL VPN is most commonly used to grant remote workers access to their corporate networks, it is also possible to configure it between two FortiGate firewalls.** // Aunque la SSL VPN se utiliza más comúnmente para otorgar a los trabajadores remotos acceso a sus redes corporativas, también es posible configurarla entre dos firewalls FortiGate.
    
- **In this lesson, you will learn about the remote access implementation.** // En esta lección, aprenderás sobre la implementación de acceso remoto.

### Additional Notes & Observations // Notas Adicionales y Observaciones

- **The diagram illustrates two main ways to connect: via FortiClient (Tunnel Mode) or via Web Portal (Web Mode).** // El diagrama ilustra dos formas principales de conectarse: a través de FortiClient (Modo Túnel) o mediante un Portal Web (Modo Web).
    
- **The FortiGate acts as the termination point for the VPN tunnel, bridging the external WAN traffic (172.20.120.123) to the internal LAN (192.168.1.99/24).** // El FortiGate actúa como el punto de terminación para el túnel VPN, conectando el tráfico externo de la WAN (172.20.120.123) con la LAN interna (192.168.1.99/24).

- **In "Web Mode," the user doesn't need special software, just a browser. In "Tunnel Mode," FortiClient creates a virtual network interface on the user's computer for full network access.** // En el "Modo Web", el usuario no necesita software especial, solo un navegador. En el "Modo Túnel", FortiClient crea una interfaz de red virtual en la computadora del usuario para un acceso completo a la red.
![[Pasted image 20260312233154.png]]


## Benefits of Using SSL VPN // Beneficios de usar SSL VPN

**Many organizations opt to use SSL VPN for remote access over the IPsec VPN. However, each technology has its pros and cons, so you should examine your scenario carefully to make the best choice.** // Muchas organizaciones optan por utilizar SSL VPN para el acceso remoto en lugar de la VPN IPsec. Sin embargo, cada tecnología tiene sus pros y sus contras, por lo que debe examinar su escenario cuidadosamente para tomar la mejor decisión.

**These are some benefits of using SSL VPNs with FortiGate. It is important to note that some of these benefits apply only to specific configurations.** // Estos son algunos beneficios del uso de SSL VPN con FortiGate. Es importante notar que algunos de estos beneficios se aplican solo a configuraciones específicas.

### 1. Use of common protocol HTTP/HTTPS // Uso de protocolo común HTTP/HTTPS

**SSL is used to encrypt HTTP traffic and, by default, uses port 443. This means that typically this traffic is not blocked by intermediate firewalls.** // SSL se utiliza para cifrar el tráfico HTTP y, por defecto, utiliza el puerto 443. Esto significa que, normalmente, este tráfico no es bloqueado por firewalls intermedios.

### 2. Flexibility for client access // Flexibilidad para el acceso de clientes

**Depending on the needs of the clients, they may only require a web browser to access a customized web portal. This is especially useful when dealing with mobile devices. However, the option of installing client VPN software is also available.** // Dependiendo de las necesidades de los clientes, es posible que solo necesiten un navegador web para acceder a un portal web personalizado. Esto es especialmente útil cuando se trata de dispositivos móviles. Sin embargo, la opción de instalar un software cliente VPN también está disponible.

### 3. Granular access // Acceso granular

**Administrators can easily restrict which resources the clients are allowed to access.** // Los administradores pueden restringir fácilmente a qué recursos se les permite acceder a los clientes.

### 4. Integrity checks for Windows clients // Verificaciones de integridad para clientes Windows

**This security feature ensures that remote devices connecting to the VPN are compliant with the security policies of the organization. For example, it can check if the client has an antivirus software installed and deny access if it doesn't.** // Esta función de seguridad garantiza que los dispositivos remotos que se conectan a la VPN cumplan con las políticas de seguridad de la organización. Por ejemplo, puede verificar si el cliente tiene un software antivirus instalado y denegar el acceso si no lo tiene.

### 5. Cost effective // Costo-efectivo (Económico)

**Unlike other vendors, no additional license is required to use SSL VPN. The FortiClient VPN can also be made available for download at no cost from the SSL portal. Additionally, the number of remote users supported is determined only by the FortiGate model.** // A diferencia de otros proveedores, no se requiere ninguna licencia adicional para usar SSL VPN. El FortiClient VPN también puede estar disponible para su descarga sin costo desde el portal SSL. Además, el número de usuarios remotos admitidos se determina únicamente por el modelo de FortiGate.

### Datos extraídos del video y las imágenes (Faltantes anteriormente) // Extra data from video and images

- **The video mentions that SSL VPN is often chosen because it is easier to use than IPsec for remote workers.** // El video menciona que la SSL VPN se elige a menudo porque es más fácil de usar que IPsec para trabajadores remotos.
    
- **The image for "Integrity checks" shows a laptop with a "SECURE" shield, emphasizing the compliance aspect.** // La imagen de "Verificaciones de integridad" muestra una laptop con un escudo de "SEGURO", enfatizando el aspecto de cumplimiento (compliance).
    
- **The "Granular access" image includes a 2FA icon, suggesting that identity verification is part of restricting access.** // La imagen de "Acceso granular" incluye un icono de 2FA, sugiriendo que la verificación de identidad es parte de la restricción de acceso.
![[Pasted image 20260312234359.png]]
![[Pasted image 20260312234223.png]]
![[Pasted image 20260312234249.png]]
![[Pasted image 20260312234309.png]]
![[Pasted image 20260312234322.png]]
![[Pasted image 20260312234339.png]]

Esta sección es fundamental porque profundiza en las diferencias operativas entre los dos modos. He capturado cada palabra del video y el texto íntegro de las ventanas emergentes en las imágenes para que tu apunte sea total.

---

## SSL VPN Functionality // Funcionalidad de SSL VPN

**SSL VPNs are available in two modes: web mode and tunnel mode. Based on your requirements, you can deploy an SSL VPN using one mode or both.** // Las SSL VPN están disponibles en dos modos: modo web y modo túnel. Basado en sus requisitos, puede implementar una SSL VPN usando un modo o ambos.

---

### Web Mode // Modo Web

**Web mode provides access to web-based applications through a web browser.** // El modo web proporciona acceso a aplicaciones basadas en web a través de un navegador web.

- **The user only needs to open the URL or IP address provided and log in to the web portal.** // El usuario solo necesita abrir la URL o la dirección IP proporcionada e iniciar sesión en el portal web.
    
- **It is important to mention that FortiGate functions as a reverse web proxy to allow access to applications that are not natively designed to be accessed through the web.** // Es importante mencionar que FortiGate funciona como un proxy web inverso para permitir el acceso a aplicaciones que no están diseñadas nativamente para ser accedidas a través de la web.
    
- **This mode is best suited for users who need access to a limited set of resources, such as web-based applications, intranet sites, and email, among others.** // Este modo es el más adecuado para usuarios que necesitan acceso a un conjunto limitado de recursos, como aplicaciones basadas en web, sitios de intranet y correo electrónico, entre otros.
    

**Advantages (+) // Ventajas (+):**

- **Doesn't require any client software to be installed.** // No requiere que se instale ningún software cliente.
    
- **Administrators can provide very granular access to the users.** // Los administradores pueden proporcionar un acceso muy granular a los usuarios.
    

**Disadvantages (-) // Desventajas (-):**

- **Supports limited number of applications and protocols, for example, bookmarked URLs, FTP servers, and so on.** // Admite un número limitado de aplicaciones y protocolos, por ejemplo, URL marcadas, servidores FTP, etc.
    

---

### Tunnel Mode // Modo Túnel

**Tunnel mode provides full network access to remote users as if they were physically present on the corporate network.** // El modo túnel proporciona acceso total a la red a los usuarios remotos como si estuvieran físicamente presentes en la red corporativa.

- **This mode is best suited for remote workers who need to access a wide range of services, including client-server applications, file shares, and other typical network resources.** // Este modo es el más adecuado para trabajadores remotos que necesitan acceder a una amplia gama de servicios, incluyendo aplicaciones cliente-servidor, archivos compartidos y otros recursos de red típicos.
    
- **The ability to access all kinds of resources is the big advantage of this mode.** // La capacidad de acceder a todo tipo de recursos es la gran ventaja de este modo.
    

**Advantages (+) // Ventajas (+):**

- **Provides access to all kinds of resources.** // Proporciona acceso a todo tipo de recursos.
    

**Disadvantages (-) // Desventajas (-):**

- **However, to enable this, you must install and configure FortiClient VPN on the remote device. This may create extra overhead for the support team.** // Sin embargo, para habilitar esto, debe instalar y configurar FortiClient VPN en el dispositivo remoto. Esto puede crear una carga de trabajo adicional para el equipo de soporte.
    
- **Especially when dealing with users who are not technically savvy and are trying to use their own devices.** // Especialmente cuando se trata de usuarios que no tienen conocimientos técnicos y están intentando usar sus propios dispositivos.
    

---

### Additional Notes & Observations // Notas adicionales y observaciones

- **Protocol Support in Web Mode: The video specifically mentions that typical access includes bookmarked URLs, FTP servers, Windows shares, and remote sessions using Telnet, SSH, VNC, or RDP.** // Soporte de protocolos en Modo Web: El video menciona específicamente que el acceso típico incluye marcadores de URL, servidores FTP, carpetas compartidas de Windows y sesiones remotas usando Telnet, SSH, VNC o RDP.
    
- **Reverse Proxy Mechanism: Note that in Web Mode, FortiGate is the one "talking" to the internal servers on behalf of the user, which is why it's called a reverse proxy.** // Mecanismo de Proxy Inverso: Nota que en el Modo Web, FortiGate es quien "habla" con los servidores internos en nombre del usuario, por eso se le llama proxy inverso.
    
- **Support Overhead: The mention of "extra overhead" refers to the time the IT team spends helping users install FortiClient, update it, and troubleshoot local connection issues.** // Carga de soporte: La mención de "carga adicional" se refiere al tiempo que el equipo de TI gasta ayudando a los usuarios a instalar FortiClient, actualizarlo y solucionar problemas de conexión local.
![[Pasted image 20260312234658.png]]
![[Pasted image 20260312235142.png]]
![[Pasted image 20260312235200.png]]

## Configuring SSL VPN // Configurando SSL VPN

**Configuring SSL VPN requires several steps that vary according to specific requirements. The process is very simple and involves the following general steps:** // La configuración de la SSL VPN requiere varios pasos que varían según los requisitos específicos. El proceso es muy sencillo e involucra los siguientes pasos generales:

### Step 1 // Paso 1

**Create the users and groups that will be authorized to connect.** // Crear los usuarios y grupos que estarán autorizados para conectarse.

- **You can use local users or any of the supported remote authentication servers for this.** // Puede utilizar usuarios locales o cualquiera de los servidores de autenticación remota admitidos para esto.
    
- **The image shows an example with groups like "Guest-group" and "RemoteVPNUsers" assigned as Firewall type.** // La imagen muestra un ejemplo con grupos como "Guest-group" y "RemoteVPNUsers" asignados como tipo Firewall.

### Step 2 // Paso 2

**Review, edit, or create SSL VPN portals.** // Revisar, editar o crear portales SSL VPN.

- **FortiGate includes three default SSL VPN portals configured for web access, tunnel access, or both (full-access).** // FortiGate incluye tres portales SSL VPN predeterminados configurados para acceso web, acceso por túnel o ambos (full-access).
    
- **You can also create custom portals to meet specific needs for specific users.** // También puede crear portales personalizados para satisfacer necesidades específicas de usuarios particulares.
    
- **Note that SSL VPN is not enabled by default, so no portals will be visible until you enable the feature under System > Feature Visibility.** // Tenga en cuenta que la SSL VPN no está habilitada por defecto, por lo que no habrá portales visibles hasta que habilite la función en System > Feature Visibility.
    
- **Web mode must also be enabled as a separate step to be able to see the third (web access) portal.** // El modo web también debe habilitarse como un paso separado para poder ver el tercer portal (de acceso web).

### Step 3 // Paso 3

**Configure the SSL VPN settings.** // Configurar los ajustes de la SSL VPN.

- **These settings determine the port number that will be used to receive connection requests, the SSL certificate to be used, and options specific to each SSL VPN mode.** // Estos ajustes determinan el número de puerto que se utilizará para recibir solicitudes de conexión, el certificado SSL que se usará y las opciones específicas para cada modo de SSL VPN.
    
- **In this step, you also determine which users will be accessing which portal.** // En este paso, también se determina qué usuarios accederán a qué portal.
    
- **The example shows listening on "port3" using port "10443".** // El ejemplo muestra la escucha en el "port3" utilizando el puerto "10443".

### Step 4 // Paso 4

**Create a firewall policy to allow VPN traffic.** // Crear una política de firewall para permitir el tráfico VPN.

- **You create the firewall policy that allows the traffic through the firewall in the same manner as with other policies.** // Se crea la política de firewall que permite el tráfico a través del firewall de la misma manera que con otras políticas.
    
- **One difference here is the use of a virtual tunnel interface in the "From" field (ssl.root) to refer specifically to the VPN traffic.** // Una diferencia aquí es el uso de una interfaz de túnel virtual en el campo "From" (ssl.root) para referirse específicamente al tráfico de la VPN.
    
- **The policy usually goes from "ssl.root" to the internal destination (e.g., "port6" / LAN).** // La política generalmente va desde "ssl.root" hacia el destino interno (por ejemplo, "port6" / LAN).

### Additional Notes & Observations // Notas adicionales y observaciones

- **Default Port Change: Notice in Step 3 the port is 10443. It is a common best practice to change the default port (443) to avoid conflicts with the FortiGate administrative HTTPS access.** // Cambio de puerto por defecto: Nota en el Paso 3 que el puerto es 10443. Es una mejor práctica común cambiar el puerto por defecto (443) para evitar conflictos con el acceso HTTPS administrativo del FortiGate.
    
- **Interface ssl.root: This is a logical interface. Even if the users connect physically via "port3", the firewall policies must use "ssl.root" as the source interface.** // Interfaz ssl.root: Esta es una interfaz lógica. Aunque los usuarios se conecten físicamente a través del "port3", las políticas del firewall deben usar "ssl.root" como la interfaz de origen.
    
- **Authentication Servers: When the video mentions "remote authentication servers", it refers to integration with services like RADIUS, LDAP, or AD (Active Directory).** // Servidores de autenticación: Cuando el video menciona "servidores de autenticación remota", se refiere a la integración con servicios como RADIUS, LDAP o AD (Active Directory).
![[Pasted image 20260312235414.png]]
![[Pasted image 20260312235429.png]]
![[Pasted image 20260312235446.png]]
![[Pasted image 20260312235501.png]]
![[Pasted image 20260312235518.png]]

## SSL VPN Best Practices // Mejores prácticas de SSL VPN

**The following are some general best practices to keep in mind when working with SSL VPN. Click each tile to learn more.** // Las siguientes son algunas mejores prácticas generales a tener en cuenta al trabajar con SSL VPN. Haga clic en cada mosaico para obtener más información.

### 1. Select the appropriate SSL VPN mode // Seleccionar el modo de SSL VPN apropiado

**It may be possible that your users need only one of the SSL VPN modes. Use SSL VPN portals with the unused SSL mode disabled.** // Es posible que sus usuarios solo necesiten uno de los modos de SSL VPN. Utilice portales SSL VPN con el modo SSL no utilizado deshabilitado.

### 2. Reduce administrative effort by using remote authentication servers // Reducir el esfuerzo administrativo mediante el uso de servidores de autenticación remota

**Avoid using local users if possible. Having a centralized authentication solution saves time and prevents human errors. This is especially true in bigger environments.** // Evite el uso de usuarios locales si es posible. Tener una solución de autenticación centralizada ahorra tiempo y evita errores humanos. Esto es especialmente cierto en entornos más grandes.

### 3. Use a valid SSL certificate // Usar un certificado SSL válido

**Replace the default self-signed certificate with another one that is trusted by your users’ devices. You can purchase a certificate from a trusted vendor, or you can implement your own PKI infrastructure to achieve this.** // Reemplace el certificado predeterminado autofirmado por otro en el que confíen los dispositivos de sus usuarios. Puede comprar un certificado de un proveedor de confianza o puede implementar su propia infraestructura PKI para lograrlo.

### 4. Use the principle of least privilege when configuring firewall policies for VPN traffic // Usar el principio de menor privilegio al configurar políticas de firewall para el tráfico VPN

**This is true for any firewall policy, but it is especially important when you are allowing remote devices to connect to your network.** // Esto es cierto para cualquier política de firewall, pero es especialmente importante cuando permite que dispositivos remotos se conecten a su red.

### 5. Use the client integrity check // Usar la verificación de integridad del cliente

**For Windows clients, always verify that they have antivirus software, firewall software, or both, installed.** // Para clientes Windows, verifique siempre que tengan instalado software antivirus, software de firewall o ambos.

### 6. If possible, do not allow connections from all locations // Si es posible, no permita conexiones desde todas las ubicaciones

**This is not always feasible, but it is ideal to restrict access to connection requests from specific public IP addresses trusted by your organization.** // Esto no siempre es factible, pero lo ideal es restringir el acceso a las solicitudes de conexión desde direcciones IP públicas específicas en las que confíe su organización.

### Additional Notes & Observations // Notas adicionales y observaciones

- **Geo-Restricting Access: The last point refers to "Geo-IP" filtering. If your company only operates in one country, you can configure FortiGate to block VPN login attempts from any other country to reduce the attack surface.** // El último punto se refiere al filtrado por "Geo-IP". Si su empresa solo opera en un país, puede configurar el FortiGate para bloquear intentos de inicio de sesión VPN desde cualquier otro país para reducir la superficie de ataque.
    
- **PKI Infrastructure: Mentioned in point 3, a PKI (Public Key Infrastructure) is a system for creating, managing, and distributing digital certificates.** // Infraestructura PKI: Mencionada en el punto 3, una PKI (Infraestructura de Clave Pública) es un sistema para crear, gestionar y distribuir certificados digitales.
    
- **Self-Signed Warnings: Using the default certificate causes browsers to show a "Your connection is not private" warning, which can confuse users and decrease trust.**// Advertencias de autofirmado: El uso del certificado por defecto hace que los navegadores muestren una advertencia de "Su conexión no es privada", lo que puede confundir a los usuarios y disminuir la confianza.

![[Pasted image 20260312235921.png]]
![[Pasted image 20260312235940.png]]
![[Pasted image 20260312235956.png]]
![[Pasted image 20260313000010.png]]
![[Pasted image 20260313000027.png]]
![[Pasted image 20260313000048.png]]
![[Pasted image 20260313000107.png]]


![[Pasted image 20260313000131.png]]
![[Pasted image 20260313000202.png]]
![[Pasted image 20260313000246.png]]