### Configuring the Fortigate intrusion Prevention System (IPS)

![[Pasted image 20260311150557.png]]

## Objetivos de Aprendizaje

Al finalizar esta lección, serás capaz de alcanzar los siguientes objetivos:

- **Describir qué es un Sistema de Prevención de Intrusiones (IPS).**
    
- **Explicar cómo un IPS puede detectar y bloquear actividad maliciosa en una red.**
    
- **Configurar el IPS de FortiGate.**
    
- **Describir las mejores prácticas comunes al trabajar con un IPS.**

### Intrusion Prevention System (IPS)
**Intrusion prevention systems, or IPS, play a very important part in preventing cyberattacks and protecting networks from various threats.**
**An IPS can detect and block malicious network activity by analyzing the traffic and identifying and blocking potential threats.**
Los sistemas de prevención de intrusiones, o IPS, desempeñan un papel fundamental en la prevención de ciberataques y la protección de las redes contra diversas amenazas.
Un IPS puede detectar y bloquear la actividad maliciosa en la red analizando el tráfico e identificando y bloqueando posibles amenazas.
![[Pasted image 20260311151144.png]]

### IPS Functionality Overview
**The identify malicious traffic, FortiGate uses its top-of-then-line IPS engine and IPS sensors. An ips sensor is a collection of IPS signatures and filters that define thr scope of what the IPS engine scans when IPS the IPS sensor is applied to a firewall policy.**
**IPS sensors also provide the ability to block access to known malicious URLs and ip addresses linked to botnet command-and-control (C&C) servers.** 
**An IPS works by analyzing network traffic in real time, and using a variety of techniques to look for patterns that may indicate a potential attack.** 
**At times some of these techniques overlap and complement each other to provide better results.** 
Para identificar tráfico malicioso, FortiGate utiliza su motor IPS y sensores IPS de última generación. Un sensor IPS es un conjunto de firmas y filtros IPS que definen el alcance de lo que el motor IPS escanea cuando se aplica a una política de firewall.
Los sensores IPS también permiten bloquear el acceso a URL y direcciones IP maliciosas conocidas vinculadas a servidores de comando y control (C&C) de botnets.
Un IPS funciona analizando el tráfico de red en tiempo real y utilizando diversas técnicas para buscar patrones que puedan indicar un posible ataque.
En ocasiones, algunas de estas técnicas se superponen y se complementan para ofrecer mejores resultados.
![[Pasted image 20260311152033.png]]

### FortiGate ips Engine Detection Techniques
**The FortiGate IPS engine uses the following detection techniques, among others:** 

**Once an IPS detects malicious activity, it can take various actions that range from simply creating a log, to blocking threat entirely.** 

Una vez que un IPS detecta actividad maliciosa, puede tomar varias acciones que van desde simplemente crear un registro hasta bloquear la amenaza por completo.

**-Protocol Decoders -> Attackers can send malformed packets to make the target system work abnormally or even stop working. Before checking for attacks, FortiGate uses protocol decoder to detect anomalous traffic patterns that do not conform to established** 
**protocol requirements and standards.** 
**This allows FortiGate, for example, to identify any HTTP packets that deviate from the HTTP protocol standard. FortiGate protocol decoders can identify most protocols even when they use nonstandard port numbers.** 
El motor IPS de FortiGate utiliza, entre otras, las siguientes técnicas de detección:
- Decodificadores de protocolo: Los atacantes pueden enviar paquetes malformados para que el sistema objetivo funcione de forma anormal o incluso deje de funcionar. Antes de comprobar si hay ataques, FortiGate utiliza un decodificador de protocolo para detectar patrones de tráfico anómalos que no cumplen con los requisitos y estándares de protocolo establecidos.
Esto permite a FortiGate, por ejemplo, identificar cualquier paquete HTTP que se desvíe del estándar del protocolo HTTP. Los decodificadores de protocolo de FortiGate pueden identificar la mayoría de los protocolos incluso cuando utilizan números de puerto no estándar.
![[Pasted image 20260311152924.png]]

-**Signatures -> After FortiGate identifies the protocol, it uses signatures to check for malicious traffic. Signatures are entries in a database that include very specific details about known threats. the IPS examines the network traffic and looks for matches in the database.** 
**when it finds a match, the IPS takes the action configured for that specific signature. Each signature includes a default action, but you can change it to another one as needed. FortiGate firewalls include thousands of signatures and receive daily updates from FortiGuard.** 
**However, FortiGate uses only the signatures that you specify to examine traffic. The use of asignatures is effective in detecting known threats, but ir does not detect new or unknown threats.** 
Firmas -> Una vez que FortiGate identifica el protocolo, utiliza firmas para detectar tráfico malicioso. Las firmas son entradas en una base de datos que incluyen detalles muy específicos sobre amenazas conocidas. El IPS examina el tráfico de red y busca coincidencias en la base de datos.
Cuando encuentra una coincidencia, el IPS ejecuta la acción configurada para esa firma específica. Cada firma incluye una acción predeterminada, pero puede modificarla según sea necesario. Los firewalls FortiGate incluyen miles de firmas y reciben actualizaciones diarias de FortiGuard.
Sin embargo, FortiGate solo utiliza las firmas que usted especifica para examinar el tráfico. El uso de firmas es eficaz para detectar amenazas conocidas, pero no detecta amenazas nuevas o desconocidas.
![[Pasted image 20260311153750.png]]

### Configuring the FortiGate IPS 
Follow these general steps to configure the FortiGate IPS. click each step to learn more. 

**Firts, you must select the IPS sensor that will be used to analyze the traffic. FortiGate includes several predefined sensors that you can use as provided, or you edit. Additionally, you can create your own custom sensor to meet your speciific requirements.** 
Primero, debe seleccionar el sensor IPS que se usará para analizar el tráfico. FortiGate incluye varios sensores predefinidos que puede usar tal como se proporcionan o editar. Además, puede crear su propio sensor personalizado para satisfacer sus necesidades específicas.
![[Pasted image 20260311154132.png]]

**Second, you must review or edit the segnature and filters included in the sensor. you can also enable the sensor to block malicious URLs and botnet C&C traffic. Each of these options is independent from the other** **and you should configure them according to your requirements.**
En segundo lugar, debe revisar o editar la firma y los filtros incluidos en el sensor. También puede habilitar el sensor para bloquear URL maliciosas y tráfico de C&C de botnets. Cada una de estas opciones es independiente de las demás y debe configurarlas según sus necesidades.
![[Pasted image 20260311154546.png]]

**Lastly, after the sensor is ready, you must apply it to a firewall policy.** 
Por último, una vez que el sensor esté listo, debes aplicarlo a una política de firewall.
![[Pasted image 20260311154814.png]]

### IPS Actions Options 
**The table on this slide includes all possible actions that the FortiGate IPS can take when it detects a network intrusion. Most of the time, an IPS is not a set it and forget it type of solution.** 
**Determining and updating the correct signature actions is part of the continuous tuning that you must do to improve the effectiveness of your IPS implementation. Different sensors can use the same signatures but with different actions, depending on the specific scenario traffic they examine. For example, you can be more flexible with treaffic that originates at  trusted locations and more restrictive with other locations.**
La tabla de esta diapositiva incluye todas las posibles acciones que el IPS de FortiGate puede realizar al detectar una intrusión en la red. En la mayoría de los casos, un IPS no es una solución que se configura y se olvida.
Determinar y actualizar las acciones de firma correctas forma parte del ajuste continuo que debe realizar para mejorar la eficacia de su implementación de IPS. Diferentes sensores pueden usar las mismas firmas, pero con diferentes acciones, según el tráfico del escenario específico que examinen. Por ejemplo, puede ser más flexible con el tráfico que se origina en ubicaciones de confianza y más restrictivo con otras ubicaciones.
![[Pasted image 20260311155734.png]]

### Monitoring the IPS 
**As with any other security solution, it is important to monitor the IPS logs that your firewall generates.** 
**The FortiGate GUI makes all logged information available in the intrucsion prevention widget included in the security events section under logs and reports.** 
Al igual que con cualquier otra solución de seguridad, es importante supervisar los registros IPS que genera el firewall. La interfaz gráfica de usuario de FortiGate muestra toda la información registrada en el widget de prevención de intrusiones, incluido en la sección de eventos de seguridad, en la sección de registros e informes.
![[Pasted image 20260311160116.png]]

### Reviewing Details in the IPS logs 
**For a more complete examination, and to review the full information of the detected IPS traffic, you must navigate to the logs tab. In thes section youu can access all the details pertaining to the relevant logs.** 
Para un análisis más completo y revisar la información completa del tráfico IPS detectado, debe navegar a la pestaña de registros. En esta sección, puede acceder a todos los detalles de los registros relevantes.
![[Pasted image 20260311160345.png]]

### Best Practices for IPS 
![[Pasted image 20260311160419.png]]

**Verify that the IPS database is up to date.** // **Verificar que la base de datos del IPS esté actualizada:** Fundamental para detectar las amenazas más recientes, como firmas de ataques de día cero o nuevas vulnerabilidades descubiertas.
![[Pasted image 20260311160957.png]]

**Consider using the IPS sensors provided as initial templates for new custom ones.** // **Considerar el uso de los sensores IPS provistos como plantillas iniciales para crear nuevos sensores personalizados:** Es recomendable no empezar de cero; utilizá las configuraciones base de Fortinet y ajustalas según las necesidades específicas de tu red.
![[Pasted image 20260311161022.png]]

**Consider using the IPS both for incoming and outgoing traffic.** // **Considerar el uso del IPS tanto para el tráfico entrante como para el saliente:** No solo se deben bloquear ataques externos; también es vital detectar si un equipo interno está comprometido e intenta comunicarse con servidores de comando y control (C2).
![[Pasted image 20260311161037.png]]

**Ensure that SSL inspection is in place so that the IPS can examine all traffic.** // **Asegurarse de que la inspección SSL esté configurada para que el IPS pueda examinar todo el tráfico:** Si el tráfico viaja cifrado (HTTPS) y no se realiza inspección SSL, el IPS no puede "ver" el contenido y las amenazas pasarán de largo sin ser detectadas.
![[Pasted image 20260311161054.png]]

 **Evaluate whether you need to tune your IPS sensors.** // **Evaluar si es necesario ajustar (tunear) tus sensores IPS:** Este proceso es clave para reducir los falsos positivos (alertas erróneas) y optimizar el consumo de recursos de CPU del equipo FortiGate.
 ![[Pasted image 20260311161112.png]]

### Demonstration
![[Pasted image 20260311162725.png]]

![[Pasted image 20260311163937.png]]

![[Pasted image 20260311163953.png]]