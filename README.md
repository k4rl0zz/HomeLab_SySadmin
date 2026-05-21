# HomeLab_SySadmin

README

Este documento se actualizará progresivamente conforme surjan nuevas observaciones, recomendaciones o aclaraciones relacionadas con el HomeLab y las prácticas desarrolladas.

0. Como ver las paginas WEB

--------------------------------------------------------------------------------------------
##########################OJITO CON ESTO##########################
--------------------------------------------------------------------------------------------

**Nota técnica de visualización:** GitHub está diseñado nativamente para almacenar y auditar código fuente en texto plano, por lo cual restringe la ejecución directa de archivos HTML con hojas de estilo por motivos de seguridad perimetral. Para solucionar esto sin alterar la integridad del repositorio ni forzar la descarga de binarios pesados (como PDFs), este índice utiliza un proxy de renderizado seguro que interpreta dinámicamente las directivas de diseño CSS y la interactividad de los laboratorios en tiempo real, garantizando una experiencia de navegación web fluida y fiel al entorno oscuro original con un solo clic.

**[Capítulo 1.1: Instalación de Sistemas Operativos RHEL y Fedora](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%201.1.html)**

**[Capítulo 1.2: Configuración de Clientes Ubuntu y Windows](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%201.2.html)**

**[Capítulo 2: Gestión de Almacenamiento y Servicios de Red](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%202.html)**

**[Capítulo 3: Tareas Avanzadas y Hardening de SSH](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%203.html)**

**[Capítulo 4: Servidores Web Apache, Postfix y CUPS](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%204.html)**

**[Capítulo 5: Alta Disponibilidad con Pacemaker y Keepalived](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%205.html)**

**[Capítulo 6: Seguridad Avanzada, IDS Snort 3 y MFA/2FA](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%206.html)**

**[Capítulo 7: Almacenamiento Compartido y Dominio Samba4](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%207.html)**

**[Capítulo 8: Contenedores Docker, Portainer y WordPress Stack](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%208.html)**

**[Capítulo 9: Automatización e Infraestructura como Código con Ansible](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%209.html)**

**[Capitulo Wazuh: Despliegue de SIEM/XDR Wazuh en RHEL/Fedora](https://htmlpreview.github.io/?https://github.com/k4rl0zz/HomeLab_SySadmin/blob/main/Parte%20WAZUH.html)**

1. Uso de la documentación y validación de comandos

Parte de la documentación de los módulos ha sido generada con herramientas de inteligencia artificial. Debido a esto, es posible que algunos bloques de texto contengan errores o inconsistencias menores.

En caso de encontrar diferencias entre los comandos mostrados en las capturas de pantalla y los incluidos en los bloques de texto, se debe dar prioridad a los comandos visibles en las imágenes, ya que representan la ejecución real de la práctica.

2. Áreas y módulos trabajados en el laboratorio

Dentro de este entorno de laboratorio se desarrollarán prácticas correspondientes a las siguientes asignaturas y módulos:

Adrian SO3 (todo)
Adrian Fund de Seguridad (Wazuh y Radius)
Juan Alexander SSO (solo Linux)


3. Consideraciones sobre el firewall

En la mayoría de las prácticas, no será necesario habilitar reglas de firewall específicas, debido a que gran parte de los ejercicios se ejecutan dentro de una misma máquina o entorno aislado.

Sin embargo, existen escenarios donde sí será obligatorio configurar el firewall, especialmente cuando intervienen múltiples equipos o servicios de red, por ejemplo:

Samba Active Directory
Keepalived
Pacemaker
Servicios cliente-servidor entre Linux y Windows

En estos casos, la comunicación entre nodos o sistemas externos requiere permitir explícitamente determinados puertos y servicios.

Como se trata de un entorno de laboratorio, se recomienda aplicar las reglas de firewall indicadas en las prácticas siempre que aparezcan, incluso si en algunos casos el sistema pudiera funcionar sin ellas.

4. Generación de documentación final

Recordatorio importante:

Al finalizar el proyecto, se deberá entregar al usuario una recopilación organizada de todas las imágenes, capturas y evidencias utilizadas durante las prácticas del HomeLab.

Preferiblemente, esta recopilación deberá generarse en formato:

PDF
Word

Además, el contenido deberá mantenerse en un orden lógico y cronológico para facilitar su consulta.

5. Uso de snapshots y reutilización de máquinas virtuales

En prácticas como:

Samba Active Directory
Ansible
Pacemaker
Keepalived

es importante comprender que normalmente solo existirá un servidor maestro por entorno, mientras que las demás máquinas actuarán como clientes o nodos secundarios.

Por esta razón, cuando se observe la misma práctica realizada sobre diferentes distribuciones (por ejemplo Fedora y RHEL), no significa que ambas configuraciones coexistían simultáneamente. El procedimiento correcto consiste en reutilizar las máquinas cliente mediante snapshots.

Ejemplo práctico
Crear un dominio en RHEL 8.
Vincular Windows 10 al dominio.
Verificar el funcionamiento.
Restaurar una snapshot de Windows 10 previa a la unión al dominio.
Apagar el servidor RHEL 8.
Crear el dominio nuevamente, esta vez en Fedora Server 42.
Vincular Windows 10 al nuevo dominio.
Verificar el funcionamiento.
Finalizar la práctica.

Este método permite reutilizar los mismos clientes sin necesidad de crear nuevas máquinas virtuales para cada escenario.

6. Compatibilidad entre Fedora y RHEL

En muchas prácticas, los comandos ejecutados en RHEL también serán funcionales en Fedora, debido a la similitud entre ambas distribuciones.

Por ello:

Si se observan muchas capturas de RHEL y pocas de Fedora, significa que la mayoría de los pasos son compatibles entre ambas plataformas.
Las capturas específicas de Fedora solo muestran los cambios mínimos necesarios para adaptar la práctica a dicha distribución.
Si no existe ninguna aclaración diferenciando Fedora de RHEL, se debe asumir que los comandos funcionan correctamente en ambas distribuciones.
