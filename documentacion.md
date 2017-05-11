## Paquetes Instalados en Arhc Linux (Antergos)

**pip**: 
```sh 
sudo pacman -S python-pip 
```

**pygame**: 
```sh
 python3 -m pip install pygame --user 
 ```


**rar**: 
```sh 
sudo pacman -S p7zip zip unzip unrar 
```


**nodejs**:
```sh
 sudo pacman -S nodejs npm
```

**npm**:
```sh
 sudo pacman -S nodejs npm
```

## Software Instalados en Arch Linux (Antergos).


## Sublime Text
**Instalar**
```sh
**Sublime text**: yaourt -S sublime-text-dev
```


**Crear enlace simbolico**: Al instalar sublime text con yaourt se instala como un software mas, no nos permite acceder a el desde consola como un editar, tal es el caso de kate y nano que si lo hace, para ello crearemos un enlace simbolico al ejecutable de sublime text para poder usarlo como un editor mas de la consola

```sh
sudo ln -s /opt/sublime_text_3/sublime_text /usr/bin/st

//st: es el nombre con el que se abrira en la consola ejemplo 

st example.sh

//nos abre un archivo .sh en el directorio actual, un dato importante, solo guardando (ctrl+s), el archivo se creara. 
```


**Documentación**: Algunas ligas/formas para complementos/plugins que serviran en nuestro sublime text.


**Package Control**: Es indispensable para poder instalar plugins en nuestro sublime_text.


![Package Control](http://docs.sublimetext.info/en/latest/getting_started/install.html)

### Spotify
Para la instalacion de spotify se encontraron muchos probelmas entre ellos estuvieron:

*   yaourt no se conectaba con el servidor, para corregir esto accederemos a archivo grub 
```sudo 
nano /etc/default/grub 
```
cambiaremos la siguiente parte

```
GRUB_CMDLINE_LINUX=""***
```
por 
```
GRUB_CMDLINE_LINUX="ipv6.disable=1"
```
Corrigiendo esto pasaremos a instalar librerias necesarias para instalar spotify.
```sh
yaourt -S --m-arg --skippgpcheck --noconfirm libopenssl-1.0-compat
yaourt -S --m-arg --skippgpcheck --noconfirm libcurl-openssl-1.0
```

Por ultimo instalaremos spotify desde los repositorios AUR 
```sh
yaourt -S spotify
```

## Instalar Android Studio y Genymotion

**Importante**: Antes de ver el video que de como instalarlo es importante verificar el espacion que tiene tu tmpfs esto lo verificaremos con 
```
df -h
```
esto lo menciono debido a que de ser insuficiente el espacio en tmpfs al tratar de instalar android studio te marcare un error debido a espacio insuficiente para ello vamos a aumentar temporalmente el espacio que tiene, el maximo que puedes aumentar ser igual a tu memoria ram, una vez reiniciada la computadora este espacion regresara a lo que tenia anteriormente.
```sh
sudo mount -o remount,size=4G /tmp
```

**Enlace de video sobre como instalarlo**


![How to install a Android development environment](https://www.youtube.com/watch?v=2EGDIOpp088&list=PL7GYLzJcFl5McgMTp2ve_d6tqMq78ReaE&index=115)

## Grabador de pantalla
Cualquiera de los dos siguientes sirve

**Simple screen recorder**
```sh
yaourt -S simplescreenrecorder-git
```

**Kazam**
```sh
yaourt -S kazam

```





## Problemas sin solucionar
**nodemon**

Al parecer la compatibilidad de la version crea un fallo al instalarlo (agregarlo), checarlo.

```sh
npm i nodemon -D
npm install --save-deb nodemon

```