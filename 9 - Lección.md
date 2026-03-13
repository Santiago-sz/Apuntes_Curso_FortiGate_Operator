### Controlling Applications Access
![[Pasted image 20260311165243.png]]

##  Learning Objectives // Objetivos de Aprendizaje

- **Understand application control.** // **Comprender el control de aplicaciones:** Entender cómo el firewall identifica y gestiona el tráfico basándose en la aplicación específica (como Facebook, WhatsApp o BitTorrent) y no solo en puertos o protocolos.
    
- **Explain how FortiGate application control works to limit access.** // **Explicar cómo funciona el control de aplicaciones de FortiGate para limitar el acceso:** Conocer el mecanismo de inspección profunda de paquetes que permite permitir, bloquear o restringir funciones específicas dentro de una aplicación (por ejemplo, permitir ver Facebook pero bloquear el chat).
    
- **Configure FortiGate application control.** // **Configurar el control de aplicaciones de FortiGate:** Aprender a crear perfiles de sensores de aplicaciones, seleccionar categorías y aplicar estas políticas a las reglas de firewall correspondientes.
    
- **Monitor FortiGate application control.** // **Monitorear el control de aplicaciones de FortiGate:** Utilizar los logs y las herramientas de visualización (como FortiView) para auditar qué aplicaciones se están usando en la red y detectar posibles usos no autorizados o riesgosos.

### What is Application Control?
**Application control helps improve security and meet compliance standards in the traffic flow of network applications.** 
El control de aplicaciones ayuda a mejorar la seguridad y cumplir con los estándares de cumplimiento en el flujo de tráfico de las aplicaciones de red.

**To improve security and meet compliance standards, the application control capability in FortiGate helps enforce the acceptable use and resulting traffic flow of network applications, as defined in a policy.** 
Para mejorar la seguridad y cumplir con los estándares de cumplimiento, la capacidad de control de aplicaciones en FortiGate ayuda a aplicar el uso aceptable y el flujo de tráfico resultante de las aplicaciones de red, tal como se define en una política.
![[Pasted image 20260311165742.png]]

### Functions of Application Control
**Application control can identify network traffic that is generated from specific applications and take the appropiate actions, such as monitor and block traffic or apply traffic shaping for all or specific set of users of firewal policy.** 
El control de aplicaciones puede identificar el tráfico de red generado por aplicaciones específicas y tomar las acciones apropiadas, como monitorear y bloquear el tráfico o aplicar modelado de tráfico para todos los usuarios o un conjunto específico de usuarios de la política de firewall.
![[Pasted image 20260311170020.png]]

**Being able to control the traffic flow of network applications may not be a priority requirement within traditional client-server architecture that uses a defined connection protocol over a standard port number. However, the need to control application traffic is becoming increasingly relavant within peer-to-peer architecture wherein many servers need to send traffic using dynamic ports, such as bitTorrent.** 
Controlar el flujo de tráfico de las aplicaciones de red puede no ser una prioridad en la arquitectura cliente-servidor tradicional, que utiliza un protocolo de conexión definido a través de un número de puerto estándar. Sin embargo, la necesidad de controlar el tráfico de las aplicaciones cobra cada vez mayor relevancia en la arquitectura peer-to-peer, donde muchos servidores necesitan enviar tráfico mediante puertos dinámicos, como BitTorrent.
![[Pasted image 20260311170351.png]]

### Controlling Application Access
**Peer-to-peer protocols use ecasive techniques to bypass traditional firewall policies.**
**Therefore, FortiGate application control involves the matching of known patterns to the transmission patterns of the application.**
**The database for application control signatures is provided by FortiGuard labs. The traffic analysis is performed torough the ips engine, which uses flow-based inspection. So, the pattern match is performed directly in the entire byte stream of the packet, independently of protocol or port number.** 
Los protocolos punto a punto utilizan técnicas de evasión para eludir las políticas de firewall tradicionales.
Por lo tanto, el control de aplicaciones de FortiGate implica la comparación de patrones conocidos con los patrones de transmisión de la aplicación.
La base de datos de firmas de control de aplicaciones es proporcionada por FortiGuard Labs. El análisis de tráfico se realiza mediante el motor IPS, que utiliza inspección basada en flujo. De esta forma, la comparación de patrones se realiza directamente en todo el flujo de bytes del paquete, independientemente del protocolo o el número de puerto.

![[Pasted image 20260311171123.png]]

### Aplication Control Settings

**In the Application Control profile, you can configure the application control settings, that must be applied afterwards in the firewall policy.**
En el perfil de Control de aplicaciones, puede configurar los ajustes de control de aplicaciones que se deben aplicar posteriormente en la política de firewall.

![[Pasted image 20260311171327.png]]

In the Application Control profile, the application signatures are grouped by category, and you can set each category to monitor, allow block or quarantine. 

![[Pasted image 20260311171607.png]]

**To provide mare granularity, you can configure each application signature or group of application signatures specifically using the override option.** 
**For example, the override option allows you to block Facebook apps while still allowing users to collaborate using facebook chat** 
Para mayor granularidad, puede configurar cada firma de aplicación o grupo de firmas de aplicaciones específicamente mediante la opción de anulación.
Por ejemplo, la opción de anulación permite bloquear aplicaciones de Facebook y, al mismo tiempo, permitir que los usuarios colaboren mediante el chat de Facebook.

![[Pasted image 20260311171823.png]]

### Configuring Application Control
**Firts, create an application control profile, or modify a preconfigure one.**
En primer lugar, cree un perfil de control de aplicación o modifique uno preconfigurado.
![[Pasted image 20260311172229.png]]

**Second, modify action in the application categories or configure application override.**
En segundo lugar, modifique la acción en las categorías de la aplicación o configure la anulación de la aplicación.
![[Pasted image 20260311172241.png]]

**Thir, select the correct application control profile in the firewall policy.**
En tercer lugar, seleccione el perfil de control de aplicación correcto en la política de firewall.
![[Pasted image 20260311172257.png]]

**Fourth, verify the configuration by attempting to acces the corresponding application.** 
En cuarto lugar, verifique la configuración intentando acceder a la aplicación correspondiente.
![[Pasted image 20260311172311.png]]

**Finaly, use FortiGate logs to monitor applications access limitation.** 
Por último, utilice los registros de FortiGate para supervisar la limitación de acceso a las aplicaciones.
![[Pasted image 20260311172325.png]]

### Lab Simulation
![[Pasted image 20260311172859.png]]
![[Pasted image 20260311173211.png]]