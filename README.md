<p align="center">
<img src="screenshots/BannerEDSI.png" width="1024" >
</p>

# BOT Telegram & Vision One :robot:

Toma acciones en tu consola de Vision One por mensaje. El Bot se encargará de realizar el trabajo.

### Pasos

#### Ingresar a la VM en Azure (Ubuntu)

```bash
utilizar Putty para acceder a la VM con los datos provistos
```

#### Actualiza la VM e instale Docker

```bash
sudo apt update
```

```bash
sudo apt upgrade
```

```bash
sudo snap install docker
```

```bash
sudo apt install podman-docker
```

```bash
sudo apt install docker.io
```

#### Creamos un par de Llaves Privadas-Publicas

```bash
cd /home/{equipoX}/.ssh
```

```bash
ssh-keygen -t rsa -b 4096 -C "casilla@dominio.com"
```

#### Subimos la Llave Pública a nuestro GitHub

```bash
Dentro de nuestra cuenta de Git, nos dirigimos hacia Settings>SSH and GPG Keys>New SSH Key
```

```bash
Copiamos el contenido del archivo id_rsa.pub y lo pegamos dentro de la nueva Key
``` 

#### Descarga el Proyecto

```bash
cd /tmp
```

```bash
git clone git@github.com:EDSITec/BotTelegram.git
```

#### Construir la imagen

```bash
cd /tmp/{nombre del Repo creado}
```

```bash
sudo docker build -t bot .
```

#### Construir Bot de TLG

```bash
Levantar Cuenta de Telegram y escribirle al usuario/contacto de nombre botfather
```

```bash
/newbot
```

```bash
Definir Nombre y usuario de bot. Recibiremos un Token
```

#### Ejecutar el contenedor dentro del Ubuntu

```bash
sudo docker run -e TOKEN_TELEGRAM="YOUR_TELEGRAM_TOKEN" bot
```

#### Interactuamos con el Bot desde Telegram
```bash
Accedemos al Bot por Telegram desde el Link provisto por BotFather
```

```bash
/start
```
Diálogo entre el BOT y el Administrador, donde se le informa las instrucciones para realizar e impactar en su consola de Vision One. Utilizando el comando /help le proporcionara las posibiles acciones que pueda realizar.

<p align="center">
<img src="screenshots/start.png" width="400" >
</p>
<p align="center">
<img src="screenshots/TelegramBot2.png" width="800" >
</p>

### Consulta de tareas disponibles

<p align="center">
<img src="screenshots/help.png" width="400" >
</p>

## Prueba

Puedo validar que el bot este funcionando ejecutando el comando /chiste en Telegram

<p align="center">
<img src="screenshots/chiste.png" width="800" >
</p>


## Proceso :robot:

### Envío IoC al Bot

<p align="center">
<img src="screenshots/ios.png" width="400" >
</p>

### Impacto del IoC en Trend Micro Vision One en sección de indicadores de compromiso

<p align="center">
<img src="screenshots/iocv1.png" width="800" >
</p>

### Indicarle al Bot que aisle un Endpoint

<p align="center">
<img src="screenshots/aislar.png" width="400" >
</p>

### Indicarle al Bot que restablezca un Endpoint

<p align="center">
<img src="screenshots/recuperar.png" width="400" >
</p>

### Impacto del acciones de respuesta globales en Trend Micro Vision One

<p align="center">
<img src="screenshots/respuestaioc.png" width="800" >
</p>
