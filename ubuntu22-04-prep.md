Preparacion Laboratorios
==================================
**En esta guia vamos a estar instalando las siguientes aplicaciones**
```
virtualbox
vagrant
ansible
pip
```
**Comandos en la terminal**

```
 sudo apt install ansible -y
 sudo apt install virtualbox -y
 sudo apt install vagrant -y
 sudo apt install pip3 -y
 pip3 install poetry
 vagrant plugin install vagrant-vyos
```
Vagrant Boxes
-------
Con el objetivo de evitar tiempos muertos de descarga se requiere descargar las imagenes de VyOS y Ubuntu 22.04
```
vagrant box add --box-version 20231215.0.0 vyos/current --provider virtualbox
vagrant box add --box-version 20230907.00.21 ubuntu/jammy64 --provider virtualbox