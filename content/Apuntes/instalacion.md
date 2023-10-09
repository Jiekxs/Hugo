+++
archetype = "chapter"
title = "Instalación de Hugo"
weight = 2
+++

## Instalación
```bash
sudo snap install hugo
```

Creamos un sitio nuevo: 

```bash
hugo new site Prueba
```

Nos movemos a la carpeta "themes" y hacemos un clonamos el tema del repositorio:

```bash
git clone https://github.com/McShelby/hugo-theme-relearn.git
```
Una vez clonado vamos al archivo hugo.toml y añadimos lo siguiente:

```
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
theme = "relearn"

[outputs]
home = [ "HTML", "RSS", "SEARCH"]
```
Luego en la carpeta content creamos un _index.md con: 
```
+++
archetype = "chapter"
title = "Home"
weight = 1
+++

Lorem Ipsum.
```
![md](/Hugo_md.png)



