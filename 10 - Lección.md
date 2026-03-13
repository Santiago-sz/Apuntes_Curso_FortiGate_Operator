### Creating IPsec Virtual Private Networks

![[Pasted image 20260312195439.png]]
**After completing this lesson, you will be able to achieve these objectives:** // Después de completar esta lección, será capaz de alcanzar estos objetivos:

- **Understand what IPsec virtual private networks (VPNs) are and why they are used** // Comprender qué son las redes privadas virtuales (VPN) IPsec y por qué se utilizan
    
- **Understand how FortiGate IPsec VPNs work** // Comprender cómo funcionan las VPN IPsec de FortiGate
    
- **Configure IPsec VPNs using FortiGate devices** // Configurar VPNs IPsec utilizando dispositivos FortiGate

### IPsec VPNs
**IPsec is a suite of industry standard protocols that is used to create secure connections between devices located on different, and often geographically distant, networks.** // IPsec es un conjunto de protocolos de estándares de la industria que se utiliza para crear conexiones seguras entre dispositivos ubicados en redes diferentes y, a menudo, geográficamente distantes.

**These secure connections are known as virtual private networks, or VPNs.** // Estas conexiones seguras se conocen como redes privadas virtuales, o VPN.

![[Pasted image 20260312200844.png]]


## **Features of IPsec VPNs**

- **Depending on the configuration used, IPsec can provide some or all the following features:** // Dependiendo de la configuración utilizada, IPsec puede proporcionar algunas o todas las siguientes características:

### **Core Features (Características Principales)**

- **Data Authentication: To verify the source of the data.** // Autenticación de Datos: Para verificar la fuente de los datos.
    
- **Data Integrity: To prevent data tampering.** // Integridad de Datos: Para prevenir la manipulación de los datos.
    
- **Data Confidentiality: To encrypt the traffic.** // Confidencialidad de Datos: Para cifrar el tráfico.
    
- **Anti-replay Protection: To prevent replay attacks.** // Protección Anti-replay (Anti-reproducción): Para prevenir ataques de replicación.
    

---

### **Extra Information & Context (Información Adicional)**

Aquí te agrego algunos puntos clave que no se mencionan explícitamente en el texto pero que son fundamentales para entender estos conceptos en un entorno FortiGate:

- **Data Confidentiality is achieved through encryption algorithms like AES or 3DES, ensuring that even if data is intercepted, it cannot be read without the proper key.** // La confidencialidad de los datos se logra mediante algoritmos de cifrado como AES o 3DES, lo que garantiza que, incluso si se interceptan los datos, no se puedan leer sin la clave adecuada.
    
- **Data Integrity and Authentication often use Hashing algorithms like SHA-256 or MD5 to create a digital fingerprint of the packet.** // La integridad y la autenticación de los datos suelen utilizar algoritmos de Hashing como SHA-256 o MD5 para crear una huella digital del paquete.
    
- **Anti-replay protection works by assigning a unique sequence number to each packet; if a packet arrives with a duplicate or outdated number, the FortiGate drops it to prevent a breach.** // La protección anti-replay funciona asignando un número de secuencia único a cada paquete; si un paquete llega con un número duplicado o desactualizado, el FortiGate lo descarta para evitar una brecha de seguridad.
    


![[Pasted image 20260312204431.png]]


## **Advantages of Using IPsec VPNs**

- **These features are extremely important because, in most implementations, the VPN traffic travels through non-secure networks like the Internet.** // Estas características son extremadamente importantes porque, en la mayoría de las implementaciones, el tráfico VPN viaja a través de redes no seguras como Internet.

- **One important advantage that IPsec VPNs have over other VPN solutions is that they don't require the intervention of service providers.** // Una ventaja importante que tienen las VPN de IPsec sobre otras soluciones de VPN es que no requieren la intervención de los proveedores de servicios.

- **All that you need to establish a secure VPN tunnel is IP reachability between the two ends of the connection.** // Todo lo que necesitas para establecer un túnel VPN seguro es la "alcanzabilidad IP" (IP reachability) entre los dos extremos de la conexión.

### **Text from the Image (Texto de la Imagen)**

- **Remote offices are interconnected by routers or security appliances.** // Las oficinas remotas están interconectadas por routers o dispositivos de seguridad.
    
- **Mobile workers with VPN software client on laptops.** // Trabajadores móviles con software de cliente VPN en sus laptops.
    
- **Central site VPN aggregation by routers or security appliances.** // Agregación de VPN en el sitio central mediante routers o dispositivos de seguridad.
    
- **Encrypted VPN Tunnel** // Túnel VPN Cifrado.

### **Extra Information & Context (Información Adicional)**

- **IP Reachability: This refers to the ability of two devices to communicate over a network (like the Internet) using their IP addresses. As long as they can "see" each other, the tunnel can be formed without special ISP configuration.** // Alcanzabilidad IP: Se refiere a la capacidad de dos dispositivos para comunicarse a través de una red (como Internet) usando sus direcciones IP. Mientras puedan "verse" entre sí, el túnel puede formarse sin una configuración especial del proveedor de internet (ISP).
    
- **VPN Aggregation: This occurs when a central FortiGate device manages multiple incoming VPN connections from different branches or remote users simultaneously.** // Agregación de VPN: Esto ocurre cuando un dispositivo FortiGate central gestiona múltiples conexiones VPN entrantes desde diferentes sucursales o usuarios remotos de forma simultánea.

![[Pasted image 20260312210003.png]]

## **Types of VPNs**

- **IPsec can be used to create two types of VPNs: remote access VPNs and site-to-site VPNs.** // IPsec se puede utilizar para crear dos tipos de VPN: VPN de acceso remoto y VPN de sitio a sitio.
    
- **Click each VPN to learn more.** // Haz clic en cada VPN para aprender más.

### **Categories (Categorías)**

- **Remote access VPNs** // VPN de acceso remoto.
    
- **Site-to-site VPNs** // VPN de sitio a sitio.

### **Extra Information & Context (Información Adicional)**

Aquí te detallo qué significa cada una en el lenguaje técnico de Fortinet:

- **Site-to-Site VPN: Also known as "Gateway-to-Gateway", it connects two fixed locations (like a branch office to the main headquarters) through their respective FortiGate units. The users in both locations don't need any special software; the firewalls handle the encryption.** // VPN de Sitio a Sitio: También conocida como "Gateway-to-Gateway", conecta dos ubicaciones fijas (como una sucursal con la oficina central) a través de sus respectivas unidades FortiGate. Los usuarios en ambas ubicaciones no necesitan software especial; los firewalls se encargan del cifrado.
    
- **Remote Access VPN: Also known as "Client-to-Site", it allows individual users (teleworkers) to connect to the corporate network from anywhere. In FortiGate, this is typically done using the FortiClient software.** // VPN de Acceso Remoto: También conocida como "Cliente a Sitio", permite que usuarios individuales (teletrabajadores) se conecten a la red corporativa desde cualquier lugar. En FortiGate, esto se hace típicamente usando el software FortiClient.


![[Pasted image 20260312210334.png]]

## **Remote Access VPNs**

- **A remote access VPN allows a client device to connect to a remote network.** // Una VPN de acceso remoto permite que un dispositivo cliente se conecte a una red remota.
    
- **In a remote VPN, the client always initiates the connection.** // En una VPN remota, el cliente siempre inicia la conexión.
    
- **Remote users typically use a password to log into their workplace network, but other solutions are supported, including multi-factor authentication (MFA).** // Los usuarios remotos suelen utilizar una contraseña para iniciar sesión en la red de su lugar de trabajo, pero se admiten otras soluciones, incluida la autenticación de múltiples factores (MFA).
    
- **FortiGate accepts FortiClient and several products from other vendors as remote VPN clients.** // FortiGate acepta FortiClient y varios productos de otros proveedores como clientes de VPN remota.

![[Pasted image 20260312210821.png]]

## **Site-to-site VPNs**

- **A site-to-site VPN allows networks in two different physical locations to reach each other securely.** // Una VPN de sitio a sitio permite que las redes en dos ubicaciones físicas diferentes se comuniquen entre sí de forma segura.
    
- **In site-to-site VPN, either side can initiate the connection.** // En una VPN de sitio a sitio, cualquiera de los dos lados puede iniciar la conexión.
    
- **FortiGate can establish site-to-site VPNs with other FortiGate devices, as well as with devices from other vendors, including cloud service providers like AWS and Azure.** // FortiGate puede establecer VPN de sitio a sitio con otros dispositivos FortiGate, así como con dispositivos de otros proveedores, incluidos proveedores de servicios en la nube como AWS y Azure.
    

### **Extra Information & Context (Información Adicional)**

- **Initiating the connection: Notice the difference! In Remote Access, the user (client) must start the process. In Site-to-Site, both firewalls are "peers" and either can bring up the tunnel.** // Iniciar la conexión: ¡Nota la diferencia! En el Acceso Remoto, el usuario (cliente) debe iniciar el proceso. En Sitio a Sitio, ambos firewalls son "pares" (peers) y cualquiera puede levantar el túnel.
    
- **Interoperability: FortiGate uses standard IPsec protocols, which is why it can talk to AWS, Azure, or even other firewall brands like Cisco or Palo Alto.** // Interoperabilidad: FortiGate utiliza protocolos IPsec estándar, razón por la cual puede comunicarse con AWS, Azure o incluso con otras marcas de firewall como Cisco o Palo Alto.
    


![[Pasted image 20260312210743.png]]

## **Connecting Through VPNs**

- **In both types of VPNs, after the connection is established, the devices in one network can reach the devices in the other network.** // En ambos tipos de VPN, después de establecer la conexión, los dispositivos de una red pueden alcanzar a los dispositivos de la otra red.
    
- **When connected through a VPN, devices in different networks become part of the same logical network.** // Cuando se conectan a través de una VPN, los dispositivos de diferentes redes pasan a formar parte de la misma red lógica.

### **Text from the Image (Texto de la Imagen)**

- **Encrypted VPN Tunnel** // Túnel VPN cifrado.
    
- **Branch Office** // Sucursal / Oficina remota.
    
- **VPN Server** // Servidor VPN (En este caso, los FortiGate).
    
- **Headquarter** // Oficina Central / Sede principal.

### **Extra Information & Context (Información Adicional)**

- **Logical Network: This means that even if the computers are thousands of miles apart physically, they act as if they were on the same local network (LAN). This allows for easy sharing of resources like printers, file servers, and internal applications.** // Red Lógica: Esto significa que, aunque las computadoras estén físicamente a miles de kilómetros de distancia, actúan como si estuvieran en la misma red local (LAN). Esto permite compartir fácilmente recursos como impresoras, servidores de archivos y aplicaciones internas.
    
- **Routing and Policies: For this "logical network" to work, the FortiGate must have specific "Firewall Policies" that allow traffic to flow through the VPN tunnel. Just having the tunnel "up" isn't enough; you must also permit the traffic in the settings.** // Enrutamiento y Políticas: Para que esta "red lógica" funcione, el FortiGate debe tener "Políticas de Firewall" específicas que permitan que el tráfico fluya a través del túnel VPN. No basta con que el túnel esté "activo"; también debes permitir el tráfico en la configuración.

![[Pasted image 20260312223841.png]]

## **Internet Key Exchange (IKE) Protocol**

- **The IKE protocol is used to create the tunnels dynamically.** // El protocolo IKE se utiliza para crear los túneles dinámicamente.
    
- **Regardless of the IPsec VPN type used, the IKE protocol is used to create the tunnels dynamically.** // Independientemente del tipo de VPN IPsec utilizado, el protocolo IKE se utiliza para crear los túneles dinámicamente.
    
- **FortiGate supports the two available versions of IKE: IKEv1 and IKEv2.** // FortiGate admite las dos versiones disponibles de IKE: IKEv1 e IKEv2.
    
- **IKEv1 is still widely used in many VPN deployments.** // IKEv1 todavía se usa ampliamente en muchas implementaciones de VPN.
    
- **IKEv2 includes several security improvements over IKEv1.** // IKEv2 incluye varias mejoras de seguridad sobre IKEv1.
    
- **When using IKEv1, the IPsec VPN process goes through two stages: Phase 1 and Phase 2.** // Al usar IKEv1, el proceso de VPN IPsec pasa por dos etapas: Fase 1 y Fase 2.

### **Extra Information & Context (Información Adicional)**

Aquí te explico por qué estas fases son tan importantes en FortiGate:

- **Phase 1 (Fase 1): In this stage, the two devices (Gateways) authenticate each other and establish a secure channel to negotiate the VPN parameters. If Phase 1 fails, the tunnel will never come up.** // En esta etapa, los dos dispositivos (Gateways) se autentican entre sí y establecen un canal seguro para negociar los parámetros de la VPN. Si la Fase 1 falla, el túnel nunca se levantará.
    
- **Phase 2 (Fase 2): Once the secure channel from Phase 1 is established, Phase 2 negotiates the encryption for the actual data that will travel through the tunnel. You can have multiple Phase 2 tunnels inside a single Phase 1.** // Una vez establecido el canal seguro de la Fase 1, la Fase 2 negocia el cifrado de los datos reales que viajarán por el túnel. Puedes tener múltiples túneles de Fase 2 dentro de una sola Fase 1.
    
- **IKEv2 Advantages: Unlike IKEv1, IKEv2 is more efficient, supports EAP (Extensible Authentication Protocol), and has better "Dead Peer Detection" (DPD) to know if the connection was lost.** // A diferencia de IKEv1, IKEv2 es más eficiente, admite EAP (Protocolo de Autenticación Extensible) y tiene una mejor "Detección de Pares Muertos" (DPD) para saber si se perdió la conexión.
![[Pasted image 20260312224100.png]]
## **IKEv1 Protocol | Phase 1**

- **In Phase 1, the two peer devices authenticate with each other and establish a secure channel that they will use to negotiate the security parameters of Phase 2.** // En la Fase 1, los dos dispositivos pares se autentican entre sí y establecen un canal seguro que utilizarán para negociar los parámetros de seguridad de la Fase 2.
    
- **This first channel acts as the control plane of the VPN connection.** // Este primer canal actúa como el plano de control de la conexión VPN.
    
- **The peers can be configured with several combinations, or proposals.** // Los pares se pueden configurar con varias combinaciones o propuestas.
    
- **Each proposal consists of several security parameters.** // Cada propuesta consta de varios parámetros de seguridad.
    
### **Dialogue from the Image (Diálogo de la Imagen)**

- **I want to connect. My password is 123456, and I want to use AES-128 for encryption, SHA-1 for hashing, and DH group 5.** // Quiero conectarme. Mi contraseña es 123456, y quiero usar AES-128 para cifrado, SHA-1 para hashing y el grupo DH 5.
    
- **OK, your password is good. However, I must use AES-256 for more secure encryption. The rest is fine. Can you use that?** // Bien, tu contraseña es correcta. Sin embargo, debo usar AES-256 para un cifrado más seguro. El resto está bien. ¿Puedes usar eso?
    
- **Yes, I can. Let’s use AES-256, SHA-1 and DH group 5.** // Sí, puedo. Usemos AES-256, SHA-1 y el grupo DH 5.
    
- **Ok! Let’s create this Phase 1 channel before we agree on the Phase 2 parameters.** // ¡De acuerdo! Creemos este canal de Fase 1 antes de acordar los parámetros de la Fase 2.


### **Extra Information & Context (Información Adicional)**

- **Proposal Negotiation: This dialogue represents the "handshake". If the two FortiGates don't have at least one matching proposal (same encryption, hashing, etc.), the VPN will fail with a "no proposal chosen" error.** // Negociación de Propuestas: Este diálogo representa el "saludo de mano" (handshake). Si los dos FortiGates no tienen al menos una propuesta que coincida (mismo cifrado, hashing, etc.), la VPN fallará con un error de "no proposal chosen" (ninguna propuesta elegida).
    
- **Control Plane vs. Data Plane: Think of Phase 1 as a secure "management" tunnel. It doesn't carry your files or emails; it only carries the instructions to build the "Data" tunnel (Phase 2).** // Plano de Control vs. Plano de Datos: Piensa en la Fase 1 como un túnel de "gestión" seguro. No transporta tus archivos o correos; solo transporta las instrucciones para construir el túnel de "Datos" (Fase 2).
    
- **DH Group (Diffie-Hellman): This is a method for securely exchanging cryptographic keys over a public channel. A higher group number usually means a stronger key but more CPU usage.** // Grupo DH (Diffie-Hellman): Este es un método para intercambiar claves criptográficas de forma segura a través de un canal público. Un número de grupo más alto suele significar una clave más fuerte pero más uso de CPU.




![[Pasted image 20260312224326.png]]

![[Pasted image 20260312224402.png]]
![[Pasted image 20260312224425.png]]

## **IKEv1 Protocol Phase 1 Parameters**

- **For a successful Phase 1, the following parameters must match in at least one of the proposals on each peer device:** // Para una Fase 1 exitosa, los siguientes parámetros deben coincidir en al menos una de las propuestas en cada dispositivo par:

### **Key Parameters (Parámetros Clave)**

1. **IKE Mode: Main or Aggressive** // Modo IKE: Principal (Main) o Agresivo (Aggressive).
    
2. **Authentication** // Autenticación (generalmente mediante una clave precompartida o certificados).
    
3. **Encryption Algorithm** // Algoritmo de Cifrado (ej. AES, 3DES).
    
4. **Hashing Algorithm** // Algoritmo de Hashing (ej. SHA-256, MD5).
    
5. **Diffie Helman Group** // Grupo Diffie Helman (determina la fuerza de la clave de cifrado).

### **Important Notes (Notas Importantes)**

- **Other parameters don't need to match because they can be negotiated.** // Otros parámetros no necesitan coincidir porque pueden ser negociados.
    
- **Phase 2 can start only after Phase 1 completes successfully.** // La Fase 2 puede comenzar solo después de que la Fase 1 se complete con éxito.

### **Extra Information & Context (Información Adicional)**

- **Main vs. Aggressive Mode: "Main Mode" is more secure as it hides the identity of the peers during negotiation, but requires more packets. "Aggressive Mode" is faster but less secure. FortiGate usually defaults to Main Mode for better security.** // Modo Main vs. Aggressive: El "Modo Main" es más seguro ya que oculta la identidad de los pares durante la negociación, pero requiere más paquetes. El "Modo Aggressive" es más rápido pero menos seguro. FortiGate suele usar por defecto el Modo Main para mayor seguridad.
    
- **Proposals: A FortiGate can send multiple "proposals" (lists of algorithms). As long as the other side says "I accept one of those", the tunnel stays up. If none match, you'll see a "no proposal chosen" error in the logs.** // Propuestas: Un FortiGate puede enviar múltiples "propuestas" (listas de algoritmos). Mientras el otro lado diga "Acepto una de esas", el túnel se mantiene. Si ninguna coincide, verás un error de "no proposal chosen" en los logs.
![[Pasted image 20260312224815.png]]

## **IKEv1 Protocol | Phase 2**

- **In Phase 2, both peer devices determine which traffic must be sent over the VPN, and how it will be authenticated and encrypted.** // En la Fase 2, ambos dispositivos pares determinan qué tráfico debe enviarse a través de la VPN y cómo se autenticará y cifrará.
    
- **In this phase, a sub-tunnel of the parent Phase 1 tunnel is created.** // En esta fase, se crea un subtúnel del túnel padre de la Fase 1.
    
- **This sub-tunnel acts as the data plane.** // Este subtúnel actúa como el plano de datos.

### **Dialogue from the Image (Diálogo de la Imagen)**

- **For phase 2 I want to use AES256, SHA-1 and DH group 5 for the traffic from my subnet 10 to your subnet 20.** // Para la fase 2 quiero usar AES256, SHA-1 y el grupo DH 5 para el tráfico desde mi subred 10 a tu subred 20.
    
- **OK, I agree with those parameters, and I will use them for the traffic from my subnet 20 to your subnet 10. Let’s finish setting up this VPN.** // Bien, estoy de acuerdo con esos parámetros, y los usaré para el tráfico desde mi subred 20 a tu subred 10. Terminemos de configurar esta VPN.

### **Extra Information & Context (Información Adicional)**

- **Data Plane: This is where your actual information (files, web traffic, etc.) travels. It is protected by the security "rules" negotiated in Phase 1.** // Plano de Datos: Aquí es donde viaja tu información real (archivos, tráfico web, etc.). Está protegida por las "reglas" de seguridad negociadas en la Fase 1.
    
- **Selectors (Subnets): In Phase 2, we define "Selectors" (the subnets). In the example, the FortiGate needs to know that traffic from `10.x.x.x` going to `20.x.x.x` must be encrypted. If the traffic doesn't match these subnets, it won't go through the tunnel.** // Selectores (Subredes): En la Fase 2, definimos los "Selectores" (las subredes). En el ejemplo, el FortiGate necesita saber que el tráfico de la subred `10` hacia la `20` debe cifrarse. Si el tráfico no coincide con estas subredes, no pasará por el túnel.
    
- **Quick Mode: In IKEv1, Phase 2 is also known as "Quick Mode".** // Quick Mode: En IKEv1, la Fase 2 también se conoce como "Quick Mode".

![[Pasted image 20260312225216.png]]


## **IKEv1 Protocol Phase 2 Parameters**

- **For a successful Phase 2 the following parameters must match in at least one proposal on both peers:** // Para una Fase 2 exitosa, los siguientes parámetros deben coincidir en al menos una propuesta en ambos pares:
    
- **Like Phase 1, the peers can be configured with several Phase 2 proposals.** // Al igual que en la Fase 1, los pares se pueden configurar con varias propuestas de Fase 2.
    

---

### **Key Parameters (Parámetros Clave)**

1. **Encryption Algorithm** // Algoritmo de Cifrado (ej. AES, 3DES).
    
2. **Hashing Algorithm** // Algoritmo de Hashing (ej. SHA-256, MD5).
    
3. **Diffie Helman Group (Only if Perfect Forward Secrecy (PFS) is used, which is highly recommended).** // Grupo Diffie Helman (Solo si se utiliza Perfect Forward Secrecy (PFS), lo cual es altamente recomendado).

### **Important Notes (Notas Importantes)**

- **Other parameters don't need to match because they can be negotiated.** // Otros parámetros no necesitan coincidir porque pueden ser negociados.

### **Extra Information & Context (Información Adicional)**

- **Perfect Forward Secrecy (PFS): This is a security feature that ensures that if one specific key is compromised, previous and future keys remain secure. It does this by creating a completely new key for each session instead of deriving it from the master key. In FortiGate, it's a checkbox in the Phase 2 settings.** // Perfect Forward Secrecy (PFS): Es una característica de seguridad que garantiza que, si una clave específica se ve comprometida, las claves anteriores y futuras permanezcan seguras. Lo hace creando una clave completamente nueva para cada sesión en lugar de derivarla de la clave maestra. En FortiGate, es una casilla de verificación en la configuración de la Fase 2.
    
- **Independence from Phase 1: You can use different encryption/hashing algorithms in Phase 2 than you used in Phase 1. For example, Phase 1 could use AES-128 and Phase 2 could use AES-256.** // Independencia de la Fase 1: Puedes usar algoritmos de cifrado/hashing diferentes en la Fase 2 a los que usaste en la Fase 1. Por ejemplo, la Fase 1 podría usar AES-128 y la Fase 2 podría usar AES-256.

![[Pasted image 20260312225413.png]]

## **Configuring IKEv1 Protocol Phase 2**

- **The traffic that is to be protected must be indicated by listing the local and remote subnets that will communicate through the tunnel.** // El tráfico que debe protegerse debe indicarse enumerando las subredes locales y remotas que se comunicarán a través del túnel.
    
- **In a remote access VPN, both subnets are configured on the server side.** // En una VPN de acceso remoto, ambas subredes se configuran en el lado del servidor.
    
- **In a site-to-site VPN, the subnets on each peer must mirror each other.** // En una VPN de sitio a sitio, las subredes de cada par deben ser el espejo (mirror) la una de la otra.

### **Specific Values from the Image (Valores de la Imagen)**

- **Subnet 192.168.2.0/24** // Subred 192.168.2.0/24.
    
- **Subnet 192.168.3.0/24** // Subred 192.168.3.0/24.
    
- **192.168.3.10/24 Client received the IP address from the headquarters.** // 192.168.3.10/24 El cliente recibió la dirección IP de la oficina central.

### **Extra Information & Context (Información Adicional)**

- **The "Mirror" Concept: If FortiGate A has Local: 192.168.2.0 and Remote: 192.168.3.0, then FortiGate B MUST have Local: 192.168.3.0 and Remote: 192.168.2.0. If they aren't exact opposites, Phase 2 will fail.** // El concepto de "Espejo": Si el FortiGate A tiene como Local: 192.168.2.0 y Remota: 192.168.3.0, entonces el FortiGate B DEBE tener como Local: 192.168.3.0 y Remota: 192.168.2.0. Si no son opuestos exactos, la Fase 2 fallará.
    
- **Phase 2 Selectors: These subnets are also called "Proxy IDs" or "Phase 2 Selectors". They define the "Interesting Traffic" that triggers the VPN tunnel.** // Selectores de Fase 2: Estas subredes también se llaman "Proxy IDs" o "Selectores de Fase 2". Definen el "Tráfico Interesante" que activa el túnel VPN.

![[Pasted image 20260312225511.png]]

## **IKEv2 Protocol**

- **IKEv2 was designed with several improvements over IKEv1, both in security and performance.** // IKEv2 fue diseñado con varias mejoras sobre IKEv1, tanto en seguridad como en rendimiento.
    
- **It is the recommended protocol for new IPsec VPN implementations, unless the available hardware does not support it.** // Es el protocolo recomendado para nuevas implementaciones de VPN IPsec, a menos que el hardware disponible no lo admita.
    
- **IKEv2 does not include two phases and is not backward compatible with IKEv1.** // IKEv2 no incluye dos fases y no es compatible con versiones anteriores de IKEv1.

### **Key Features (Características Clave)**

- **Better than IKEv1 in security and performance.** // Mejor que IKEv1 en seguridad y rendimiento.
    
- **Recommended protocol for new IPsec VPN implementation.** // Protocolo recomendado para nuevas implementaciones de VPN IPsec.
    
- **Does not include two phases.** // No incluye dos fases.
    
- **Incompatible with IKEv1.** // Incompatible con IKEv1.

### **Extra Information & Context (Información Adicional)**

- **Simplified Exchange: Although the text says "it does not include two phases," IKEv2 actually combines the negotiation into a more efficient, single-step process (four-message exchange) compared to the multiple steps of IKEv1.** // Intercambio Simplificado: Aunque el texto dice que "no incluye dos fases", IKEv2 en realidad combina la negociación en un proceso único y más eficiente (intercambio de cuatro mensajes) en comparación con los múltiples pasos de IKEv1.
    
- **MOBIKE Support: One of the biggest advantages of IKEv2 is MOBIKE (IKEv2 Mobility and Multihoming Protocol), which allows a VPN session to stay active even if the user changes networks (e.g., switching from Wi-Fi to 5G).** // Soporte MOBIKE: Una de las mayores ventajas de IKEv2 es MOBIKE, que permite que una sesión VPN permanezca activa incluso si el usuario cambia de red (por ejemplo, al pasar de Wi-Fi a 5G).
    
- **Incompatibility: Remember, both ends of the tunnel MUST use the same version. You cannot connect a FortiGate using IKEv1 to another device using IKEv2.** // Incompatibilidad: Recuerda que ambos extremos del túnel DEBEN usar la misma versión. No puedes conectar un FortiGate usando IKEv1 a otro dispositivo usando IKEv2.

![[Pasted image 20260312225714.png]]

## **Benefits of Using IKEv2 Over IKEv1**

- **Reduced Latency: The use of fewer messages reduces the latency and the bandwidth used during the negotiation of the tunnels.** // Latencia Reducida: El uso de menos mensajes reduce la latencia y el ancho de banda utilizado durante la negociación de los túneles.
    
- **Better Reliability: The use of sequence numbers and acknowledgements in messages result in better reliability.** // Mejor Confiabilidad: El uso de números de secuencia y acuses de recibo en los mensajes resulta en una mejor confiabilidad.
    
- **Supports Extensible Authentication Protocol (EAP): Support of EAP adds more flexibility, scalability and interoperability during the authentication process.** // Soporta el Protocolo de Autenticación Extensible (EAP): El soporte de EAP añade más flexibilidad, escalabilidad e interoperabilidad durante el proceso de autenticación.
    
- **Support of PPK: Support of PPK (Post-quantum pre-shared keys).** // Soporte de PPK: Soporte de claves precompartidas post-cuánticas (PPK).
    
- **Support of asymmetric authentication: Support of asymmetric authentication allows the peers to use different authentication methods.** // Soporte de autenticación asimétrica: El soporte de autenticación asimétrica permite que los pares utilicen diferentes métodos de autenticación.
    
- **Support of stronger security algorithms: For example, FortiGate supports PRF-SHA for hashing and AES-GCM for encryption, both with several bit lengths available.** // Soporte de algoritmos de seguridad más fuertes: Por ejemplo, FortiGate admite PRF-SHA para hashing y AES-GCM para cifrado, ambos con varias longitudes de bits disponibles.
    
- **Better resilience against DoS attacks.** // Mejor resiliencia contra ataques de denegación de servicio (DoS).

### **Extra Information & Context (Información Adicional)**

- **Asymmetric Authentication: In IKEv1, both sides had to use the same method (e.g., both use a Pre-shared Key). In IKEv2, one side can use a certificate while the other uses a password, which is very useful for remote workers.** // Autenticación Asimétrica: En IKEv1, ambos lados debían usar el mismo método (ej. ambos clave precompartida). En IKEv2, un lado puede usar un certificado mientras el otro usa una contraseña, lo cual es muy útil para trabajadores remotos.
    
- **Post-quantum pre-shared keys (PPK): This is a future-proofing feature. It protects the VPN traffic against potential future attacks from quantum computers that could break current encryption standards.** // Claves precompartidas post-cuánticas (PPK): Esta es una característica para el futuro. Protege el tráfico VPN contra posibles ataques de computadoras cuánticas que podrían romper los estándares de cifrado actuales.
    
- **AES-GCM: This is a modern encryption mode that is faster and more secure than traditional modes because it provides both confidentiality and data integrity in a single process.** // AES-GCM: Es un modo de cifrado moderno que es más rápido y seguro que los modos tradicionales porque proporciona tanto confidencialidad como integridad de datos en un solo proceso.

![[Pasted image 20260312230356.png]]
## **Encapsulating Security Payload (ESP)**

- **FortiGate firewalls support ESP protocol for the authentication and encryption of VPN traffic.** // Los firewalls FortiGate admiten el protocolo ESP para la autenticación y el cifrado del tráfico VPN.
    
- **ESP provides data encryption, data integrity, and data origin authentication, but it does not provide identity authentication.** // ESP proporciona cifrado de datos, integridad de datos y autenticación del origen de los datos, pero no proporciona autenticación de identidad.
    
- **Identity authentication is provided by IKE during Phase 1 negotiation.** // La autenticación de identidad es proporcionada por IKE durante la negociación de la Fase 1.
    
- **The following table shows some of the most well-known encryption and hashing algorithms supported by ESP in FortiGate.** // La siguiente tabla muestra algunos de los algoritmos de cifrado y hashing más conocidos admitidos por ESP en FortiGate.


### **Encryption and Hashing Comparison (Comparativa de Cifrado y Hashing)**

|**Function**|**Weaker (Más débil)**|**⟶**|**Stronger (Más fuerte)**|
|---|---|---|---|
|**Encryption**|DES|3DES|AES128|
|**Data integrity and authentication**|MD5|SHA-1|SHA256|


### **Extra Information & Context (Información Adicional)**

- **ESP vs. AH: IPsec can use two protocols: AH (Authentication Header) and ESP. AH only provides authentication and integrity, but NOT encryption. ESP is the standard choice because it protects the privacy of the data by encrypting the entire payload.** // ESP vs. AH: IPsec puede usar dos protocolos: AH (Authentication Header) y ESP. AH solo proporciona autenticación e integridad, pero NO cifrado. ESP es la opción estándar porque protege la privacidad de los datos cifrando toda la carga útil (payload).
    
- **Performance Impact: Stronger algorithms like AES-256 or SHA-512 provide better security but require more CPU resources. Modern FortiGate units have hardware acceleration (CP/NP chips) to handle this without losing speed.** // Impacto en el Rendimiento: Los algoritmos más fuertes como AES-256 o SHA-512 brindan mejor seguridad pero requieren más recursos de CPU. Las unidades FortiGate modernas tienen aceleración por hardware (chips CP/NP) para manejar esto sin perder velocidad.

![[Pasted image 20260312230202.png]]

## **VPN Configuration Best Practices (Full Narrator's Context)**

### **1. Update & Security Patches**

- **Ensure your firewalls have the latest updates and security patches installed. VPNs are one of the most preferred targets of cybercriminals. An up-to-date firewall minimizes your risk of becoming a victim of cybercrime.** // Asegúrese de que sus firewalls tengan las últimas actualizaciones y parches de seguridad instalados. Las VPN son uno de los objetivos preferidos de los ciberdelincuentes. Un firewall actualizado minimiza el riesgo de convertirse en víctima del cibercrimen.
    

### **2. Performance & Hardware Offloading (CPs)**

- **Use encryption and hashing levels that meet your requirements. Many FortiGate models include specialized content processors (CPs) that can offload the encryption and decryption operations from the CPU.** // Use niveles de cifrado y hashing que cumplan con sus requisitos. Muchos modelos de FortiGate incluyen procesadores de contenido especializados (CPs) que pueden descargar las operaciones de cifrado y descifrado de la CPU.
    
- **If your device does not have this capability, remember that the use of stronger encryption and hashing algorithms requires more CPU resources and that can affect device performance.** // Si su dispositivo no tiene esta capacidad, recuerde que el uso de algoritmos de cifrado y hashing más fuertes requiere más recursos de la CPU y eso puede afectar el rendimiento del dispositivo.
    

### **3. Peer Compatibility**

- **Verify both peers support the same IPsec features. Older devices, or devices from other vendors, may not support the same levels of encryption, hashing and so on. You should verify which IPsec features are supported since they must match.** // Verifique que ambos pares admitan las mismas características de IPsec. Los dispositivos más antiguos, o de otros proveedores, pueden no admitir los mismos niveles de cifrado, hashing, etc. Debe verificar qué funciones de IPsec son compatibles, ya que deben coincidir.
    

### **4. Ports & NAT Traversal (Important!)**

- **Ensure the needed ports are open in all the firewalls in the traffic path. IKE uses UDP port 500 by default, and UDP port 4500 when the VPN device is behind network address translation (NAT).** // Asegúrese de que los puertos necesarios estén abiertos en todos los firewalls en la ruta del tráfico. IKE usa el puerto UDP 500 por defecto, y el puerto UDP 4500 cuando el dispositivo VPN está detrás de una traducción de direcciones de red (NAT).
    
- **A firewall blocking these ports, such as those from a service provider, will prevent the establishment of IPsec VPN connections.** // Un firewall que bloquee estos puertos, como los de un proveedor de servicios, impedirá el establecimiento de conexiones VPN IPsec.
    

### **5. IKEv1 Negotiation Modes**

- **Select the proper mode when using IKEv1. Main mode is more secure but slower. This is the FortiGate default for site-to-site VPNs. Aggressive mode is less secure but faster. This is the FortiGate default for remote access VPNs.** // Seleccione el modo adecuado al usar IKEv1. El modo Main es más seguro pero más lento. Este es el valor predeterminado de FortiGate para VPN de sitio a sitio. El modo Aggressive es menos seguro pero más rápido. Este es el valor predeterminado de FortiGate para VPN de acceso remoto.
    

---

### **Extra Technical Details from the Video (Lo que no estaba en las diapositivas)**

- **The narrator emphasizes that VPNs are high-value targets because they are the "door" to the internal network. That's why keeping the firmware (FortiOS) updated is critical.** // El narrador enfatiza que las VPN son objetivos de alto valor porque son la "puerta" a la red interna. Por eso, mantener el firmware (FortiOS) actualizado es crítico.
    
- **NAT Traversal Detail: Port 4500 is only triggered when the FortiGate detects a NAT device in the path. If it's a "clean" path with public IPs on both ends, it will stay on port 500.** // Detalle de NAT Traversal: El puerto 4500 solo se activa cuando el FortiGate detecta un dispositivo NAT en la ruta. Si es una ruta "limpia" con IPs públicas en ambos extremos, se mantendrá en el puerto 500.

![[Pasted image 20260312230922.png]]
![[Pasted image 20260312230737.png]]
![[Pasted image 20260312230758.png]]![[Pasted image 20260312230829.png]]
![[Pasted image 20260312230848.png]]
![[Pasted image 20260312230907.png]]

## **Configuring IPsec VPNs**

- **FortiGate provides an intuitive wizard to help you easily configure IPsec VPNs.** // FortiGate proporciona un asistente intuitivo para ayudarte a configurar fácilmente las VPN de IPsec.
    
- **The wizard includes several templates with security settings that are appropriate for the most common scenarios.** // El asistente incluye varias plantillas con configuraciones de seguridad adecuadas para los escenarios más comunes.
    
- **The security settings include various proposals combining different levels of AES for encryption and SHA-2 for hashing.** // Las configuraciones de seguridad incluyen varias propuestas que combinan diferentes niveles de AES para el cifrado y SHA-2 para el hashing.
    
- **If for legal or compliance reasons you are required to use specific security parameters, you can create a custom tunnel.** // Si por razones legales o de cumplimiento se requiere el uso de parámetros de seguridad específicos, puedes crear un túnel personalizado.
    
- **This will allow you to select the specific settings that meet your needs.** // Esto te permitirá seleccionar las configuraciones específicas que se adapten a tus necesidades.
    
- **Another option is to convert a tunnel created with a template into a custom tunnel so you can edit all its settings.** // Otra opción es convertir un túnel creado con una plantilla en un túnel personalizado para que puedas editar todas sus configuraciones.

### **Wizard Steps (Pasos del Asistente)**

1. **VPN Setup** // Configuración de la VPN (Nombre y tipo).
    
2. **Authentication** // Autenticación (Claves y certificados).
    
3. **Policy & Routing** // Políticas y Enrutamiento (Quién puede pasar y por dónde).
    
4. **Review Settings** // Revisar configuraciones (Resumen final).

### **Specific Options from the Image (Opciones de la Imagen)**

- **Template type: Site to Site, Hub-and-Spoke, Remote Access, Custom.** // Tipo de plantilla: Sitio a Sitio, Hub-and-Spoke, Acceso Remoto, Personalizado.
    
- **NAT configuration: Not NAT between sites, This site is behind NAT, The remote site is behind NAT.** // Configuración de NAT: Sin NAT entre sitios, Este sitio está detrás de NAT, El sitio remoto está detrás de NAT.
    
- **Remote device type: FortiGate, Cisco.** // Tipo de dispositivo remoto: FortiGate, Cisco.

### **Extra Information & Context (Información Adicional)**

- **The "Cisco" Option: Even though it's a Fortinet course, they include a Cisco template because it's a very common scenario to connect a FortiGate with a Cisco router. This template pre-configures the specific settings Cisco devices usually expect.** // La opción "Cisco": Aunque es un curso de Fortinet, incluyen una plantilla de Cisco porque es un escenario muy común conectar un FortiGate con un router Cisco. Esta plantilla preconfigura los ajustes específicos que suelen esperar los dispositivos Cisco.
    
- **Template vs. Custom: Use templates for speed and to avoid errors in standard setups. Use "Custom" when you need granular control, like using IKEv2 with very specific algorithms required by your company's security policy.** // Plantilla vs. Personalizado: Usa plantillas por rapidez y para evitar errores en configuraciones estándar. Usa "Personalizado" cuando necesites un control granular, como usar IKEv2 con algoritmos muy específicos requeridos por la política de seguridad de tu empresa.

![[Pasted image 20260312231425.png]]

## **Monitoring VPN Tunnels**

- **The FortiGate GUI also makes it very easy for you to monitor VPN tunnels.** // La interfaz gráfica de usuario (GUI) de FortiGate también te facilita mucho el monitoreo de los túneles VPN.
    
- **Not only can you check whether a tunnel status is up or down, details about traffic volume and even the status of both phase 1 and phase 2 are also shown.** // No solo puedes verificar si el estado de un túnel está activo (up) o inactivo (down), sino que también se muestran detalles sobre el volumen de tráfico e incluso el estado de las fases 1 y 2.
    
- **This can be very helpful while troubleshooting.** // Esto puede ser muy útil durante la resolución de problemas.

### **Troubleshooting Example from the Video (Ejemplo de Resolución de Problemas)**

- **For example, if only the phase 2 tunnel is not working, it means that the peer devices were able to create the phase 1 tunnel.** // Por ejemplo, si solo el túnel de fase 2 no está funcionando, significa que los dispositivos pares pudieron crear el túnel de fase 1.
    
- **Knowing this means that you can discard lack of connectivity as the reason for the failure.** // Saber esto significa que puedes descartar la falta de conectividad como la razón de la falla.
    
- **You can proceed to double check that the parameters were configured correctly on both devices and that they include at least one matching proposal.** // Puedes proceder a verificar nuevamente que los parámetros se configuraron correctamente en ambos dispositivos y que incluyen al menos una propuesta que coincida.

### **GUI Elements from the Image (Elementos de la Interfaz)**

- **Bring Up / Bring Down:** // Levantar / Bajar (el túnel manualmente).
    
- **Reset Statistics:** // Reiniciar estadísticas.
    
- **Incoming Data / Outgoing Data:** // Datos entrantes / Datos salientes (muestra el volumen de tráfico).
    
- **Phase 1 / Phase 2 Selectors:** // Selectores de Fase 1 y Fase 2 (indicadores de estado individuales).

### **Extra Information & Context (Información Adicional)**

- **Traffic Volume (kb): If you see data going out but nothing coming back (Incoming Data is 0), you probably have a routing issue or a firewall policy on the remote side blocking the traffic.** // Volumen de tráfico (kb): Si ves datos saliendo pero nada regresando (Incoming Data es 0), probablemente tengas un problema de enrutamiento o una política de firewall en el lado remoto bloqueando el tráfico.
    
- **Green Arrow (Up) vs. Red Arrow (Down): Always check the Phase 2 status specifically. Sometimes Phase 1 is "Up" (green), but Phase 2 is "Down" (red), which means the connection is established but no data can pass due to a parameter mismatch (like the "mirror" issue we saw before).** // Flecha verde (Up) vs. Flecha roja (Down): Siempre verifica específicamente el estado de la Fase 2. A veces la Fase 1 está "Up" (verde), pero la Fase 2 está "Down" (roja), lo que significa que la conexión se estableció pero no pueden pasar datos por un error en los parámetros (como el problema de "espejo" que vimos antes).

![[Pasted image 20260312231549.png]]

### Lab simulation
![[Pasted image 20260312232313.png]]

![[Pasted image 20260312232644.png]]

![[Pasted image 20260312232717.png]]

