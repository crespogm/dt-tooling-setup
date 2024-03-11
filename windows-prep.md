Preparacion Laboratorios
==================================
**En esta guia vamos a estar instalando las siguientes aplicaciones**
* Vagrant
* Github Desktop
* Chocolatey
* VirtualBox
* VS Code
* WSL2 con Ubuntu 22.04 image
* Ansible dentro del WLS
* Vagrant dentro del WLS
* VS Code dentro del WLS


GitHub Desktop
------------
**Documentacion Oficial**

 https://desktop.github.com/

Chocolatey
------------
**Documentacion Oficial**

 https://chocolatey.org/install

**Documentacion Adicional**

 https://celerolab.com/como-instalar-chocolatey/

```
1)Abrir un cmd como ADMINISTRADOR y lanzar el comando.
2)@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
1) Cerrar el cmd.
2) Abrir cmd como administrador
3) Probar el comando choco, Ej: choco find virtualbox
```
Virtualbox
------------
**Documentacion Oficial**

 https://www.virtualbox.org/wiki/Downloads
```
1) choco install virtualbox
2) apretar la letra A cuando pregunte por los scripts.
3) Puede enviar un mensaje de error este esta solicitando un reinicio
4) Reiniciar el equipo
5) Volver a lanzar el comando choco install virtualbox
```
Vagrant
------------
**Documentacion Oficial**

 https://developer.hashicorp.com/vagrant/downloads#windows
```
choco install vagrant
```
VS Code
------------
**Documentacion Oficial**

https://code.visualstudio.com/download
```
choco install vscode
```
WSL-2 Ubuntu
------------
**Documentacion Oficial**

 https://learn.microsoft.com/en-us/windows/wsl/install
```
choco install wsl2 --params "/Version:2 /Retry:true"
```
**Manual, CMD como administrador**
```
1) dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
2) dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
3) Reiniciar el equipo
4) wsl --set-default-version 2
5) wsl --install -d Ubuntu-22.04
```
**Guia paso a paso**

https://www.youtube.com/watch?v=uJg5HVzNUN0

WSL Posibles Errores
------------
```
https://www.youtube.com/watch?v=C7XBUK1wwUE
```
Dentro de WSL
------------
En el ubuntu que esta instalado dentro del windows debemos instalar los siguientes paquetes.
```
1) sudo apt install ansible -y
2) sudo apt install vagrant -y
3) sudo apt install pip3 -y
4) sudo apt install code -y
5) pip3 install poetry
6) vagrant plugin install vagrant-vyos
7) echo "[automount]" | sudo tee -a /etc/wsl.conf
8) echo "options = \"metadata,umask=22,fmask=11\"" | sudo tee -a /etc/wsl.conf
```
Vagrant Boxes dentro de WLS
-------
Con el objetivo de evitar tiempos muertos de descarga se requiere descargar las imagenes de VyOS y Ubuntu 22.04
```
vagrant box add --box-version 20231215.0.0 vyos/current --provider virtualbox
vagrant box add --box-version 20230907.00.21 ubuntu/jammy64 --provider virtualbox
