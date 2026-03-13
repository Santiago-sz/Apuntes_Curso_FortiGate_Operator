## En el mundo de Fortigate, **VDOM** significa **Virtual Domain** (Dominio Virtual).
#VDOM
En el mundo de Fortigate, **VDOM** significa **Virtual Domain** (Dominio Virtual).

Para explicártelo de forma sencilla: es una tecnología que te permite dividir un solo firewall físico en múltiples firewalls lógicos independientes. Es como tener varios departamentos en un mismo edificio, donde cada uno tiene su propia puerta, sus propias reglas y sus propios inquilinos, pero todos comparten la misma estructura.

Aquí tienes los puntos clave para entenderlo:

### 1. Segmentación Total

Cada VDOM funciona como un dispositivo separado. Esto significa que puedes tener:

- **Políticas de seguridad independientes:** Lo que permitas en el VDOM de "Invitados" no afecta al VDOM de "Servidores".
    
- **Tablas de enrutamiento separadas:** Cada VDOM puede tener sus propias rutas y gateways.
    
- **Administradores distintos:** Puedes darle acceso a un técnico solo al VDOM "A" sin que pueda ver o tocar el VDOM "B".
    

### 2. ¿Para qué se usa?

- **Proveedores de Servicios (MSSP):** Un solo FortiGate grande puede dar servicio a 10 clientes distintos, cada uno en su propio VDOM, garantizando que los datos de uno no se mezclen con los del otro.
    
- **Grandes Empresas:** Separar redes corporativas de redes de manufactura o de invitados por razones de cumplimiento o seguridad extrema.
    
- **Entornos de Prueba:** Tener un VDOM para laboratorios sin poner en riesgo la red de producción.
    

### 3. Tipos de VDOMs

Por defecto, los FortiGates vienen con un límite de VDOMs (usualmente 10 o más dependiendo del modelo y la licencia). Existen dos modos principales:

- **Split-Task VDOM:** Separa el tráfico de gestión (administración) del tráfico de datos.
    
- **Multi-VDOM:** El modo completo donde creas múltiples dominios virtuales para distintos propósitos.
    

---

> **Dato importante:** Al activar VDOMs, la CPU y la Memoria RAM del equipo se comparten entre todos. Si un VDOM consume demasiados recursos, podría afectar a los demás si no se configuran límites adecuadamente.

**¿Estás pensando en activar VDOMs en tu equipo o solo te encontraste con el término en la configuración?** Si quieres, puedo explicarte cómo habilitarlos (ya que por defecto vienen desactivados en la mayoría de los modelos).

#GUI
Una **GUI** (por sus siglas en inglés, _Graphical User Interface_) o **Interfaz Gráfica de Usuario**, es el entorno visual que nos permite interactuar con dispositivos electrónicos (computadoras, teléfonos, tablets) de forma sencilla e intuitiva.

Antes de que las GUI fueran el estándar, la gente tenía que comunicarse con las máquinas escribiendo comandos de texto en una pantalla negra (CLI o Interfaz de Línea de Comandos). Con la GUI, pasamos de "escribir" a "señalar y hacer clic".