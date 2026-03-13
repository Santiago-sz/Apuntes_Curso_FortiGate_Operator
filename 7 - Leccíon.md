### Control Web Access Using Web Filtering

![[Pasted image 20260310162607.png]]

**Learning Objectives** // Objetivos de Aprendizaje

**Understand why you should use web filtering** // Comprender por qué deberías usar el filtrado web

**Describe FortiGuard categories** // Describir las categorías de FortiGuard

**Configure FortiGate web filtering** // Configurar el filtrado web de FortiGate

### Using Web Filtering
**So why do organizations, and peaople in general, use web filtering? Web filtering helps to control, or track, the websites that people visit.**
**There are many reasons why network administrators would apply web filtering:** 
Entonces, ¿por qué las organizaciones, y las personas en general, utilizan el filtrado web? El filtrado web ayuda a controlar o rastrear los sitios web que visitan las personas.
Hay muchas razones por las que los administradores de red aplicarían el filtrado web:

![[Pasted image 20260310163231.png]]![[Pasted image 20260310163248.png]]

**To limit access to distracting web sites, such as social networking sites, to keep their employees focused on work and maintain productivity.** 
**To prevent network congestion by marking sure users do not use valuable bandwidth for non-business purposes, such as streaming a video. To decrease exposure to web-based threats by liminting access to potentially harmful websites. to limit liability, if employees attempt to download inappropriate of offensive material. to prevent users from viewing inappropriate material.** 

Limitar el acceso a sitios web que distraigan, como las redes sociales, para mantener a los empleados concentrados en el trabajo y mantener la productividad. Prevenir la congestión de la red, asegurándose de que los usuarios no utilicen el valioso ancho de banda para fines no comerciales, como la transmisión de videos. Disminuir la exposición a amenazas web, limitando el acceso a sitios web potencialmente dañinos. Limitar la responsabilidad si los empleados intentan descargar material inapropiado u ofensivo. Evitar que los usuarios vean material inapropiado.

### FortiGuard Category Filters
**For web filtering, FortiGate can use FortiGuard category filters to control web access. FortiGuard categories are derived from the FortiGuard web filtering service.** 

Para el filtrado web, FortiGate puede usar los filtros de categorías de FortiGuard para controlar el acceso web. Las categorías de FortiGuard se derivan del servicio de filtrado web de FortiGuard.

![[Pasted image 20260310164401.png]]

### FortiGuard Category Filters
**The service includes the FortiGuard, URL Categories Database, which sorts billions of web pages into a wide range of rating categories.** 

El servicio incluye FortiGuard, la base de datos de categorías de URL, que clasifica miles de millones de páginas web en una amplia gama de categorías de clasificación.

![[Pasted image 20260310164633.png]]

**Each category contains websites or web pages that have been assigned based on their dominant web content. these categories can, in turn, be blocked or allowed according to their content. the databesa categorizes web content besad on its viewing suitability for three major groups of consumers:** 
**Enterprises, schools, and home and families.** 
**For Example, twitter is categorized as part of the General interest - Personal category. While Dropbox is categorized as part of the Bandwidth Consuming category.** 

Cada categoría contiene sitios web o páginas web asignados según su contenido web predominante. Estas categorías pueden, a su vez, bloquearse o permitirse según su contenido. La base de datos categoriza el contenido web según su idoneidad para tres grupos principales de consumidores: empresas, escuelas, hogares y familias.
Por ejemplo, Twitter se clasifica en la categoría de Interés general - Personal, mientras que Dropbox se clasifica en la categoría de Consumo de ancho de banda.

### FortiGuard Category Filters 
**Note that, categories can be further divided into subcategories.** 
**The General Interest - Personal category includes subcategories such as Social Networking, News and media. While the Bandwidth Consuming category iincludes subcategories such as file Sharing and Storage, Internet Telephony, and Streming Media and dowload.**
**Website categories are determined by both automated and human methods.** 
**The fortiGuard team has automatic web crawlers that look at various aspects of the website in order to come up with a rating.** 
**There are also people who examine websites and look into ratimg requests to determine categories.** 

Tenga en cuenta que las categorías pueden dividirse en subcategorías.
La categoría "Interés general - Personal" incluye subcategorías como "Redes sociales", "Noticias y medios de comunicación". Mientras que la categoría "Consumo de ancho de banda" incluye subcategorías como "Intercambio y almacenamiento de archivos", "Telefonía por Internet" y "Stream Media and Download".
Las categorías de sitios web se determinan mediante métodos automatizados y humanos.
El equipo de fortiGuard cuenta con rastreadores web automáticos que analizan diversos aspectos del sitio web para generar una clasificación.
También hay personas que examinan sitios web y revisan las solicitudes de clasificación para determinar las categorías.

![[Pasted image 20260310165741.png]]

**To review the complete list of categories and subcategories, visit www.fortiguard.com//webfilter/categories.**
**To search for the category for a specific URL, visit www.fortiguard.com/webfilter.** 

Para consultar la lista completa de categorías y subcategorías, visite www.fortiguard.com//webfilter/categories.
Para buscar la categoría de una URL específica, visite www.fortiguard.com/webfilter.

![[Pasted image 20260310170020.png]]

### Applying FortiGuard Category Filters 
**FortiGate works with FortiGuard categories to determine how websites are filtered. rother than block or allow websites individually, FortiGuard category filtering looks at the category, with website has been rated.** 
**FortiGate blocks or allows website access, based on the actions defined for that category, not based on the URL.** 

FortiGate trabaja con las categorías de FortiGuard para determinar cómo se filtran los sitios web. En lugar de bloquear o permitir sitios web individualmente, el filtrado por categorías de FortiGuard analiza la categoría en la que se ha clasificado el sitio web. FortiGate bloquea o permite el acceso a sitios web según las acciones definidas para esa categoría, no según la URL.

![[Pasted image 20260310170538.png]]
### Applying FortiGuard Category Actions
FortiGate allows or blocks connections to websites based on the actions configured for the FortiGuard web filter category in FortiGate. The following FortiGuard web filter category actions are available. 


**Allow permits access to the websites in the category.** // Permitir permisos de acceso a los sitios web de la categoría.

![[Pasted image 20260310170846.png]]

**Block prevents access to the websites in the category. Users trying to access a blocked website see a replacement message indicating that the website is blocked. Also, when a website is blocked, a security log is generated in FortiGate.** 
El bloqueo impide el acceso a los sitios web de la categoría. Los usuarios que intentan acceder a un sitio web bloqueado ven un mensaje indicando que el sitio web está bloqueado. Además, cuando un sitio web está bloqueado, se genera un registro de seguridad en FortiGate.

![[Pasted image 20260310170901.png]]

**Monitor permits access to websites in the category and records access data, such as URL, destination, and IP, to the FortiGate logs.** // El monitor permite el acceso a sitios web de la categoría y registra datos de acceso, como URL, destino e IP, en los registros de FortiGate.

![[Pasted image 20260310170917.png]]

**Warning informs users that the requested website cannot be accessed by internet policies. However, users are given the choice to continue or go back. You can configure a warning interval to present this warning page at specific times. The warning interval is the amount of time until the warning appears again after the user proceeds past it.**
La advertencia informa a los usuarios que, debido a las políticas de internet, no se puede acceder al sitio web solicitado. Sin embargo, se les ofrece la opción de continuar o retroceder. Se puede configurar un intervalo de advertencia para que esta página aparezca en momentos específicos. El intervalo de advertencia es el tiempo que transcurre hasta que la advertencia vuelve a aparecer después de que el usuario la supera.

![[Pasted image 20260310170930.png]]


Authenticate permits access to the websites in the category if the user provides a valid username and password. You can:

- Configure authentication based on user group or individual users.
    
- Customize the interval of time to allow access. Users are not prompted to authenticate again, if they access other websites in the same category, until the timer expires.

La autenticación permite el acceso a los sitios web de la categoría si el usuario proporciona un nombre de usuario y una contraseña válidos. Puede:

-Configurar la autenticación según el grupo de usuarios o usuarios individuales.

-Personalizar el intervalo de tiempo para permitir el acceso.
Si acceden a otros sitios web de la misma categoría, no se les solicitará que se autentiquen de nuevo hasta que expire el temporizador.

![[Pasted image 20260310170941.png]]

### Configure a web Filter to Use a FortiGuard Category 
**First, ensure that FortiGate has a valid FortiGuard security license.**
Primero, asegúrese de que FortiGate tenga una licencia de seguridad FortiGuard válida.

![[Pasted image 20260310192025.png]]

**Second, identify how the FortiGuard service categorize the specific website you are trying to block or allow.** 
En segundo lugar, identifique cómo el servicio FortiGuard clasifica el sitio web específico que está intentando bloquear o permitir.

![[Pasted image 20260310192047.png]]

**Third, configure a web filtering profile to use FortiGuard category-based filters.**
En tercer lugar, configure un perfil de filtrado web para utilizar filtros basados ​​en categorías de FortiGuard.

![[Pasted image 20260310192236.png]]

**Fourth, apply the web filter security profile to a firewall policy to start inspecting web traffic. At this point, if you want to generate logs, enable on the firewall policy.**
En cuarto lugar, aplique el perfil de seguridad del filtro web a una política de firewall para empezar a inspeccionar el tráfico web. En este punto, si desea generar registros, habilítelo en la política de firewall.

![[Pasted image 20260310192339.png]]

**Finally, test the web filter security profile configure for the specifield FortiGuard category-based filters.** 
Por último, pruebe la configuración del perfil de seguridad del filtro web para los filtros específicos basados ​​en categorías de FortiGuard.

![[Pasted image 20260310192644.png]]

### Demonstrations:
![[Pasted image 20260310192917.png]]

![[Pasted image 20260311124723.png]]

![[Pasted image 20260311124705.png]]