# Instalación y configuración de Ubuntu Server en VirtualBox

1. Descargar imagen ISO: ![Ubuntu Server](https://ubuntu.com/download/server)
2. Configurar máquina virtual.
   1. Abrir VirtualBox
   2. Crear Nueva Maquina Virtual
   3. Asignar nombre
   4. Asignar almenos 2GB de ram y 2 CPUs
   5. Disco Virtual de 25GB
   6. Confirmar creación de maquina virtual
3. Terminar de configurar VM
   1. Abrir Configuración de la VM
   2. En Almacenamiento, Controlador IDE, selecciona imagen ISO descargada.
   3. En Red, Configurar como Adaptador puente, seleccionando la tarjeta de red
   4. Guardar cambios
4. Inicializar maquina virtual
5. Instalar sisteema opetativo
   1. Configurar idioma
   2. Configurar disposición de teclado
   3. Tipo de servidor
      1. Ubuntu server: Instala configuraciones por defecto, un poco más pesado (X)
      2. Ubuntu Server minimized, más ligera evitando instalar algunos paquetes
   4. Configurar adaptador de Red
      1. Cuando es máquina virtual por lo general la tarjeta se configurac como eth (ethernet)
   5. Configuación proxy (No necesario)
      1. Servidor proxy, que monitorea todo el tráfico que pasa por los servidores.
   6. Configurar Mirror o espejo
      1. Seleccionar por defecto
   7. Configurar disco donde se intale el SO
      1. Instalacones discos lógicos, de momento no para apreeeender las particiones necesarias
      2. LUKS sistema de encrptación de discos especialmente Linux
   8. Resumen de instalación
      1. Creará una partición BIOS grub, software que permite seleccionar el dispositivo de arranque
      2. Partición root o /
      3. Confirmar instalación.
   9. Configurar nombre de usuario y contraseña
   10. Instalar servidor OpenSSh, identidad SSH - No (Instalación por defecto).
   11. En los paquetes a instalar, de momento no seleccionar ninguno.
   12. Esperar que finalice la instalación.
6.  Remover el disco de instalación.
    1.  En configuración, Almacenamiento, Controlador IDE, remover.
7.  Iniciar con el usuario configurado y contraseña
8.  Sistema inicializado.
