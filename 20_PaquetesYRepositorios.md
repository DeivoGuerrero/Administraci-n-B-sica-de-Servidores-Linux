# ¿Qué son los paquetes y repositorios en Linux?
  
## ¿Qué son los paquetes?
Un paquete en el contexto de Linux, es un conjunto de archivos compactados que contiene todos los elementos necesarios para instalar y ejecutar un software en tu sistema. Los paquetes hacen que la instalación sea más sencilla porque incluyen no solo el programa, sino también las dependencias necesarias. Al instalar un paquete, todo lo que el programa necesita está ya preparado para funcionar.

- Facilitan la instalación de software.
- Incluyen binarios y dependencias.
- Simplifican la gestión de software en servidores.

## ¿Cómo funcionan los repositorios?
Los repositorios son, básicamente, servidores que almacenan y gestionan paquetes. Estos archivos se encuentran disponibles para diferentes distribuciones de Linux y permiten que los usuarios los descarguen e instalen fácilmente en sus sistemas. Cada distribución de Linux gestiona sus repositorios de manera distinta, lo que influye en el tipo de software que puedes instalar.

- Servidores que almacenan y gestionan paquetes.
- Varían entre distribuciones como Debian y Ubuntu, y Red Hat y CentOS.
- Permiten la descarga e instalación de software adicional.

### Diferencias entre Debian y Red Hat
En el curso, se han utilizado dos servidores: Ubuntu Server (basado en Debian) y Red Hat Enterprise Linux (RHEL). Aquí es donde entenderemos las diferencias fundamentales en la administración de paquetes:

## ¿Qué es DPKG y el formato .dev?
Para sistemas basados en Debian, como Debian mismo y Ubuntu, el formato estándar de paquetes es .dev. La herramienta que se utiliza para manejar estos paquetes es DPKG. Esta herramienta no solo permite instalar y listar paquetes, sino también crear los tuyos propios si necesitas subirlos a un repositorio privado.

- Utiliza formato .dev.
- Herramienta de administración: DPKG.
- Ideal para Debian y Ubuntu.
  
## ¿Cómo funciona RPM y el formato .rpm?
Para los sistemas basados en Red Hat, como CentOS, Fedora, y Amazon Linux, el formato de paquetes es .rpm. RPM es la herramienta que gestiona estos paquetes, permitiéndote no solo instalarlos, sino también conducir otras tareas como sucripción a repositorios y movimiento de paquetes.

- Utiliza el formato .rpm.
- Herramienta de administración: RPM.
- Ideal para RHEL, CentOS, Fedora.
  
### Ventajas de las herramientas de paquete en Linux
Ambas herramientas, DPKG y RPM, son all-in-one tools, lo que significa que, aunque existen diferencias, sus comandos básicos y flags son bastante similares. Esto facilita mucho la transición entre diferentes distribuciones de Linux y te permite gestionar software de manera eficiente.

- Comandos y flags similares.
- Facilitan la transición entre distribuciones.
- Mejora la eficiencia en la gestión de software.

- `- instal`
- `- remove`
- `l` (list)
- `i` (install)
- `q` (query, acompaña con una bandera)
- `U` (upgrade)
- `e` (erase)
