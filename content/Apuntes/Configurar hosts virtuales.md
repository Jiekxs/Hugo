+++
archetype = "chapter"
title = "Configurar hosts virtuales"
weight = 3
+++

### Se actualizan los repositorios y el sistema
```bash
sudo apt update 
```
```bash
sudo apt upgrade -y 
```

### Instalar apache
```bash
sudo apt install apache2 -y
```

Para comprobar que se ha instalado correctamente utilizamos este comando para ver el estado del servicio:
```bash
sudo systemctl status apache2
```
![Estado Servicio](/ServerStatus.png)

O podemos poner en el navegador __127.0.0.1__ o __http://localhost/__.

![Estado](/Apache.png)

### Editar el fichero hosts
Editamos el fichero con permisos de super usuario con:

```bash
sudo nano /etc/hosts
```
Nos saldra lo siguiente y añadimos un dominio local.
```bash
127.0.0.1       localhost
127.0.1.1       JMSI
127.0.0.1       juego.com

::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```

Comprobamos el dominio el que hemos creado, ponemos en el navegador juego.com y nos tendria que aparecer lo siguiente: 

![Host](/Host_Comprob.png)

### Cambio de permisos
Vamos al directorio donde se ubican los html y cambiamos los permisos:

```bash
cd  /var/www/
```
Luego cambiamos el propietario.
```bash
sudo chown j:www-data html -R
```
Y reamos una carpeta para guardar nuestra web y le cambiamos los propietarios.

```bash
sudo mkdir juego
```
```bash
sudo chown j:www-data juego -R
```

![Permisos](/Permisos.png)

### Crear o cargar un html
Creamos o cargamos un archivo .html en nuestra carpeta creada anteriormente, en mi caso ya tengo un html creado.

![html](/html.png)

### Archivo .conf

Nos movemos a los ficheros de configuración de apache los sitios disponibles y creamos un nuevo archivo de configuración con el contenido de 000-default.conf.

```bash
cd /etc/apache2/sites-available/
```

```bash
sudo nano juego.conf
```
![conf](/conf.png)

Dentro del fichero modificamos el documentRoot a donde tenemos nuestra web y el nombre del servidor igual que el host virtual creado anteriormente.

```bash
<VirtualHost *:80>
    
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/juego/P1
        ServerName juego.com
        
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>
```

### Habilitar el sitio
Para habilitar el sitio tenemos que utilizar este comando y reiniciamos el servicio de apache.

```bash
sudo a2ensite juego
```

Una vez reiniciado el servicio ya podremos acceder a nuestra web.

![seo](/seo.png)


**__(Si sale la pagina por defecto de apache hay que revisar que todo esté bien escrito y borrar la cache del DNS con “sudo resolvectl flush-caches” si borrando la cache sigue sin ver la página en el navegador en modo incógnito)__**





