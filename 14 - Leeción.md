![[Pasted image 20260313150232.png]]

## High Availability (HA) en FortiGate

**FortiGate High Availability (HA) is a feature that allows multiple FortiGate firewalls to work together as a cluster, providing redundancy, improving network reliability, and minimizing downtime.** // El High Availability (HA) de FortiGate es una función que permite a múltiples firewalls FortiGate trabajar juntos como un clúster, proporcionando redundancia, mejorando la confiabilidad de la red y minimizando el tiempo de inactividad.

**If one FortiGate device in the cluster goes offline due to hardware problems, connectivity issues, or scheduled maintenance, another unit automatically takes over to ensure continuous traffic flow.** // Si un dispositivo FortiGate en el clúster se desconecta debido a problemas de hardware, problemas de conectividad o mantenimiento programado, otra unidad toma el control automáticamente para garantizar un flujo de tráfico continuo.

**FortiGate HA maintains ongoing security enforcement and connectivity by synchronizing configuration and session data between devices in the cluster.** // El HA de FortiGate mantiene la aplicación de seguridad y la conectividad de manera continua sincronizando la configuración y los datos de sesión entre los dispositivos del clúster.

**This makes it especially valuable for organizations that require high uptime and fault tolerance in their network infrastructure.** // Esto lo hace especialmente valioso para organizaciones que requieren un alto tiempo de actividad y tolerancia a fallos en su infraestructura de red.

### Información Adicional y Análisis de la Diapositiva

Aquí te agrego algunos puntos clave que se observan en la imagen y conceptos fundamentales de FortiGate que no se mencionaron explícitamente en el audio:

- **HA Cluster: In the image, you can see two FortiGate units inside a grey box labeled "HA Cluster." This represents that, logically, the network sees them as a single entity.** // Clúster HA: En la imagen, puedes ver dos unidades FortiGate dentro de un cuadro gris etiquetado como "HA Cluster". Esto representa que, lógicamente, la red los ve como una sola entidad.
    
- **Active-Passive vs. Active-Active: Although not detailed in the video, FortiGate HA can operate in "Active-Passive" (one works, the other waits) or "Active-Active" (both process traffic). In the diagram, the solid line shows the active path, while the dotted line shows the standby path.** // Activo-Pasivo vs. Activo-Activo: Aunque no se detalla en el video, el HA de FortiGate puede operar en "Activo-Pasivo" (uno trabaja, el otro espera) o "Activo-Activo" (ambos procesan tráfico). En el diagrama, la línea sólida muestra la ruta activa, mientras que la punteada muestra la ruta de espera.
    
- **Heartbeat Links: For HA to work, the devices must be physically connected to each other via "heartbeat" links to monitor each other's status.** // Enlaces Heartbeat: Para que el HA funcione, los dispositivos deben estar conectados físicamente entre sí mediante enlaces de "latido" (heartbeat) para monitorear el estado del otro.
    
- **Failover: This is the automatic process where the secondary unit becomes the primary when a failure is detected.** // Failover: Este es el proceso automático donde la unidad secundaria se convierte en la principal cuando se detecta una falla.

![[Pasted image 20260313150352.png]]


## Why Use HA? // ¿Por qué usar HA?

**FortiGate HA provides several key benefits:** // El HA de FortiGate proporciona varios beneficios clave:
### 1. Redundancy // Redundancia

**The automatic failover process eliminates the risk of a single point of failure and maintains business continuity during unexpected outages and system upgrades.** // El proceso de failover automático elimina el riesgo de un punto único de falla y mantiene la continuidad del negocio durante interrupciones inesperadas y actualizaciones del sistema.

**Redundancy maintains business continuity during unexpected outages and system upgrades.** // La redundancia mantiene la continuidad del negocio durante interrupciones inesperadas y actualizaciones del sistema.

### 2. Configuration and session synchronization // Sincronización de configuración y sesiones

**Relevant configuration data is synchronized across all cluster members to ensure seamless failover.** // Los datos de configuración relevantes se sincronizan en todos los miembros del clúster para garantizar un failover (conmutación por error) sin interrupciones.

**Session information can also be shared to allow ongoing traffic to continue without interruption after a failover.** // La información de la sesión también se puede compartir para permitir que el tráfico en curso continúe sin interrupciones después de un failover.

### 3. Simplified management // Gestión simplificada

**All cluster-related configuration changes made on the primary unit are synchronized with all other members.** // Todos los cambios de configuración relacionados con el clúster realizados en la unidad primaria se sincronizan con todos los demás miembros.


### Información Adicional y Análisis de la Imagen

- **Single Point of Failure: This refers to any part of a system that, if it fails, will stop the entire system from working. HA prevents the firewall from being that point.** // Punto único de falla: Se refiere a cualquier parte de un sistema que, si falla, detendrá el funcionamiento de todo el sistema. El HA evita que el firewall sea ese punto.
    
- **Seamless Failover: This means the user doesn't notice when the secondary unit takes over. Because sessions are synchronized, a video call or a file download shouldn't drop.** // Failover sin interrupciones: Esto significa que el usuario no nota cuando la unidad secundaria toma el control. Debido a que las sesiones están sincronizadas, una videollamada o una descarga de archivos no debería cortarse.
    
- **Primary vs. Secondary: In the "Simplified management" icon, you can see one large FortiGate pointing to others. This illustrates that you only need to configure the "Primary" (or Master) unit, and it will push those settings to the "Secondary" (or Slave) units automatically.** // Primario vs. Secundario: En el icono de "Gestión simplificada", puedes ver un FortiGate grande apuntando a otros. Esto ilustra que solo necesitas configurar la unidad "Primaria" (o Maestra), y esta enviará esos ajustes a las unidades "Secundarias" (o Esclavas) automáticamente.

![[Pasted image 20260313150612.png]]


## How Does HA Work? // ¿Cómo funciona el HA?
### Layer 1: Cluster Creation and Roles // Capa 1: Creación del clúster y roles

**During cluster creation and failover, the HA cluster elects a device to serve as the primary. The primary election process also occurs during a failover.** // Durante la creación del clúster y el failover, el clúster HA elige un dispositivo para que actúe como primario. El proceso de elección del primario también ocurre durante un failover.

**By default, the first device added to the cluster assumes the primary role. The primary device manages cluster operations and processes traffic.** // Por defecto, el primer dispositivo añadido al clúster asume el rol primario. El dispositivo primario gestiona las operaciones del clúster y procesa el tráfico.

**All configuration changes made on the primary are automatically pushed to the secondary. All other devices are designated as secondary, with roles that vary depending on the HA mode in use.** // Todos los cambios de configuración realizados en el primario se envían automáticamente al secundario. Todos los demás dispositivos se designan como secundarios, con roles que varían según el modo de HA en uso.

**Once set up, device members communicate using heartbeat interfaces to monitor cluster health. These interfaces detect failures quickly and initiate failover when they occur.** // Una vez configurados, los miembros del dispositivo se comunican mediante interfaces "heartbeat" para monitorear la salud del clúster. Estas interfaces detectan fallas rápidamente e inician el failover cuando ocurren.

### Layer 2: Primary Election Process (Standard) // Capa 2: Proceso de elección del primario (Estándar)

**By default, the primary device is selected by comparing several parameters among the cluster members, in the following order:** // Por defecto, el dispositivo primario se selecciona comparando varios parámetros entre los miembros del clúster, en el siguiente orden:

1. **Monitored Interfaces: The device with the highest number of monitored interfaces in an UP status (Unit with fewest failed monitored interfaces becomes primary).** // Interfaces monitoreadas: El dispositivo con el mayor número de interfaces monitoreadas en estado "UP" (La unidad con menos interfaces monitoreadas fallidas se convierte en primaria).
    
2. **Uptime: The device with the highest HA uptime, by at least 5 minutes.** // Tiempo de actividad (Uptime): El dispositivo con el mayor tiempo de actividad en HA, por al menos 5 minutos.
    
3. **Priority: The device with the highest priority.** // Prioridad: El dispositivo con la prioridad más alta.
    
4. **Serial Number: The device with the highest serial number.** // Número de serie: El dispositivo con el número de serie más alto.

### Layer 3: The Override Option // Capa 3: La opción Override

**Optionally, you can enable the override option to have the cluster check the priority value before the HA uptime. This makes it easy to specify which device should be the primary by giving it the highest priority value.** // Opcionalmente, puedes habilitar la opción "override" para que el clúster verifique el valor de prioridad antes que el tiempo de actividad (uptime). Esto facilita especificar qué dispositivo debe ser el primario dándole el valor de prioridad más alto.

**A disadvantage of this option is that if the primary temporarily becomes unavailable, it will trigger a failover process twice: once when it goes down and again when it comes back online.** // Una desventaja de esta opción es que si el primario queda no disponible temporalmente, activará un proceso de failover dos veces: una cuando se cae y otra cuando vuelve a estar en línea.

### Información Adicional y Análisis de las Imágenes

- **Heartbeat Traffic: In Layer 1, the small gear icons between FortiGates represent the "Heartbeat" traffic. This is non-routable traffic used only for cluster sync.** // Tráfico Heartbeat: En la Capa 1, los iconos de engranajes pequeños entre los FortiGates representan el tráfico "Heartbeat". Es tráfico no enrutable usado solo para la sincronización del clúster.
    
- **The 5-Minute Rule: In Layer 2, for Uptime to be the deciding factor, there must be a difference of at least 5 minutes. If the difference is smaller, it moves to the next criteria (Priority).** // La regla de los 5 minutos: En la Capa 2, para que el Uptime sea el factor decisivo, debe haber una diferencia de al menos 5 minutos. Si la diferencia es menor, pasa al siguiente criterio (Prioridad).
    
- **Override Command: The CLI snippet shown in Layer 3 is crucial: `set override enable`. Without this, Priority is almost never used because Uptime usually breaks the tie first.** // Comando Override: El fragmento de CLI mostrado en la Capa 3 es crucial: `set override enable`. Sin esto, la Prioridad casi nunca se usa porque el Uptime suele romper el empate primero.
    
- **Flapping Risk: As mentioned in the video, with `override enable`, if a Primary reboots, it will "fight" to take back its position immediately upon startup, causing a second brief interruption (preemption).** // Riesgo de Flapping: Como se menciona en el video, con `override enable`, si un Primario se reinicia, "luchará" por recuperar su posición inmediatamente al arrancar, causando una segunda interrupción breve (preemption).
![[Pasted image 20260313151114.png]]
![[Pasted image 20260313151055.png]]
![[Pasted image 20260313151045.png]]

## Protocols Used in an HA Cluster // Protocolos utilizados en un clúster HA

**At the core of FortiGate HA is the FortiGate Clustering Protocol (FGCP).** // En el núcleo del HA de FortiGate se encuentra el Protocolo de Clúster de FortiGate (FGCP).

**FGCP manages member discovery, elects the primary FortiGate unit, synchronizes data among members, and monitors their health.** // El FGCP gestiona el descubrimiento de miembros, elige la unidad FortiGate primaria, sincroniza los datos entre los miembros y monitorea su salud.

**It performs all these tasks through the configured heartbeat interfaces.** // Realiza todas estas tareas a través de las interfaces "heartbeat" (latido) configuradas.

**FGCP also assigns virtual MAC addresses to each primary unit interface.** // El FGCP también asigna direcciones MAC virtuales a cada interfaz de la unidad primaria.

**When a failover occurs, the required MAC addresses are forwarded to the new primary unit. This ensures that clients don't need to update their ARP tables, reducing downtime and packet loss.** // Cuando ocurre un failover, las direcciones MAC requeridas se reenvían a la nueva unidad primaria. Esto garantiza que los clientes no necesiten actualizar sus tablas ARP, reduciendo el tiempo de inactividad y la pérdida de paquetes.

**You can enable session pickup to synchronize the TCP session table from the primary unit to all cluster members.** // Puedes habilitar el "session pickup" (recogida de sesión) para sincronizar la tabla de sesiones TCP desde la unidad primaria a todos los miembros del clúster.

**If the primary fails, the newly elected primary resumes those sessions from its synchronized table, ensuring minimal disruption to active TCP connections.** // Si la unidad primaria falla, la nueva primaria elegida reanuda esas sesiones desde su tabla sincronizada, asegurando una interrupción mínima en las conexiones TCP activas.

**Additional configuration is required to synchronize non-TCP traffic.** // Se requiere una configuración adicional para sincronizar el tráfico que no sea TCP.

### Información Adicional y Análisis de la Imagen

- **Virtual MAC Address: This is a "trick" used by FortiGate. When a failure occurs, the secondary unit "inherits" the same MAC address as the primary. This way, the rest of the network (switches and routers) doesn't even realize the hardware has changed.** // Dirección MAC Virtual: Este es un "truco" que usa FortiGate. Cuando ocurre una falla, la unidad secundaria "hereda" la misma dirección MAC que tenía la primaria. De esta forma, el resto de la red (switches y routers) ni siquiera se entera de que el hardware cambió.
    
- **Session Pickup: By default, if a firewall fails, active sessions (like a file transfer) might drop. Enabling `set session-pickup enable` (as shown in the CLI box) ensures the secondary unit "knows" about all open connections and can take over without the user losing their connection.** // Session Pickup: Por defecto, si un firewall falla, las sesiones activas (como una transferencia de archivos) podrían caerse. Habilitar `set session-pickup enable` (como se ve en el cuadro de comandos) asegura que la unidad secundaria "conozca" todas las conexiones abiertas y pueda tomarlas sin que el usuario pierda su conexión.
    
- **FGCP (FortiGate Clustering Protocol): It's important to remember this acronym for the exam. It uses port 703 (UDP) for heartbeat and 23 (TCP) for synchronization, although it usually runs on a dedicated link.** // FGCP (FortiGate Clustering Protocol): Es importante recordar estas siglas para el examen. Utiliza el puerto 703 (UDP) para el heartbeat y el 23 (TCP) para la sincronización, aunque generalmente corre por un enlace dedicado.
![[Pasted image 20260313151313.png]]

## What information is synchronized? // ¿Qué información se sincroniza?

**Device members synchronize all the information necessary for the cluster to function properly.** // Los miembros del dispositivo sincronizan toda la información necesaria para que el clúster funcione correctamente.

**The table on this slide displays which information is synchronized and which is not.** // La tabla de esta diapositiva muestra qué información se sincroniza y cuál no.

### Synchronized // Sincronizado

- **Cluster configuration settings (with some exceptions)** // Ajustes de configuración del clúster (con algunas excepciones).
    
- **FIB entries** // Entradas de la FIB (Forwarding Information Base - tabla de reenvío).
    
- **DHCP leases** // Concesiones (leases) de DHCP.
    
- **ARP table** // Tabla ARP.
    
- **FortiGuard definitions** // Definiciones de FortiGuard (como firmas de IPS o antivirus).
    
- **IPsec tunnel SAs** // SAs (Security Associations) de túneles IPsec.
    
- **Information about current sessions (if enabled)** // Información sobre las sesiones actuales (si está habilitado).
    
- **Monitored interfaces** // Interfaces monitoreadas.

### Not Synchronized // No sincronizado

- **Monitored interfaces** // Interfaces monitoreadas. _(Nota: Aparece en ambas listas porque, aunque el estado se conoce, la configuración local de monitoreo es individual)._
    
- **Dashboard widgets** // Widgets del tablero de control (la interfaz gráfica personalizada).
    
- **HA override configuration (disabled or enabled)** // Configuración de "override" de HA (habilitado o deshabilitado).
    
- **HA device priority value** // Valor de prioridad del dispositivo HA.
    
- **HA management interface settings** // Ajustes de la interfaz de administración de HA.
    
- **In-band HA management interface** // Interfaz de administración de HA "en banda" (in-band).
    
- **All licenses, except FortiToken licenses** // Todas las licencias, excepto las licencias de FortiToken.
    
- **Cache (web filtering, email filtering, web cache)** // Caché (filtrado web, filtrado de correo, caché web).

### Información Adicional y Análisis de la Imagen

- **Licensing:** It's a common exam question: **Most licenses are NOT synchronized.** Each FortiGate must have its own licenses for Support, UTM, etc. Only FortiTokens are shared across the cluster. // Licencias: Es una pregunta común de examen: **La mayoría de las licencias NO se sincronizan.** Cada FortiGate debe tener sus propias licencias de Soporte, UTM, etc. Solo los FortiTokens se comparten en el clúster.
    
- **Individual Identity:** Notice that **Priority** and **Override** are not synchronized. This is logical because if they were, both devices would always have the same priority, making the election process impossible. // Identidad individual: Nota que la **Prioridad** y el **Override** no se sincronizan. Esto es lógico porque, si lo hicieran, ambos dispositivos siempre tendrían la misma prioridad, haciendo imposible el proceso de elección.
    
- **FIB vs. Routing Table:** While the Routing Table (RIB) is part of the config, the **FIB** (the table the CPU actually uses to move packets) is synchronized to ensure that when a failover happens, the new primary knows exactly where to send traffic immediately. // FIB vs. Tabla de enrutamiento: Mientras que la tabla de enrutamiento (RIB) es parte de la configuración, la **FIB** (la tabla que la CPU realmente usa para mover paquetes) se sincroniza para asegurar que cuando ocurra un failover, el nuevo primario sepa exactamente a dónde enviar el tráfico de inmediato.

![[Pasted image 20260313151800.png]]

## HA Modes // Modos de HA

**There are two HA operation modes available: active-passive (AP) and active-active (AA).** // Hay dos modos de operación de HA disponibles: activo-pasivo (AP) y activo-activo (AA).

### Active-Passive (AP) // Activo-Pasivo (AP)

**In active-passive mode, the primary device handles all traffic, while the secondary devices remain in standby mode.** // En el modo activo-pasivo, el dispositivo primario maneja todo el tráfico, mientras que los dispositivos secundarios permanecen en modo de espera (standby).

**If the primary fails, a new primary is elected from the available secondary devices.** // Si el primario falla, se elige un nuevo primario de entre los dispositivos secundarios disponibles.

### Active-Active (AA) // Activo-Activo (AA)

**In active-active mode, all devices process traffic simultaneously.** // En el modo activo-activo, todos los dispositivos procesan el tráfico de forma simultánea.

**The primary device assigns and distributes supported sessions to the secondary devices.** // El dispositivo primario asigna y distribuye las sesiones compatibles a los dispositivos secundarios.

**This is the recommended option for high-throughput environments because, in addition to the redundancy achieved, traffic is distributed evenly among all cluster members.** // Esta es la opción recomendada para entornos de alto rendimiento porque, además de la redundancia lograda, el tráfico se distribuye equitativamente entre todos los miembros del clúster.

### Información Adicional y Análisis de la Imagen

- **Resource Usage: In AP mode, the secondary unit is "wasted" in terms of processing power until a failure occurs. In AA mode, you utilize the CPU/RAM of all units.** // Uso de recursos: En el modo AP, la unidad secundaria se "desperdicia" en términos de potencia de procesamiento hasta que ocurre una falla. En el modo AA, utilizas la CPU/RAM de todas las unidades.
    
- **Load Balancing: It’s important to note that even in Active-Active, the Primary unit still receives all traffic first and then decides which sessions to offload to the secondary units.** // Balanceo de carga: Es importante notar que incluso en Activo-Activo, la **unidad Primaria sigue recibiendo todo el tráfico primero** y luego decide qué sesiones derivar a las unidades secundarias.
    
- **UTM Inspection: AA mode is most effective when you have a lot of UTM (antivirus, IPS) inspection, as the primary can send that heavy processing work to the secondary members.** // Inspección UTM: El modo AA es más efectivo cuando tienes mucha inspección UTM (antivirus, IPS), ya que el primario puede enviar ese trabajo pesado de procesamiento a los miembros secundarios.
![[Pasted image 20260313151808.png]]

## HA Requirements // Requisitos de HA

**Before configuring FortiGate HA, ensure that the devices you want to add have the same hardware or VM model, firmware version, licensing, hard drive configuration, and operation mode.** // Antes de configurar el HA de FortiGate, asegúrate de que los dispositivos que deseas agregar tengan el mismo modelo de hardware o VM (máquina virtual), versión de firmware, licencias, configuración de disco duro y modo de operación.

### All cluster members must have the same: // Todos los miembros del clúster deben tener el mismo:

- **Model** // Modelo.
    
- **Firmware version** // Versión de firmware.
    
- **Licensing (if different, the cluster uses the lowest-level license)** // Licencias (si son diferentes, el clúster utilizará el nivel de licencia más bajo entre ellos).
    
- **Hard drive configuration** // Configuración de disco duro.
    
- **Operating mode (NAT or transparent)** // Modo de operación (NAT o transparente).

### During cluster creation, the following parameters must match: // Durante la creación del clúster, los siguientes parámetros deben coincidir:

- **HA group ID** // ID de grupo de HA.
    
- **Group name** // Nombre del grupo.
    
- **Password** // Contraseña.
    
- **Heartbeat interface settings** // Ajustes de la interfaz de "heartbeat".

### Información Adicional y Análisis de la Imagen

- **Firmware Version:** This is the most common reason HA fails to form. Even a small difference in the build number can prevent synchronization. // Versión de Firmware: Esta es la razón más común por la que un HA no se forma. Incluso una pequeña diferencia en el número de "build" puede evitar la sincronización.
    
- **Licensing:** Although the video says the cluster uses the "lowest-level license," in practice, if one unit has an expired license and the other doesn't, the cluster might experience issues with security updates (UTM). It's best to keep them identical. // Licencias: Aunque el video dice que el clúster usa el "nivel más bajo", en la práctica, si una unidad tiene la licencia vencida y la otra no, el clúster podría tener problemas con las actualizaciones de seguridad (UTM). Lo ideal es mantenerlas idénticas.
    
- **HA Group ID:** This ID is used to generate the **Virtual MAC address**. If you have two different HA clusters on the same network, they **must** have different Group IDs to avoid MAC address conflicts. // HA Group ID: Este ID se usa para generar la **dirección MAC virtual**. Si tienes dos clústeres de HA diferentes en la misma red, **deben** tener Group IDs diferentes para evitar conflictos de direcciones MAC.
    
- **Heartbeat Interfaces:** For stability, it is highly recommended to use at least **two dedicated heartbeat links** (redundant) to avoid a "split-brain" scenario where both units think they are the primary. // Interfaces Heartbeat: Para mayor estabilidad, se recomienda encarecidamente usar al menos **dos enlaces de heartbeat dedicados** (redundantes) para evitar un escenario de "split-brain" donde ambas unidades creen que son la primaria.

![[Pasted image 20260313152032.png]]

## Best Practices // Buenas Prácticas

**The following are some general best practices to keep in mind when working with FortiGate HA:** // Las siguientes son algunas buenas prácticas generales a tener en cuenta al trabajar con el HA de FortiGate:

### Redundancy & Connections // Redundancia y Conexiones

- **Use redundant, dedicated, and matching heartbeat interfaces: At least two heartbeat links should be configured for redundancy and quicker failure detection. Dual back-to-back connections between HA units are highly recommended.** // Utiliza interfaces de "heartbeat" redundantes, dedicadas y coincidentes: Se deben configurar al menos dos enlaces de heartbeat para redundancia y una detección de fallas más rápida. Se recomiendan encarecidamente las conexiones dobles directas (back-to-back) entre las unidades HA.
    
- **Use identical connections for internal and external interfaces: Connect each HA unit to the same switches using identical ports and cabling.** // Utiliza conexiones idénticas para las interfaces internas y externas: Conecta cada unidad HA a los mismos switches utilizando puertos y cableado idénticos.
    
- **Match hardware and firmware: To avoid compatibility problems, all HA members must have the same model and run the same firmware version.** // Coincidir hardware y firmware: Para evitar problemas de compatibilidad, todos los miembros del HA deben tener el mismo modelo y ejecutar la misma versión de firmware.

### Management & Maintenance // Gestión y Mantenimiento

- **Avoid making changes on secondary units: Manual changes on a secondary unit may cause disrupting mismatches. Always make configuration changes from the primary only.** // Evita realizar cambios en las unidades secundarias: Los cambios manuales en una unidad secundaria pueden causar desajustes disruptivos. Realiza siempre los cambios de configuración solo desde el primario.
    
- **Monitor critical interfaces: Enable link monitoring on WAN/LAN interfaces to detect failures and trigger a failover process when needed.** // Monitorea las interfaces críticas: Habilita el monitoreo de enlaces en las interfaces WAN/LAN para detectar fallas y activar un proceso de failover cuando sea necesario.
    
- **Test Regularly: Periodically verify failover functionality to ensure the cluster performs as expected in real-world scenarios.** // Realiza pruebas regularmente: Verifica periódicamente la funcionalidad del failover para asegurar que el clúster funcione según lo esperado en escenarios del mundo real.

### Información Adicional y Análisis de la Imagen

- **Split-brain Scenario: As mentioned in the video, having two heartbeat links is the best defense against "split-brain," which happens when the secondary loses contact with the primary but the primary is still alive. Both units start acting as "Primary," causing IP and MAC conflicts throughout the network.** // Escenario de Split-brain: Como se menciona en el video, tener dos enlaces de heartbeat es la mejor defensa contra el "split-brain", que ocurre cuando el secundario pierde contacto con el primario pero el primario sigue vivo. Ambas unidades comienzan a actuar como "Primarias", causando conflictos de IP y MAC en toda la red.
    
- **Link Monitoring: By default, if a cable on a LAN port breaks, the FortiGate might NOT failover because the device itself is still "up." You must manually tell the FortiGate to monitor those specific ports so it knows to switch to the other unit if a cable is unplugged.** // Monitoreo de enlaces: Por defecto, si un cable en un puerto LAN se rompe, el FortiGate podría NO hacer failover porque el dispositivo en sí sigue "encendido". Debes decirle manualmente al FortiGate que monitoree esos puertos específicos para que sepa cambiar a la otra unidad si se desconecta un cable.
    
- **Identical Cabling: In the image, the second box emphasizes "identical ports." This means if `port1` is WAN on the Primary, `port1` must be WAN on the Secondary. This ensures the Virtual MAC works correctly across the switches.** // Cableado idéntico: En la imagen, el segundo cuadro enfatiza "puertos idénticos". Esto significa que si el `port1` es WAN en el Primario, el `port1` **debe** ser WAN en el Secundario. Esto asegura que la MAC Virtual funcione correctamente a través de los switches.

![[Pasted image 20260313153047.png]]![[Pasted image 20260313153133.png]]