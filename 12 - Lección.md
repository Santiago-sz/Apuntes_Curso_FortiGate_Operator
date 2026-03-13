### Fortigate sistem Maintenance and Monitoring

![[Pasted image 20260313001117.png]]


## FortiGate System Maintenance and Monitoring Overview // Descripción general del mantenimiento y monitoreo del sistema FortiGate

**Performing regular maintenance on FortiGate firewalls is essential to ensure the security and optimal performance of your network. Organizations should prioritize these tasks to:** // Realizar un mantenimiento regular en los firewalls FortiGate es esencial para garantizar la seguridad y el rendimiento óptimo de su red. Las organizaciones deben priorizar estas tareas para:

- **Prevent security breaches // Prevenir brechas de seguridad**
    
- **Optimize performance // Optimizar el rendimiento**
    
- **Meet compliance requirements // Cumplir con los requisitos de cumplimiento**
    
- **Ensure business continuity // Garantizar la continuidad del negocio**


### Additional Notes & Observations // Notas adicionales y observaciones

- **Prevent security breaches: This involves keeping the firmware updated to the latest stable version to patch known vulnerabilities and ensuring security profiles are correctly configured.** // Prevenir brechas de seguridad: Esto implica mantener el firmware actualizado a la versión estable más reciente para corregir vulnerabilidades conocidas y asegurar que los perfiles de seguridad estén configurados correctamente.
    
- **Optimize performance: Regular monitoring helps identify bottlenecks, such as high CPU or memory usage, which could impact network speed.** // Optimizar el rendimiento: El monitoreo regular ayuda a identificar cuellos de botella, como el alto uso de CPU o memoria, lo que podría afectar la velocidad de la red.
    
- **Meet compliance requirements: Many industries require logs and reports to prove that security measures are in place. Regular maintenance ensures these logs are being captured and stored correctly.** // Cumplir con los requisitos de cumplimiento: Muchas industrias requieren registros (logs) e informes para demostrar que las medidas de seguridad están vigentes. El mantenimiento regular asegura que estos registros se capturen y almacenen correctamente.
    
- **Ensure business continuity: By having backups and monitoring device health, you can quickly recover from hardware failures or misconfigurations.** // Garantizar la continuidad del negocio: Al contar con respaldos y monitorear la salud del dispositivo, puede recuperarse rápidamente de fallas de hardware o configuraciones erróneas.
![[Pasted image 20260313001209.png]]

## Functions of FortiGate System Maintenance // Funciones del mantenimiento del sistema FortiGate

**The most common firewall maintenance tasks include:** // Las tareas de mantenimiento de firewall más comunes incluyen:

- **Backing up configurations // Realizar copias de seguridad de las configuraciones.**
    
- **Performing firmware upgrades // Realizar actualizaciones de firmware.**
    
- **Monitoring system performance // Monitorear el rendimiento del sistema.**
    
- **Examining licenses // Examinar las licencias.**
    
- **Monitoring event logs // Monitorear los registros de eventos.**
    

---

### Additional Notes & Observations // Notas adicionales y observaciones

- **Backing up configurations: This is the most critical task before making any major change. It allows you to restore the device to a working state if something goes wrong. // Realizar copias de seguridad de las configuraciones: Esta es la tarea más crítica antes de realizar cualquier cambio importante. Le permite restaurar el dispositivo a un estado funcional si algo sale mal.**
    
- **Performing firmware upgrades: Keeping the FortiOS updated ensures you have the latest security patches and features. Always check the upgrade path before proceeding. // Realizar actualizaciones de firmware: Mantener el FortiOS actualizado garantiza que tenga los últimos parches y funciones de seguridad. Siempre verifique la ruta de actualización antes de proceder.**
    
- **Monitoring system performance: Regularly checking the dashboard for CPU and memory spikes can prevent system crashes (Conserve Mode). // Monitorear el rendimiento del sistema: Revisar regularmente el tablero para detectar picos de CPU y memoria puede prevenir bloqueos del sistema (Modo Conservación).**
    
- **Examining licenses: It’s important to track the expiration dates of FortiGuard services (IPS, Antivirus, Web Filtering) to maintain continuous protection. // Examinar las licencias: Es importante rastrear las fechas de vencimiento de los servicios de FortiGuard (IPS, Antivirus, Filtrado Web) para mantener una protección continua.**
    
- **Monitoring event logs: Logs provide visibility into what is happening on the network, helping to troubleshoot issues and identify potential threats.** // Monitorear los registros de eventos: Los registros brindan visibilidad de lo que sucede en la red, lo que ayuda a solucionar problemas e identificar amenazas potenciales.
![[Pasted image 20260313001432.png]]

## Backing up FortiGate Configurations // Realizar copias de seguridad de las configuraciones de FortiGate

**Every FortiGate administrator should back up their system configurations on a regular basis. In case of a system or hardware failure, restoring the backup configuration saves time and effort by avoiding having to reconfigure the firewall from scratch.** // Todo administrador de FortiGate debe realizar copias de seguridad de las configuraciones de su sistema de forma regular. En caso de una falla del sistema o del hardware, restaurar la configuración de respaldo ahorra tiempo y esfuerzo al evitar tener que volver a configurar el firewall desde cero.

- **Back up system configurations regularly.** // Realizar copias de seguridad de las configuraciones del sistema regularmente.
    
- **Backing up protects systems and hardware from failures, and helps during hardware migrations.** // El respaldo protege los sistemas y el hardware contra fallas, y ayuda durante las migraciones de hardware.
    
- **Save configuration backups as files or to the FortiGate local disk.** // Guarde los respaldos de configuración como archivos o en el disco local de FortiGate.

### Backup and Restore Options // Opciones de Respaldo y Restauración

**Configuration backups are also useful when migrating to a new hardware platform or when troubleshooting issues after unexpected configuration changes.** // Los respaldos de configuración también son útiles al migrar a una nueva plataforma de hardware o al solucionar problemas después de cambios de configuración inesperados.

- **Backup to Local PC / USB Disk:** **You can save configuration backups as files on the local PC or, if available, a USB key.** // Puedes guardar los respaldos de configuración como archivos en la PC local o, si está disponible, en una llave USB.
    
- **Restore from Local PC / USB Disk:** **To restore a configuration, you must know where the backup file is stored and upload it using the GUI.** // Para restaurar una configuración, debe saber dónde está almacenado el archivo de respaldo y cargarlo usando la interfaz gráfica (GUI).
    
- **Revisions:** **Additionally, if your FortiGate device has at least 512 MB of flash memory, you can store configuration revisions locally on the firewall and use them to revert quickly to a previous system state.** // Además, si su dispositivo FortiGate tiene al menos 512 MB de memoria flash, puede almacenar revisiones de configuración localmente en el firewall y usarlas para volver rápidamente a un estado anterior del sistema.

### Additional Notes & Observations // Notas adicionales y observaciones

- **Config ID / Build:** **The image shows several "Build" IDs (e.g., Build 2285, 2286). These represent specific points in time where the configuration was saved as a revision.** // La imagen muestra varios IDs de "Build" (ej. Build 2285, 2286). Estos representan puntos específicos en el tiempo donde la configuración se guardó como una revisión.
    
- **Encryption and Password Mask:** **In the video (around 0:05), the GUI shows options for "Password mask" and "Encryption". Encrypting your backup file is a best practice to protect sensitive data like VPN pre-shared keys and local user passwords.** // En el video (alrededor de 0:05), la interfaz muestra opciones para "Password mask" (máscara de contraseña) y "Encryption" (cifrado). Cifrar su archivo de respaldo es una mejor práctica para proteger datos sensibles como claves pre-compartidas de VPN y contraseñas de usuarios locales.
    
- **Restore Reboot:** **Important: When you restore a configuration file, the FortiGate will automatically reboot to apply the changes.** // Importante: Cuando restauras un archivo de configuración, el FortiGate se reiniciará automáticamente para aplicar los cambios.

![[Pasted image 20260313001813.png]]
![[Pasted image 20260313001825.png]]

## Performing Firmware Upgrades // Realizando actualizaciones de firmware

**Fortinet releases new firmware versions regularly to: add new features, resolve important issues, and improve performance. Upgrading the firmware helps FortiGate firewalls to stay up to date on the latest security threats and ensures optimal performance.** // Fortinet lanza nuevas versiones de firmware regularmente para: agregar nuevas funciones, resolver problemas importantes y mejorar el rendimiento. Actualizar el firmware ayuda a los firewalls FortiGate a mantenerse al día con las últimas amenazas de seguridad y garantiza un rendimiento óptimo.

### Firmware Maturity Levels // Niveles de madurez del firmware

**In version 7.2 and later, new FortiOS firmware uses a tag to indicate its maturity level:** // En la versión 7.2 y posteriores, el nuevo firmware de FortiOS utiliza una etiqueta para indicar su nivel de madurez:

- **F (feature): A letter F, for features, indicates that the firmware includes new features.** // F (feature): Una letra F, de "features" (funciones), indica que el firmware incluye nuevas funciones.
    
- **M (mature): A letter M, for Mature, indicates that the release doesn't include any new major features.** // M (mature): Una letra M, de "Mature" (maduro), indica que la versión no incluye ninguna función nueva importante.

### Upgrade Methods // Métodos de actualización

**When an upgrade is available, you can let FortiGate download and install it, or you can download and install it manually.** // Cuando una actualización está disponible, puede dejar que FortiGate la descargue e instale, o puede descargarla e instalarla manualmente.

- **Automatic Notification:** **FortiGate devices with a firmware upgrade license display a notification when new firmware is released and provide the option to install it. Using this method, FortiGate downloads and installs the upgrade automatically.** // Notificación automática: Los dispositivos FortiGate con una licencia de actualización de firmware muestran una notificación cuando se lanza un nuevo firmware y ofrecen la opción de instalarlo. Usando este método, FortiGate descarga e instala la actualización automáticamente.
    
- **Manual Upgrade:** **Alternatively, you can download the firmware file manually from the Fortinet support portal and perform the upgrade using the downloaded file.** // Actualización manual: Alternativamente, puede descargar el archivo de firmware manualmente desde el portal de soporte de Fortinet y realizar la actualización utilizando el archivo descargado.


### Additional Notes & Observations // Notas adicionales y observaciones

- **Pre-upgrade Backup:** **It is highly recommended that you create a configuration backup before performing a firmware upgrade. While performing the upgrade, you are prompted to back up your configuration.** // Respaldo pre-actualización: Se recomienda encarecidamente que cree un respaldo de configuración antes de realizar una actualización de firmware. Mientras realiza la actualización, el sistema le pedirá que respalde su configuración.
    
- **Compatibility:** **It is important to ensure that the firmware you download is compatible with the FortiGate model and that you follow the supported upgrade path.** // Compatibilidad: Es importante asegurarse de que el firmware que descargue sea compatible con el modelo de FortiGate y que siga la ruta de actualización admitida.
    
- **System Information Screen:** **The image shows the "System Information" widget where you can see the current "Build" and its maturity tag (e.g., Build 1262 (Feature) or Build 0450 (Mature)).** // La pantalla de información del sistema muestra el widget "System Information" donde puede ver la versión ("Build") actual y su etiqueta de madurez (ej. Build 1262 (Feature) o Build 0450 (Mature)).
![[Pasted image 20260313002139.png]]
![[Pasted image 20260313002159.png]]
![[Pasted image 20260313002218.png]]
![[Pasted image 20260313002239.png]]

## **Following the Recommended Upgrade Path // Siguiendo la ruta de actualización recomendada**

- **If there are a number of firmware versions between your current version and the version you want to upgrade to, use the upgrade path that FortiGate recommends.** // Si hay varias versiones de firmware entre su versión actual y la versión a la que desea actualizar, utilice la ruta de actualización que recomienda FortiGate.
    
- **Following the recommended upgrade path ensures compatibility, stability, and a smooth upgrade process.** // Seguir la ruta de actualización recomendada garantiza la compatibilidad, la estabilidad y un proceso de actualización sin problemas.
    
- **The upgrade path is the recommended sequence of firmware upgrades that you should follow when updating a FortiGate device.** // La ruta de actualización es la secuencia recomendada de actualizaciones de firmware que debe seguir al actualizar un dispositivo FortiGate.
    
- **This sequence is provided by Fortinet. It ensures that the new version is compatible and guarantees the stability of your device.** // Esta secuencia es proporcionada por Fortinet. Asegura que la nueva versión sea compatible y garantiza la estabilidad de su dispositivo.
    
- **FortiGate devices can follow the recommended upgrade path automatically.** // Los dispositivos FortiGate pueden seguir la ruta de actualización recomendada de forma automática.
    
- **Select All Upgrades, select the firmware version, and then select Follow upgrade path.** // Seleccione "All Upgrades" (Todas las actualizaciones), elija la versión de firmware y luego seleccione "Follow upgrade path" (Seguir ruta de actualización).


### **Additional Information & Image Analysis // Información adicional y análisis de imagen**

- **Note on "GA" and "Feature" labels in the image: In the firmware selection menu, you will see "GA" (General Availability) which is recommended for production environments due to its stability, and "Feature" which contains new capabilities but might be less mature.** // Nota sobre las etiquetas "GA" y "Feature" en la imagen: En el menú de selección de firmware, verá "GA" (Disponibilidad General), que se recomienda para entornos de producción por su estabilidad, y "Feature" (Funciones), que contiene nuevas capacidades pero puede ser menos madura.
    
- **Security Fabric upgrade notes: The image shows a specific link for these notes. It is crucial to read them if your FortiGate is part of a Fabric, as upgrading one device may require upgrading others (like FortiSwitch or FortiAP) to maintain connectivity.** // Notas de actualización del Security Fabric: La imagen muestra un enlace específico para estas notas. Es crucial leerlas si su FortiGate es parte de un "Fabric", ya que actualizar un dispositivo puede requerir la actualización de otros (como FortiSwitch o FortiAP) para mantener la conectividad.
    
- **The "Follow upgrade path" tool: When using this automated feature, FortiGate will download and install each intermediate version step-by-step for you, rebooting as many times as necessary until reaching the target version.** // La herramienta "Follow upgrade path": Al usar esta función automatizada, FortiGate descargará e instalará cada versión intermedia paso a paso por usted, reiniciándose las veces que sea necesario hasta llegar a la versión final deseada.
![[Pasted image 20260313002537.png]]
![[Pasted image 20260313002553.png]]


## **Fortinet Upgrade Path Tool // Herramienta de ruta de actualización de Fortinet**

- **Refer to the Upgrade Path Tool when manually upgrading the firmware.** // Consulte la herramienta de ruta de actualización cuando realice una actualización manual del firmware.
    
- **If you are performing the upgrade manually, you should check the upgrade path tool provided by Fortinet.** // Si está realizando la actualización manualmente, debe consultar la herramienta de ruta de actualización proporcionada por Fortinet.
    
- **This is an online utility that allows you to easily find the recommended sequence of firmware versions for your specific platform.** // Esta es una utilidad en línea que le permite encontrar fácilmente la secuencia recomendada de versiones de firmware para su plataforma específica.
### **Additional Information & Image Analysis // Información adicional y análisis de imagen**

- **Online availability: The tool is available at the official documentation site: [https://docs.fortinet.com/upgrade-tool](https://docs.fortinet.com/upgrade-tool). This is the source of truth for all Fortinet product migrations.** // Disponibilidad en línea: La herramienta está disponible en el sitio oficial de documentación: [https://docs.fortinet.com/upgrade-tool](https://docs.fortinet.com/upgrade-tool). Esta es la fuente oficial para todas las migraciones de productos Fortinet.
    
- **Input parameters in the tool: To get the correct path, you must provide the "Current Product" (e.g., FortiGate-VM-KVM), your "Current FortiOS Version" (e.g., 7.4), and the "Upgrade to FortiOS Version" you want to reach (e.g., 7.6.0).** // Parámetros de entrada en la herramienta: Para obtener la ruta correcta, debe proporcionar el "Producto actual" (ej. FortiGate-VM-KVM), su "Versión actual de FortiOS" (ej. 7.4) y la "Versión de FortiOS a la que desea actualizar" (ej. 7.6.0).
    
- **The Recommended Upgrade Path Table: The resulting table shows the specific builds you must pass through. In the example, it indicates that to go from 7.4 to 7.6.0, you must first upgrade to 7.4.1 (build 2463), then to 7.4.3 (build 2573), and finally to 7.6.0 (build 3401).** // Tabla de ruta de actualización recomendada: La tabla resultante muestra las compilaciones (builds) específicas por las que debe pasar. En el ejemplo, indica que para ir de la 7.4 a la 7.6.0, debe actualizar primero a la 7.4.1 (build 2463), luego a la 7.4.3 (build 2573) y finalmente a la 7.6.0 (build 3401).
    
- **Why manual upgrades require this: Unlike the automatic process shown previously, if you download images manually from the Support Portal, you are responsible for following this sequence to prevent configuration corruption or loss of connectivity.** // Por qué las actualizaciones manuales requieren esto: A diferencia del proceso automático mostrado anteriormente, si descarga las imágenes manualmente desde el Portal de Soporte, usted es responsable de seguir esta secuencia para evitar la corrupción de la configuración o la pérdida de conectividad.
![[Pasted image 20260313002919.png]]

## **Monitoring System Performance // Monitoreo del rendimiento del sistema**

- **Monitoring the performance of FortiGate helps to ensure that it is functioning correctly.** // Monitorear el rendimiento de FortiGate ayuda a asegurar que esté funcionando correctamente.
    
- **Performance monitoring involves observing key system metrics such as CPU, memory, and disk usage.** // El monitoreo del rendimiento implica observar métricas clave del sistema como el uso de CPU, memoria y disco.
    
- **You can view these metrics through various widgets on the FortiGate dashboard.** // Puede ver estas métricas a través de varios widgets en el tablero (dashboard) de FortiGate.
    
- **Keeping an eye on session counts and SSL-VPN active users is also critical for maintaining optimal performance.** // Vigilar el recuento de sesiones y los usuarios activos de SSL-VPN también es fundamental para mantener un rendimiento óptimo.

### **Additional Information & Image Analysis // Información adicional y análisis de imagen**

- **The "Add widget" button: This allows you to customize your dashboard by adding more monitors according to your needs, such as network interface traffic or security events.** // El botón "Add widget": Este permite personalizar su tablero agregando más monitores según sus necesidades, como el tráfico de interfaces de red o eventos de seguridad.
    
- **CPU and Memory Widgets: Notice they show a "1 minute" average by default. You can change this interval to see longer historical trends (e.g., 1 hour, 24 hours) to identify peak usage times.** // Widgets de CPU y Memoria: Note que muestran un promedio de "1 minuto" por defecto. Puede cambiar este intervalo para ver tendencias históricas más largas (ej. 1 hora, 24 horas) para identificar momentos de uso pico.
    
- **Disk Usage: While CPU and Memory are volatile, disk usage monitoring is important to ensure that logging or local storage doesn't reach capacity, which could stop the device from recording events.** // Uso de disco: Mientras que la CPU y la memoria son volátiles, el monitoreo del uso de disco es importante para asegurar que el registro de logs o el almacenamiento local no alcancen su capacidad, lo que podría impedir que el dispositivo registre eventos.
    
- **Sessions and SPU: The Sessions widget shows total active sessions. "SPU" refers to Security Processing Units; a 0.0% usage might indicate that the current traffic is not being offloaded to the hardware accelerators or that the load is very light.** // Sesiones y SPU: El widget de sesiones muestra el total de sesiones activas. "SPU" se refiere a las Unidades de Procesamiento de Seguridad; un uso de 0.0% podría indicar que el tráfico actual no está siendo derivado a los aceleradores de hardware o que la carga es muy ligera.
    
- **SSL-VPN Widget: This provides real-time visibility into remote access users. Monitoring this is vital for security and for ensuring the VPN license or hardware limits aren't being exceeded.** // Widget de SSL-VPN: Este proporciona visibilidad en tiempo real de los usuarios de acceso remoto. Monitorear esto es vital para la seguridad y para asegurar que no se excedan los límites de licencia o de hardware de la VPN.
![[Pasted image 20260313003156.png]]


## **Examing FortiGate Licenses // Examinando las licencias de FortiGate**

- **FortiGate requires licenses that you must renew periodically.** // FortiGate requiere licencias que debe renovar periódicamente.
    
- **Different licenses provide access to a variety of features and services, such as technical support, antivirus, web filtering, and IPS.** // Diferentes licencias brindan acceso a una variedad de funciones y servicios, como soporte técnico, antivirus, filtrado web e IPS.
    
- **You can view the status of your FortiGate license in two locations: on the GUI, by clicking System and then FortiGuard, and in the Licenses widget on the dashboard.** // Puede ver el estado de su licencia de FortiGate en dos ubicaciones: en la interfaz gráfica (GUI), haciendo clic en "System" y luego en "FortiGuard", y en el widget "Licenses" en el tablero (dashboard).
    
- **The Licenses widget provides a quick overview of the status of your licenses.** // El widget de licencias proporciona una descripción rápida del estado de sus licencias.
    
- **Each feature indicates whether its corresponding license is valid and displays its expiration date.** // Cada función indica si su licencia correspondiente es válida y muestra su fecha de vencimiento.
    
- **It is important to renew all licenses before their expiration date to avoid service disruptions, avoid legal issues, and maintain compliance.** // Es importante renovar todas las licencias antes de su fecha de vencimiento para evitar interrupciones en el servicio, evitar problemas legales y mantener el cumplimiento.
    
- **An expired license stops FortiGate from receiving software updates and technical support.** // Una licencia vencida impide que FortiGate reciba actualizaciones de software y soporte técnico.
    
- **Some features may keep running during a grace period, while others stop running completely.** // Algunas funciones pueden seguir ejecutándose durante un período de gracia, mientras que otras dejan de funcionar por completo.


### **Additional Information & Image Analysis // Información adicional y análisis de imagen**

- **License Status Icons: In the dashboard widget, icons in green indicate an active and valid service. If an icon turns red or shows a warning symbol, the service has expired or is not reachable.** // Iconos de estado de licencia: En el widget del tablero, los iconos en verde indican un servicio activo y válido. Si un icono se vuelve rojo o muestra un símbolo de advertencia, el servicio ha caducado o no es alcanzable.
    
- **Grace Period Variation: It is vital to know that the "Grace Period" (período de gracia) is not the same for all services. For example, some security signatures might stop updating immediately upon expiration, leaving the network vulnerable.** // Variación del período de gracia: Es vital saber que el "Período de gracia" no es el mismo para todos los servicios. Por ejemplo, algunas firmas de seguridad podrían dejar de actualizarse inmediatamente al vencer, dejando la red vulnerable.
    
- **FortiToken Cloud "Not Licensed": The image shows "FortiToken Cloud" as "Not Licensed" with a warning sign. This means that while other system features are active, the specific cloud-based two-factor authentication service is not enabled for this device.** // FortiToken Cloud "No licenciado": La imagen muestra "FortiToken Cloud" como "No licenciado" con un signo de advertencia. Esto significa que mientras otras funciones del sistema están activas, el servicio específico de autenticación de dos factores basado en la nube no está habilitado para este dispositivo.
    
- **IP Address in Widget: The widget shows an IP (173.243.141.6). This is often the IP of the FortiGuard distribution server that the FortiGate is communicating with to validate the licenses.** // Dirección IP en el widget: El widget muestra una IP (173.243.141.6). Esta suele ser la IP del servidor de distribución de FortiGuard con el que el FortiGate se está comunicando para validar las licencias.
![[Pasted image 20260313003430.png]]
![[Pasted image 20260313003355.png]]


## **Monitoring Event Logs // Monitoreo de los registros de eventos**

- **Monitoring logs regularly can help you to identify unusual activity, detect security threats, and diagnose issues.** // Monitorear los registros (logs) regularmente puede ayudarle a identificar actividades inusuales, detectar amenazas de seguridad y diagnosticar problemas.
    
- **FortiGate logs provide essential information about the firewall’s activity, including network traffic, security events, and system events.** // Los registros de FortiGate proporcionan información esencial sobre la actividad del firewall, incluyendo el tráfico de red, eventos de seguridad y eventos del sistema.
    
- **All logging information is located under Log and Report and is divided in different categories for easy access.** // Toda la información de registro se encuentra bajo "Log and Report" y está dividida en diferentes categorías para facilitar el acceso.
    
- **Select the relevant category and double-click a log entry to see all its details. You can use filters to find specific logs.** // Seleccione la categoría relevante y haga doble clic en una entrada de registro para ver todos sus detalles. Puede usar filtros para encontrar registros específicos.
    
- **The System Events and Security Events sections provide a summary page in addition to the log entries.** // Las secciones de "System Events" (Eventos del sistema) y "Security Events" (Eventos de seguridad) proporcionan una página de resumen además de las entradas de registro habituales.
 
### **Additional Information & Image Analysis // Información adicional y análisis de imagen**

- **Log Categories: In the side menu, you can see categories like "Forward Traffic" (traffic passing through the FortiGate), "Local Traffic" (traffic to/from the FortiGate itself), and "Sniffer Traffic".** // Categorías de logs: En el menú lateral, puede ver categorías como "Forward Traffic" (tráfico que pasa a través del FortiGate), "Local Traffic" (tráfico hacia/desde el propio FortiGate) y "Sniffer Traffic".
    
- **Detailed Log View: When double-clicking a log, a "Log Details" window opens. It shows precise data like the exact Date, Time, Session ID, and Virtual Domain (VDOM). This is crucial for forensic analysis after a security incident.** // Vista detallada de logs: Al hacer doble clic en un registro, se abre una ventana de "Log Details". Muestra datos precisos como la Fecha exacta, Hora, ID de sesión y Dominio Virtual (VDOM). Esto es crucial para el análisis forense después de un incidente de seguridad.
    
- **Source and NAT Information: The detailed view shows both the original Source IP (e.g., 10.1.100.188) and the NAT IP (e.g., 172.16.200.1). This helps administrators understand how the traffic was translated when going to the internet.** // Información de Origen y NAT: La vista detallada muestra tanto la IP de Origen original (ej. 10.1.100.188) como la IP de NAT (ej. 172.16.200.1). Esto ayuda a los administradores a entender cómo se tradujo el tráfico al salir a internet.
    
- **Threat Level Summary Chart: The summary page includes a color-coded graph. Red indicates "Emergency", Orange "Alert", and Yellow "Critical". A spike in these colors usually means immediate action is required.** // Gráfico de resumen de niveles de amenaza: La página de resumen incluye un gráfico codificado por colores. El rojo indica "Emergencia", el naranja "Alerta" y el amarillo "Crítico". Un pico en estos colores generalmente significa que se requiere acción inmediata.
    
- **SDN Connector Events: The image shows logs related to SDN (Software-Defined Network) updates, such as "Dynamic address updated". This confirms that FortiGate is successfully communicating with external cloud or virtualization platforms.** // Eventos de conector SDN: La imagen muestra registros relacionados con actualizaciones de SDN (Red definida por software), como "Dynamic address updated". Esto confirma que FortiGate se está comunicando exitosamente con plataformas externas de nube o virtualización.
![[Pasted image 20260313003719.png]]
![[Pasted image 20260313003703.png]]![[Pasted image 20260313003708.png]]
![[Pasted image 20260313003844.png]]




![[Pasted image 20260313003836.png]]![[Pasted image 20260313004106.png]]![[Pasted image 20260313004146.png]]