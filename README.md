# Taller Linux Agosto 2020
Este repositorio contiene todos los archivos necesarios para el funcionamiento del playbook de ansible. El playbook sirve para instalar el servicio Apache en distribuciones de Linux basadas tanto en RedHat como en Debian, y además permite la creación de virtual hosts configurados como balanceadores de carga.

### Instrucciones de uso:
- Todos los pasos tienen que ser ejecutados desde el equipo controlador.
- Añadir los equipos a ser modificados en el archivo "inventario" debajo de su familia correspondiente, según si es Debian o Red Hat de esta manera: **[nombredelequipo] ansible_host=[ipdelequipo]**
- Ejecutar el comando **ssh-copy-id usuariodelequipo@ipdelequipo** para copiar la llave de SSH a los equipos que van a ser modificados.
- Ejecutar el comando **ansible-playbook main.yml --ask-become-pass** el cual ejecutará el playbook. Cuando pida la contraseña, utilice la del usuario administrador.

#### Cambiar configuración del balanceador de cargas:
- Edite el archivo **loadbalancer_vars.yml** con los valores apropiados para el nombre del cluster, los nodos, puertos, y la red correcta.

#### Tares que realiza el playbook:
- Instala el servicio Apache (apache2 en Debian, httpd en Red Hat).
- Inicia y habilita el servicio.
- Configura reglas de firewall necesarias.
- Crea configuración de balanceo de cargas, y de ser cambiada la configuración, reinicia el servicio.
- En distribuciones Red Hat, crea un directorio de configuración de virtual hosts y lo agrega a la configuración del servicio httpd.

¡Aprobado!
