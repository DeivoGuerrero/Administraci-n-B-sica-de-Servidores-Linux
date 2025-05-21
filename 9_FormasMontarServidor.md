# Formas de montar un servidor
## Instalación directa
Se instala un sistema operativo para ocupar el 100% de los recursos dedicados (software y hardware) ya sean a un solo servicio o varios.

## Virtualización
Se instala un software que sirve como host conocido como (hypervisor) que administra los recursos para crear múltiples guest.

Physical Hardware -> Hypervisor -> 

### Hyepervisor Tipo 1 bare-metal
En los fierros, tenemos capa de hardware y sobre esta misma se monta el hypervisor, a nivel de firmware, nos permite a través de una Shell crear nuestras máquinas virtuales. No necesita SO para funcionar.
### Hypervisor Tipo 2 Hosted
Sobre el hardware se monta un SO (Mac, Windows, Linux), usar hypervisor con GUI para la creación de las máquinas virtuales.

## Contenedores y máquinas virtuales
Contenedor no es lo mismo que maquina virtual, VM posee sus recursos físicos directamente asignados.
