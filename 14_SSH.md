# Configuración de SSH en Servidores Linux Virtuales
## SSH
Secure Shell Protocol: Es un protocolo que nos permite acceder de manera remota a un servidor.
## Práctica
1.	Inicializar las 2 máquinas virtuales
2.	Iniciar sesión en ambos servidores con el usuario creado en la instalación
3.	Verificar si tenemos instalado el comando ssh
a.	Ejecutar `ssh` en la terminal
b.	Si no en Ubuntu `sudo apt install openssh-server`
c.	Si no en RHEL `sudo dnf install openssh`
4.	Identificar la IP de los servidores con `ip address`
5.	Desde la terminal local de la computadora conectarse a los servidores remotamente.
a.	Ejecutar comando `ssh usuario@ip_servidor`
b.	Introducir contraseña correspondiente
