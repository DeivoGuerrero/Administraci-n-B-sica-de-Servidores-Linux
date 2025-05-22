# Particiones de un servidor Linux
## Comando df
Comando man para obtener más información
```bash 
man df
```

Nos muestra un reporte de espacio asignado y en uso de cada uno de los discos en el servidor
```bash
~$ df
Filesystem     1K-blocks    Used Available Use% Mounted on
tmpfs             304420    1048    303372   1% /run
/dev/sda2       25623780 5694516  18602316  24% /
tmpfs            1522084       0   1522084   0% /dev/shm
tmpfs               5120       0      5120   0% /run/lock
tmpfs             304416      12    304404   1% /run/user/1000
```
Podemos agregar más detalle en la información y con una lectura más cómoda.
```bash
~$ df -Th
Filesystem     Type   Size  Used Avail Use% Mounted on
tmpfs          tmpfs  298M  1,1M  297M   1% /run
/dev/sda2      ext4    25G  5,5G   18G  24% /
tmpfs          tmpfs  1,5G     0  1,5G   0% /dev/shm
tmpfs          tmpfs  5,0M     0  5,0M   0% /run/lock
tmpfs          tmpfs  298M   12K  298M   1% /run/user/1000
```

## Comando lsblk

Comando man para obtener más información
```bash 
man lsblk
```
Por defecto el comando nos muestra los dispositivos de disco duro.

```bash
~$ lsblk
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda      8:0    0   25G  0 disk
├─sda1   8:1    0    1M  0 part
└─sda2   8:2    0   25G  0 part /
sr0     11:0    1 1024M  0 rom
```

Cada disco físico, Linux lo identifica como `sd` seguido de una letra empezando con `a`, el primero será `sda` el siguineten `sdb` y asi sucesivamente.
Dentro de cada disco cada partición se enumerará siguiendo la misma nomenclatura del disco.

```bash
~$ lsblk -f
NAME   FSTYPE FSVER LABEL UUID                                 FSAVAIL FSUSE% MOUNTPOINTS
sda
├─sda1
└─sda2 ext4   1.0         dceb7229-d901-4f26-bddf-0db92dd415ab   17,7G    22% /
sr0
```

## Comando fdisk

Este comando nos ayuda a crear, modificar y eliminar particiones de los discos duros.

Listar particiones.

```bash
~$ sudo fdisk -l
Disk /dev/sda: 25 GiB, 26843545600 bytes, 52428800 sectors
Disk model: VBOX HARDDISK
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: FE5458AB-D995-48CB-92A4-0DB39095BC02

Device     Start      End  Sectors Size Type
/dev/sda1   2048     4095     2048   1M BIOS boot
/dev/sda2   4096 52426751 52422656  25G Linux filesystem
```
---

## Comando en Sevidor RHEL

```bash
$ lsblk -f
NAME              FSTYPE      FSVER    LABEL UUID                                   FSAVAIL FSUSE% MOUNTPOINTS
sda
├─sda1            xfs                        48b07a49-6683-40a8-8e5e-690a27287e09    648,2M    32% /boot
└─sda2            LVM2_member LVM2 001       X69key-T0EB-krIE-2uFq-DeT1-quxg-wHdfbT
  ├─rhel_192-root xfs                        de845850-eb7c-43d0-be9e-1dc0c03e30bb     32,7G     6% /
  └─rhel_192-swap swap        1              6164fe86-d62b-4a31-b2b2-078cc154efcf                  [SWAP]
sr0
```

Vemos que RedHat realiza dos particiones en el disco, uno tipo xfs para el boot y otro tipo LVM2 que es donde se instala el sistema operativo, crea un grupo de Volumenes. 

## Comando free
Comando que nos ayuda a saber cuanta memoria RAM esta en uso 
```bash
$ free -h
               total        used        free      shared  buff/cache   available
Mem:           7,5Gi       464Mi       7,1Gi       8,0Mi       200Mi       7,0Gi
Swap:          4,0Gi          0B       4,0Gi
```

Vemos que la partición Swap, que creó, queda en uso como parte de la memoria RAM del sistema.

---
Comando	Descripción
`lsblk`	Lista los dispositivos de bloques y las particiones en el sistema
`fdisk`	Herramienta para administrar particiones de disco
`parted`	Herramienta para crear y administrar particiones de disco
`mkfs`	Formatea una partición con un sistema de archivos
`mount`	Monta un sistema de archivos en una partición o un directorio
`umount`	Desmonta un sistema de archivos
`df`	Muestra el espacio libre y utilizado en las particiones montadas
`du`	Muestra el tamaño de un archivo o directorio
`resize2fs`	Ajusta el tamaño de un sistema de archivos ext2, ext3 o ext4
`lvcreate`	Crea un volumen lógico en un grupo de volúmenes LVM
`lvextend`	Amplía el tamaño de un volumen lógico
`lvresize`	Ajusta el tamaño de un volumen lógico
`lvremove`	Elimina un volumen lógico
`vgcreate`	Crea un grupo de volúmenes LVM
`vgextend`	Amplía un grupo de volúmenes LVM
`vgreduce`	Reduce un grupo de volúmenes LVM
`pvcreate`	Crea un volumen físico LVM en una partición o dispositivo
`pvextend`	Amplía un volumen físico LVM
`pvresize`	Ajusta el tamaño de un volumen físico LVM
`pvremove`	Elimina un volumen físico LVM