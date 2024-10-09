# repositoriop3
Consulta dig danielcastelao.org e identifica cada parte de la respuesta:
Comando:
dig danielcastelao.org
Identificación de las secciones:

QUERY SECTION: Sección de consulta que muestra el nombre de dominio y tipo de registro solicitado (por defecto, A).
ANSWER SECTION: Respuesta obtenida para la consulta, con el registro de recursos solicitado (puede incluir registros A, CNAME, etc.).
AUTHORITY SECTION: Indica los servidores de nombres autoritativos para la zona del dominio.
ADDITIONAL SECTION: Información adicional como registros de direcciones IP de los servidores de nombres autoritativos.
IN: Se refiere a la clase de red "Internet".
A: Indica que es un registro de dirección IPv4.
CNAME: (Canonical Name) Si existe un alias para el dominio.

2. Consultas de moodle.danielcastelao.org y www.danielcastelao.org:
Comando:
dig moodle.danielcastelao.org
dig www.danielcastelao.org
Compara las respuestas de ambos dominios. Analiza si hay diferencias en las respuestas como registros CNAME, A, o si apuntan a diferentes IPs.

3. Nombre e IP de servidores DNS autoritativos de www.danielcastelao.org y por qué suelen ser dos:
Comando:
dig NS www.danielcastelao.org
Esto te mostrará los servidores de nombres autoritativos.
Explicación: Generalmente hay al menos dos servidores DNS autoritativos para garantizar redundancia y alta disponibilidad en caso de que uno falle.

4. Consultas inversas para las IPs 130.206.164.68 y otras dos:
Comando para consulta inversa:
dig -x 130.206.164.68
Haz lo mismo para otras dos IPs que te interesen.

5. ¿A qué servidor DNS estás consultando? Cambiar sin modificar archivos de configuración del sistema:
Puedes ver el servidor DNS consultado en la sección SERVER en la respuesta de dig.
Para cambiar el servidor DNS sin modificar archivos de configuración del sistema:
dig @8.8.8.8 www.danielcastelao.org
Aquí 8.8.8.8 es el DNS de Google. Puedes cambiarlo por otro servidor DNS.

6. Obtener el registro SOA del dominio moodle.danielcastelao.org:
Comando para consultar el SOA con el DNS de Google:
dig @8.8.8.8 SOA moodle.danielcastelao.org
Comando para consultar el SOA al servidor primario:
dig @servidor_primario SOA moodle.danielcastelao.org

7. Consulta la IP de www.elpais.com y observa el TTL:
Comando:
dig www.elpais.com
Mira la sección ANSWER y el campo TTL (Time to Live) para saber cuánto tiempo queda almacenado el registro.

8. TTL de distintos dominios:
Consulta varios dominios:
dig dominio1.com
dig dominio2.com
Compara los TTLs en la sección ANSWER. Las diferencias pueden deberse a políticas de cacheo o configuración de servidores DNS para optimizar el rendimiento.

9. Determinar el TTL máximo de un dominio:
Usa el comando dig y busca el valor máximo en el campo TTL. Esto puede variar dependiendo de la configuración del servidor DNS.

10. Máquinas detrás del dominio www.google.es:
dig www.google.es
Consulta cuántas direcciones IP (registros A) están asociadas al dominio. Para comprobar si son siempre las mismas:
dig www.google.es +short
Repítelo varias veces.

11. Consultar a un servidor raíz:
Consulta a un servidor raíz (por ejemplo J.ROOTSERVERS.NET):
dig @j.root-servers.net www.google.es
Observa si acepta el modo recursivo (debe decir RA).

12. Ver todas las queries que hace el servidor DNS:
Usa la opción +trace para ver todas las consultas:
dig +trace www.timesonline.co.uk

14. Servidores de correo de danielcastelao.org:
Comando para obtener los registros MX:
dig MX danielcastelao.org

14. Obtener registros AAAA de www.facebook.com:
Comando:
dig AAAA www.facebook.com
