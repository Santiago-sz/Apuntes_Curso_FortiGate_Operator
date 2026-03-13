## Inspect SSl Traffic
### Learning Objectives
**After completing this lesson, you will be able to achieve these objectives.

Al completar esta lección, podrá lograr estos objetivos.

**-Describe why SSL traffic should be inspected** // Describir por qué se debe inspeccionar el tráfico SSL.

**-Describe how SSL inspection works in FortiGate** // Describir cómo funciona la inspección SSL en FortiGate

**-Configure an SSL inspection in a firewall policy** // Configurar una inspección SSL en una política de firewall.

### Using SSL inspection
**HTTPS offers protection by applying encryption to web traffic; however, it also introduces a potential security risk because attackers may attempt to use encrypted traffic to get around your network's normal defenses.** 

HTTPS ofrece protección al aplicar cifrado al tráfico web; sin embargo, también introduce un riesgo de seguridad potencial porque los atacantes pueden intentar utilizar tráfico cifrado para eludir las defensas normales de su red.

![[Pasted image 20260308154106.png]]

### Using SSL Inspection to Inspect Encrypted Traffic
**For example, Bob connects to the website example.com.
This site a certificate issued by a legitimate certificate authority (CA).
Because the CA is approved, a valid verification certification is in Bob's certificate store, and Bob browser establishes an SSL session with the website.
However, unknown to Bob, the example.com website has been infected with a virus.
The virus, cloaked by encryption, passes through FortiGate undetected and enters Bob's computer.
To prevent this, you can use SSL inspection to inspect encrypted traffic** 

Por ejemplo, Bob se conecta al sitio web ejemplo.com.
Este sitio cuenta con un certificado emitido por una autoridad de certificación (CA) legítima.
Dado que la CA está aprobada, el almacén de certificados de Bob contiene un certificado de verificación válido, y su navegador establece una sesión SSL con el sitio web.
Sin embargo, Bob no lo sabe, el sitio web ejemplo.com ha sido infectado con un virus.
El virus, camuflado mediante cifrado, atraviesa FortiGate sin ser detectado y entra en el ordenador de Bob.
Para evitarlo, puede usar la inspección SSL para inspeccionar el tráfico cifrado.

![[Pasted image 20260308160724.png]]

### Types of SSL inspection

**There are two different types od SSL FortiGate SSL inspection.** // Existen dos tipos diferentes de inspección SSL de FortiGate.
**-Certificate Inspection:** // Inspección de certificado:
**-Inspects the SSL/TLS handshake.** // Inspecciona el protocolo de enlace SSL/TLS.
**-Verifies the identity of the web server.** // Verifica la identidad del servidor web.
**-Used only with web filtering.** // Se utiliza solo con el filtrado web.


![[Pasted image 20260308164345.png]]

**-Deep Inspection:** // Inspección profunda:
**-Decrypts incoming traffic to inspect it.** // - Descifra el tráfico entrante para inspeccionarlo.
**-if safe, re-encrypts the traffic and sends it to the recipient.** // - Si es seguro, vuelve a cifrar el tráfico y lo envía al destinatario.
**-Used with all types of security scanning.** // - Se utiliza con todo tipo de análisis de seguridad.

![[Pasted image 20260308164850.png]]

#### Certificate inspection
**when you use SSL certificate inspection, FortiGate inspects the SSL/TLS**
**Handshake when a session begins. by doing this, FortiGate verifies the identity of the web server and makes sure that the HTTPS protocol is not used as a workaround to access sites you have blocked using web filtering.** 
**The only security feature that yoou can use with SSL certificate inspection mode is web filtering.** 
**However, this method does not introduce certificate errors and can be useful alternative to deep SSL inspection when you use web filtering.**

Al usar la inspección de certificados SSL, FortiGate inspecciona el protocolo SSL/TLS
Intercambio de información al iniciar una sesión. De esta manera, FortiGate verifica la identidad del servidor web y garantiza que el protocolo HTTPS no se utilice como alternativa para acceder a sitios que haya bloqueado mediante el filtrado web.
La única función de seguridad que puede usar con el modo de inspección de certificados SSL es el filtrado web.
Sin embargo, este método no genera errores de certificado y puede ser una alternativa útil a la inspección profunda de SSL cuando se utiliza el filtrado web.


![[Pasted image 20260308165457.png]]

#### Deep inspection
**When you use SSL deep inspection, also known as full inspection, FortiGate impersonates the recipient of the ooriginating SSL session, then decrypts and inspects the content to find and block them.**
**if the content is safe, FortiGate re-encrypts the content and sends it to the real recipient.** 
**You can apply all types of security scanning with SSL deep inspection, including web filtering. Deep inspection not only protects you from attacks that use HTTPS, it also protects you from other commonly used SSL-encrypted protocols such as SMTPS, IMAPS, and FTPS.**

Al utilizar la inspección profunda de SSL, también conocida como inspección completa, FortiGate se hace pasar por el destinatario de la sesión SSL original, descifra e inspecciona el contenido para encontrarlo y bloquearlo.**
Si el contenido es seguro, FortiGate lo vuelve a cifrar y lo envía al destinatario real.
Puede aplicar todo tipo de análisis de seguridad con la inspección profunda de SSL, incluido el filtrado web. La inspección profunda no solo le protege de ataques que utilizan HTTPS, sino también de otros protocolos de cifrado SSL comunes, como SMTPS, IMAPS y FTPS.

![[Pasted image 20260308170351.png]]

### FortiGate SSL Inspection Profiles
**To use FortiGate SSL inspection, you apply an SSL inspection profile to the firewall policy.**

Para utilizar la inspección SSL de FortiGate, se aplica un perfil de inspección SSL a la política de firewall.

**Preloaded SSL Inspection Profiiles: FortiOS includes four preloaded SSL inspection profiles, three of which are read-only:**

Perfiles de inspección SSL preinstalados: FortiOS incluye cuatro perfiles de inspección SSL preinstalados, tres de los cuales son de solo lectura:

- **certificate-inspection** // inspección de certificado
- **deep-inspection** //  inspección profunda inspección profunda
- **no-inspection** // sin inspección
![[Pasted image 20260310075453.png]]

**Custom SSL InspectionProfiles** // Perfiles de inspección SSL personalizados
- **You can edit the fourth preloaded profile, custom-deep-inspection** // Puede editar el cuarto perfil precargado, "inspección profunda personalizada"
- **you can also clone any of the read-only profiles or create your own inspection profile.** // También puede clonar cualquiera de los perfiles de solo lectura o crear su propio perfil de inspección.
![[Pasted image 20260310075811.png]]

### Certificate warnings
Certificate warnings occur when FortiGate encrypts traffic using the self-signed certificate. 

**When tou use SSL deep inspection using the FortiGate CA certificate, you browser displays a certificate warning each time you cannect to an HTTPS site.** 
**This occurs because FortiGate is generating a certificate that appears to be from the correct site, but is signed by the FortiGate CA, which is not a CA browser trusts by default.** 
**This makes it appear that the FortiGate is performing a man-in-the-middle attack.** 

Al usar la inspección profunda de SSL con el certificado de CA de FortiGate, su navegador muestra una advertencia de certificado cada vez que se conecta a un sitio HTTPS.
Esto ocurre porque FortiGate genera un certificado que parece provenir del sitio correcto, pero está firmado por la CA de FortiGate, que no es una CA en la que el navegador confía por defecto.
Esto da la impresión de que FortiGate está realizando un ataque de intermediario.

![[Pasted image 20260310080413.png]]

**For example, a nettwork user connects to <https://facebool.com> .**
**Traffic from the Facebook web server uses the real Facebook certificate, signed by a well-known CA.**

Por ejemplo, un usuario de red se conecta a <https://facebool.com>. El tráfico del servidor web de Facebook utiliza el certificado real de Facebook, firmado por una CA reconocida.

![[Pasted image 20260310080652.png]]

**FortiGate intercepts this traffic and decrypts it.** 
**Then, when it is deemed safe, FortiGate passes the traffic on to the end user.** 
**The traffic now a certificate with the same  <https://facebool.com> , but the certificate is signed by the FortiGate CA.**
**Certificate errors can also appear when you use SSL certificate inspection, because FortiGate uses its CA certificate to encrypt the replacement message that appears when you attempt to browse to a browse to a blocked site over HTTPS.**

FortiGate intercepta este tráfico y lo descifra.
Luego, cuando se considera seguro, FortiGate lo transfiere al usuario final.
El tráfico ahora tiene un certificado con el mismo <https://facebool.com>, pero este está firmado por la CA de FortiGate.
Los errores de certificado también pueden aparecer al utilizar la inspección de certificados SSL, ya que FortiGate utiliza su certificado de CA para cifrar el mensaje de reemplazo que aparece al intentar acceder a un sitio bloqueado mediante HTTPS.

![[Pasted image 20260310081500.png]]

### Avoiding Certificate Warnings 
**To avoid certificate warnings, do one of the following:** // Para evitar advertencias de certificado, realice una de las siguientes acciones:

Download the Fortinet Certificate:
**Downlooad the Fortinet_CA_SLL certificate and install it on all the workstations as a trusted root authority.** // Descargue el certificado Fortinet_CA_SLL e instálelo en todas las estaciones de trabajo como autoridad raíz de confianza.

Use a CA-issued SSL Certificate:
**In the certificate, the basec constraints field must be set to CA:TRUE and KeyUsage field must be set to KeyCertSign.** // En el certificado, el campo "basec constraints" debe estar configurado como CA:TRUE y el campo "KeyUsage" debe estar configurado como KeyCertSign.

![[Pasted image 20260310082030.png]]

![[Pasted image 20260310082008.png]]

![[Pasted image 20260310083258.png]]