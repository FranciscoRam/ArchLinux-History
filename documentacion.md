## Paquetes Instalados en Arhc Linux (Antergos)
**pip**: sudo pacman -S python-pip

**pygame**: python3 -m pip install pygame --user


**rar**: sudo pacman -S p7zip zip unzip unrar


**nodejs**: sudo pacman -S nodejs npm


**npm**: sudo pacman -S nodejs npm

## Software Instalados en Arch Linux (Antergos).


## Sublime Text
**Instalar**
´´´sh
**Sublime text**: yaourt -S sublime-text-dev
´´´


**Crear enlace simbolico**: Al instalar sublime text con yaourt se instala como un software mas, no nos permite acceder a el desde consola como un editar, tal es el caso de kate y nano que si lo hace, para ello crearemos un enlace simbolico al ejecutable de sublime text para poder usarlo como un editor mas de la consola

´´´sh
sudo ln -s /opt/sublime_text_3/sublime_text /usr/bin/st

//st: es el nombre con el que se abrira en la consola ejemplo 

st example.sh

//nos abre un archivo .sh en el directorio actual, un dato importante, solo guardando (ctrl+s), el archivo se creara. 
´´´


**Documentación**: Algunas ligas para complementos que serviran en nuestro sublime text

![Package Control](http://docs.sublimetext.info/en/latest/getting_started/install.html)

### Spotify
Para la instalacion de spotify se encontraron muchos probelmas entre ellos estuvieron:

*   yaourt no se conectaba con el servidor, para corregir esto accederemos a archivo grub ***sudo nano /etc/default/grub ***, cambiaremos la parte de ***GRUB_CMDLINE_LINUX=""***, por GRUB_CMDLINE_LINUX="ipv6.disable=1".

Corrigiendo esto pasaremos a instalar librerias necesarias para instalar spotify.
''sh
yaourt -S --m-arg --skippgpcheck --noconfirm libopenssl-1.0-compat
yaourt -S --m-arg --skippgpcheck --noconfirm libcurl-openssl-1.0
''

Por ultimo instalaremos spotify desde los repositorios AUR 
''sh
yaourt -S spotify
''

**INSTALADOS SIN EXITO**
*   yaourt -S kazam

## Instalar Android Studio y Genymotion
**Enlace de video sobre como instalarlo**

## Grabador de pantalla
Cualquiera de los dos siguientes sirve

**Simple screen recorder**
´´´sh
yaourt -S simplescreenrecorder-git
´´´

**Kazam**
´´´sh
yaourt -S kazam

´´´





## Problemas sin solucionar
**nodemon**

Al parecer la compatibilidad de la version crea un fallo al instalarlo (agregarlo), checarlo.

´´´sh
npm i nodemon -D
npm install --save-deb nodemon

´´´