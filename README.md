# Introducción

Este repositorio contiene un ejemplo del fichero de configuración [fig](http://www.fig.sh/index.html) para instanciar un servicio de Plex Media Server. Está basado en el contenedor Docker [luispa/base-plex](https://registry.hub.docker.com/u/luispa/base-plex/) (GitHub [base-plex](https://github.com/LuisPalacios/base-plex)).

Consulta este [apunte técnico sobre varios servicios en contenedores Docker](http://www.luispa.com/?p=172) para ver más ejemplos de uso. 


## Ejecución con "fig"

Para automatizar con el programa [fig](http://www.fig.sh/index.html) y que arranquen el contenedor: descarga y renombra el fichero fig-template.yml y después ejecuta el programa fig: 

    $ git clone https://github.com/LuisPalacios/servicio-plex.git
    :
    $ mv fig-template.yml fig.yml   (edita a tu gusto)
    :
    $ fig up -d


### Volumen

Directorios persistentes donde se ubica la configuración de Plex (/config) y donde espero encontrar las fuentes de video, audio y fotografía (/data). 

    - "/Volumen/A/Configuración/Plex:/config"
    - "/Volumen/Multimedia/:/data"
    - "/Volumen/Timezone/tz:/config/tz"

Directorio persistente para configurar el Timezone. Crear el directorio /Apps/data/tz y dentro de él crear el fichero timezone. Luego montarlo con -v o con fig.yml. 

    $ echo "Europe/Madrid" > /config/tz/timezone

