## Blocking Malware
## **Learning Objectives // Objetivos de Aprendizaje**

- **Understand why you should use antivirus protection.** // Comprender por qué deberías usar protección antivirus.
        
- **Explain how FortiGate antivirus works to block malware.** // Explicar cómo funciona el antivirus de FortiGate para bloquear el malware.

- **Configure FortiGate antivirus.** // Configurar el antivirus de FortiGate.

### Risk of Malware // Riesgo de Malware

**Keeping malware out of your network is key to securing your organization.** // Mantener el malware fuera de su red es clave para asegurar su organización.

Cyber criminals user malware to:

- **Cause data breaches** // Provocar filtraciones de datos
- **Extort money** // Extorsionar dinero

- **Steal intellectual property** // Robar propiedad intelectual**
    
- **Disrupt businesses** // Interrumpir los negocios

![[Pasted image 20260310083837.png]]

### FortiGuard Labs
**FortiGuard Labs provides a database of asignatures that allow FortiGate to identify malware.**
**You can configure schedule updates on FortiGate at regular intervals, such as hourly, daily, weekly, or automatically within every hour, to keep the database up-to-date.** 
**this helps maintain protection against the latest malware variants and previously unknown threats.**

FortiGuard Labs proporciona una base de datos de firmas que permite a FortiGate identificar malware.
Puede configurar actualizaciones programadas en FortiGate a intervalos regulares, como cada hora, diariamente, semanalmente o automáticamente cada hora, para mantener la base de datos actualizada.
Esto ayuda a mantener la protección contra las últimas variantes de malware y amenazas previamente desconocidas.


![[Pasted image 20260310152810.png]]

### FortiGate antivirus Scanning
**FortiGate uses many techniques to detect viruses.** // FortiGate utiliza diversas técnicas para detectar virus.

**These detection techniques include:** // FortiGate utiliza diversas técnicas para detectar virus.

**-Antivirus Scan** // Análisis antivirus
**Antivirus scan detects know malware and is the first, fastest, and the simplest way to detect malware.**
**FortiGate detects viruses that are an exact match for a signature FortiGuard antivirus database.**

El análisis antivirus detecta malware conocido y es la forma más rápida, sencilla y eficaz de detectarlo.
FortiGate detecta virus que coinciden exactamente con la base de datos de firmas del antivirus FortiGuard.

![[Pasted image 20260310153714.png]]

**-Grayware Scan** // Análisis de grayware 
**Grayware scan detects unsolicited programs, known as grayware,**
**that have been installed without the user's knowledge or consent.** 
**While graywere is not technically a virus, it can cause unwanted behavior,**
**so FoortiGate considers ir to be malware. Often, FortiGate detects grayware using a FortiGuard grayware signature.**

El análisis de grayware detecta programas no solicitados, conocidos como grayware, que se han instalado sin el conocimiento ni el consentimiento del usuario.
Si bien grayware no es técnicamente un virus, puede causar comportamientos no deseados, por lo que FortiGate lo considera malware. A menudo, FortiGate detecta grayware mediante una firma de grayware de FortiGuard.

![[Pasted image 20260310154402.png]]

**-Machine Learning/ Artificial intelligence Scan** // Análisis de aprendizaje automático/inteligencia artificial
**Marchine learning/artificial intelligence scan uses machine learning and artificial intelligence techniques to detect zero-day attacks containing malware that is new, unknown, and does not yet have a matching associated signature. Because this type of scan is based on probability, using ir does increase the possibility of false positives.** 
**By default, when FortiGate detects a new virus, ir logs the file as suspicious but does not block ir.** 

El análisis de aprendizaje/inteligencia artificial de Marchine utiliza técnicas de aprendizaje automático e inteligencia artificial para detectar ataques de día cero que contienen malware nuevo, desconocido y que aún no tiene una firma asociada. Dado que este tipo de análisis se basa en la probabilidad, el uso de ir aumenta la posibilidad de falsos positivos.
Por defecto, cuando FortiGate detecta un nuevo virus, ir registra el archivo como sospechoso, pero no lo bloquea.

![[Pasted image 20260310154945.png]]

### FortiGate Antivirus Profiles
**You configure antivirus senttings.** 
**As part of an antivirus profile. in the antivirus profile, you can define what FortiGate should do if detects an infected file.**
**After you configure an antivirus profile, you must apply it the firewall policy.** 

Configura los envíos de antivirus.
Como parte de un perfil antivirus, puede definir qué debe hacer FortiGate si detecta un archivo infectado.
Después de configurar un perfil antivirus, debe aplicarlo a la política de firewall.

![[Pasted image 20260310155325.png]]

### Configuring Antivirus Profile 
The antivus profile contains a variety of options that you can configure, including: 
How Windows executable files are handled:
By default, FortiGate considers executable files to be viruses and blocks
any that it detects.
When to send files to FortiSandbox for inspection. 
If FortiGate connects to a FortiSandbox cloud or device, you can configure the antivirus profile to send malicius file to FortiSandbox  for behavior analysis. wheter to use the FortiGuard virus outbreak prevention database. 
This database provides additional protection from FortiGuard to keep you network safe from newly emerging malware. 
This database consists of third-party malware has signatures curated by the FortiGuard. 

El perfil antivirus contiene diversas opciones que puede configurar, incluyendo:
Cómo se gestionan los archivos ejecutables de Windows:
De forma predeterminada, FortiGate considera los archivos ejecutables como virus y bloquea cualquiera que detecte.
Cuándo enviar archivos a FortiSandbox para su inspección.
Si FortiGate se conecta a una nube o dispositivo de FortiSandbox, puede configurar el perfil antivirus para que envíe archivos maliciosos a FortiSandbox para su análisis de comportamiento.
Si usar la base de datos de prevención de brotes de virus de FortiGuard.
Esta base de datos proporciona protección adicional de FortiGuard para mantener su red protegida contra malware emergente.
Esta base de datos contiene malware de terceros con firmas seleccionadas por FortiGuard.

![[Pasted image 20260310160207.png]]

#### Executable Files
**Executable files are files that cause a computer to perform a task based on encoded instructions, rather than a file that you must open in a specific application to access.** // Los archivos ejecutables son archivos que hacen que una computadora realice una tarea basada en instrucciones codificadas, en lugar de un archivo que debe abrir en una aplicación específica para acceder a él.


![[Pasted image 20260310160225.png]]

#### FortiSandbox
**FortiSandbox is a solution from Fortinet that opens, executes, and analyzes files in an isolated testing environment.** // FortiSandbox es una solución de Fortinet que abre, ejecuta y analiza archivos en un entorno de pruebas aislado.
![[Pasted image 20260310160416.png]]

### Configure Antivirus Protection
**to instruct FortiGate to scan for malware, you can configure antivirus protection.**
**expend each task to identify the recommended process.** // Para que FortiGate busque malware, puede configurar la protección antivirus.
Invierta cada tarea en identificar el proceso recomendado.

**First, create an antivirus profile, or configure the default antivirus profile.** // Primero, cree un perfil antivirus o configure el perfil antivirus predeterminado.

![[Pasted image 20260310160717.png]]

**Second, enable antivirus scanning on a firewall policy and select the correct profile.** // En segundo lugar, habilite el análisis antivirus en una política de firewall y seleccione el perfil correcto.

![[Pasted image 20260310160857.png]]

**Third, verify the configuration by attempting to download a test file, such as the one available from.**
**The european institute for Computer Antivirus research (EICAR).**

En tercer lugar, verifique la configuración intentando descargar un archivo de prueba, como el disponible en el Instituto Europeo de Investigación en Antivirus Informáticos (EICAR).

![[Pasted image 20260310161143.png]]

**Finally, use FortiGate logs to monitor antivirus protection.**
Por último, utilice los registros de FortiGate para supervisar la protección antivirus.

![[Pasted image 20260310161220.png]]

![[Pasted image 20260310161253.png]]

![[Pasted image 20260310161908.png]]

