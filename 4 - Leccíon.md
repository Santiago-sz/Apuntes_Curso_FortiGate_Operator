
## Authenticating Network Users
### Learning Objectives
**After completing this lesson, you will be able to achieve these objectives:** // Tras completar esta lección, podrá lograr los siguientes objetivos: 

**-Understand the importance of using firewall authentication** // Comprender la importancia de usar la autenticación de firewall

**-Explain how FortiGate fiewall authentication works** // Explicar cómo funciona la autenticación de firewall de FortiGate

**-Configure authentication** // Configurar la autenticación

**-Monitor authentication** // Supervisar la autenticación


### Using Firewall Authentication

**Firewall authentication requires users to verify their identity 
FortiGate beforce they can access network resources. 
To authenticate, users must enter their credentials, such as a username and password. without firewall autentication, the onlu information that FortiGate knows about the user that is originating the traffic is their source IP address, which FortiGate cannot use to determine the user's identity. 

La autenticación mediante firewall requiere que los usuarios verifiquen su identidad en FortiGate para poder acceder a los recursos de la red. Para autenticarse, los usuarios deben ingresar sus credenciales, como nombre de usuario y contraseña. Sin la autenticación mediante firewall, la única información que FortiGate conoce sobre el usuario que origina el tráfico es su dirección IP de origen, que FortiGate no puede utilizar para determinar la identidad del usuario.

![[Pasted image 20260305113106.png]]

### Configuring Firewall Authentication

**To configure firewall authentication, you add asource user or user group to the firewall policy. 
This requires that users enter credentials at the beginning of the session.
FortiGate the uses the identity of the user, a long with the other rules in the firewall policy, to determine if the traffic should be allowed or denied. 

Para configurar la autenticación del firewall, se agrega un usuario o grupo de usuarios de origen a la política del firewall.
Esto requiere que los usuarios ingresen sus credenciales al iniciar la sesión.
FortiGate utiliza la identidad del usuario, junto con las demás reglas de la política del firewall, para determinar si se permite o deniega el tráfico.

![[Pasted image 20260305113446.png]]

Authentication Methods 
**You can configure two types of firewall authentication on FortiGate:** // Puede configurar dos tipos de autenticación de firewall en FortiGate:

**Local password authentication.** // Autenticación de contraseña local.

**Remote password authentication.** // Autenticación de contraseña remota.

**The difference between these two methods is on whether the user credentials are stored on FortiGate or on a remote authentication server.**
La diferencia entre estos dos métodos radica en si las credenciales del usuario se almacenan en FortiGate o en un servidor de autenticación remoto.

### Local Authentication
**The simplest method of authentication is local password authentication.
User information is stored locally on the FortiGate device.
This method works well for a single FortiGate installation.

El método más sencillo de autenticación es la autenticación con contraseña local.
La información del usuario se almacena localmente en el dispositivo FortiGate.
Este método funciona bien con una sola instalación de FortiGate.

**When you use firewall authentication, you need to create individual accounts for every user who requires to the network. 
A local user contains both the username and a password. 

Al usar la autenticación mediante firewall, es necesario crear cuentas individuales para cada usuario que acceda a la red. Un usuario local contiene tanto el nombre de usuario como la contraseña.

**You can also create local user groups to group together users who require the same lavel of access.

También puede crear grupos de usuarios locales para agrupar usuarios que requieren el mismo nivel de acceso.

![[Pasted image 20260305122439.png]]


**You migh want to gruop employees by business area, such as finance or HR, or by employee type, such as contractors or guests. 
in most cases, it is best practice to use a group in a firewall policy rather than individual user accounts. 

Quizás quieras agrupar a los empleados por área comercial, como finanzas o RR. HH., o por tipo de empleado, como contratistas o invitados. En la mayoría de los casos, se recomienda usar un grupo en una política de firewall en lugar de cuentas de usuario individuales.

![[Pasted image 20260305123238.png]]


**You can also use local authentication for guest groups, which contain temporaly user accounts that expire after a predetermined amount of time. 
Administrators can manually create guest accounts or create many guest accounts at once using randomly generated user IDs and passwords. 
This reduces administrator workload for large events.
Once created, you can add accounts to the guest user group and associate the group with a firewall policy.

También puede usar la autenticación local para grupos de invitados, que contienen cuentas de usuario temporales que caducan tras un período de tiempo predeterminado.
Los administradores pueden crear cuentas de invitado manualmente o crear varias a la vez utilizando ID de usuario y contraseñas generados aleatoriamente.
Esto reduce la carga de trabajo del administrador en eventos grandes.
Una vez creados, puede agregar cuentas al grupo de usuarios invitados y asociarlo a una política de firewall.

![[Pasted image 20260305123752.png]]

### Remote Authentication
**When you use a remote authentication, FortiGate sends the user entered credentials to an authentication server, such as FortiAuthenticator.**

Cuando se utiliza una autenticación remota, FortiGate envía las credenciales ingresadas por el usuario a un servidor de autenticación, como FortiAuthenticator.

**If the server successfully authenticates the user, FortiGate then applies the maching firewall policy to the traffic. in remote authentication, FortiGate does not store all, or sometimes any, of the user information locally. 

Si el servidor autentica exitosamente al usuario, FortiGate aplica la política de firewall correspondiente al tráfico. En la autenticación remota, FortiGate no almacena toda, o a veces ninguna, de la información del usuario localmente.

![[Pasted image 20260305124205.png]]

### Authenticating Remote User Groups
**Using remote authentication is desirable when multiple FortiGate devices need to authenticate the same users or user groups, or when adding FortiGate to a network that already contains an authentication server. **

El uso de autenticación remota es recomendable cuando varios dispositivos FortiGate necesitan autenticar los mismos usuarios o grupos de usuarios, o cuando se agrega FortiGate a una red que ya contiene un servidor de autenticación.

![[Pasted image 20260305125325.png]]

### Adding Authentication to Firewall Policies
**To use firewall authentication, you need include a user account or user froup in the source definition for a firewall policy, a long with the internal subnet.
After doing this, when traffic matches the firewall policy, the user must authenticate before FortiGate grants access.

Para usar la autenticación de firewall, debe incluir una cuenta o grupo de usuarios en la definición de origen de una política de firewall, junto con la subred interna.
Después de esto, cuando el tráfico coincida con la política de firewall, el usuario deberá autenticarse antes de que FortiGate le conceda acceso.

![[Pasted image 20260305131614.png]]

### Configure Local Authentication

**To allow FortiGate to identify users requesting access, you can configure local firewall authentication.
Expad each task to see the recommended process.

Para que FortiGate identifique a los usuarios que solicitan acceso, puede configurar la autenticación del firewall local.
Expanda cada tarea para ver el proceso recomendado.

**Task1 - Firts create a user account on FortiGate to locally store user credentials.** // Tarea 1: Primero, cree una cuenta de usuario en FortiGate para almacenar localmente sus credenciales.


![[Pasted image 20260305131927.png]]

**Task 2 - second , create a user group based on the user's role or type and add the user to the group.** // Tarea 2: en segundo lugar, cree un grupo de usuarios según el rol o tipo del usuario y agregue el usuario al grupo.

![[Pasted image 20260305132013.png]]

**Task 3 - Third, add the user group as the source for a firewall policy.** // Tarea 3: En tercer lugar, agregue el grupo de usuarios como fuente para una política de firewall.

![[Pasted image 20260305132517.png]]

**Task 4 - Finally, Verify the configuration by having the users sucessfully authenticate and monittor them using FortiGate logs and dashboards.** // Tarea 4: Finalmente, verifique la configuración haciendo que los usuarios se autentiquen exitosamente y monitoreándolos mediante registros y paneles de FortiGate.

![[Pasted image 20260305132652.png]]

### Configure Remote Authentication

**To allow FortiGate to identify users requesting access, you can configure firewall authentication. expand each task to see the recommended process. 

Para permitir que FortiGate identifique a los usuarios que solicitan acceso, puede configurar la autenticación del firewall. Expanda cada tarea para ver el proceso recomendado.

**Task1 - Firts, add the remote server in FortiGate.** //  Tarea 1: Primero, agregue el servidor remoto en FortiGate.

![[Pasted image 20260305133232.png]]

**Task2 - Second, create a user group and map authenticated remote users to this group.** // Tarea 2: En segundo lugar, cree un grupo de usuarios y asigne usuarios remotos autenticados a este grupo.

![[Pasted image 20260305133428.png]]

**Task3 - Third, add the user group as the soruce for firewall policy.** // Tarea 3: En tercer lugar, agregue el grupo de usuarios como fuente de la política de firewall.

![[Pasted image 20260305133535.png]]

**Task4 - Finally, verify the configuration by having the user successfully authenticate and monitor them using FortiGate logs and dashboards.** // Tarea 4: Finalmente, verifique la configuración haciendo que el usuario se autentique exitosamente y monitoreándolo mediante los registros y paneles de FortiGate.

![[Pasted image 20260305133744.png]]

## **Lab Simulation**

**Let's put these concepts into practice by completing the following lab simulation.**

**To increase the security of your network, you want to configure FortiGate to authenticate the users accessing Internet. You will achieve this by performing the following tasks:**

- **Task 1. Create a user account**
    
- **Task 2. Configure remote authentication**
    
- **Task 3. Create a user group**
    
- **Task 4. Add authentication to the firewall policy**
    
- **Task 5. Verify and monitor firewall authentication**

Pongamos en práctica estos conceptos con la siguiente simulación de laboratorio.

Para aumentar la seguridad de su red, debe configurar FortiGate para que autentique a los usuarios que acceden a Internet. Para ello, realice las siguientes tareas:

Tarea 1. Crear una cuenta de usuario

Tarea 2. Configurar la autenticación remota

Tarea 3. Crear un grupo de usuarios

Tarea 4. Agregar autenticación a la política de firewall

Tarea 5. Verificar y supervisar la autenticación del firewall

![[Pasted image 20260305162459.png]]