# Taller Linux 2020
Este repositorio contiene todos los archivos necesarios para el funcionamiento del playbook de ansible.

Para utilizar este playbook, desde el equipo controlador se debe:
- Añadir los equipos a ser modificados en el archivo "inventario" debajo de su familia correspondiente, según si es Debian o Red Hat de esta manera: *[nombredelequipo] ansible_host=[ipdelequipo]*
- Ejecutar el comando *ssh-copy-id usuariodelequipo@ipdelequipo* para copiar la llave de SSH a los equipos que van a ser modificados.
- Ejecutar el comando *ansible-playbook main.yml --ask-become-pass* el cual ejecutará el playbook. Cuando pida la contraseña, utilice la del usuario administrador.
