# Gestión Tecnológica

## Integrantes
- María Camila Guerrero Giraldo
- Cristian Camilo Cuervo Castillo
- Neider Alejandro Fajardo Cardona
- Edvard Frederick Bareño
- Nicolás Steeven Rivera Rincón
- Miguel Angel Vega Alonso

# PROYECTO FINAL 
Cuando se trabaja con una arquitectura de Microservicios. A veces es posible que una instancia de un servicio sea incapaz de manejar las peticiones y aún así estar en ejecución. Por ejemplo, podría haberse quedado sin conexiones a la base de datos. Cuando esto ocurre, debería haber un sistema de monitoreo el cual genere una alerta. 

## Problema
¿Cómo detectar que una instancia de servicio en ejecución no es capaz de gestionar las solicitudes?

## Solución
Un servicio tiene un punto final de la API de comprobación de estado (por ejemplo, HTTP /health) que devuelve el estado del servicio. El gestor de puntos finales de la API realiza varias comprobaciones, como por ejemplo:

- El estado de las conexiones a los servicios de infraestructura utilizados por la instancia de servicio.
- El estado del host, por ejemplo, espacio en disco.
- Lógica específica de la aplicación.

Un cliente de comprobación de estado - un servicio de supervisión, un registro de servicio o un equilibrador de carga - invoca periódicamente el punto final para comprobar el estado de la instancia de servicio. A esto se le denomina Healt check.

## Herramienta

### Statping - Status Page & Monitoring Server
![statping](https://camo.githubusercontent.com/31b7357212895580ce171f0eb14662b2d5495929/68747470733a2f2f73332d75732d776573742d322e616d617a6f6e6177732e636f6d2f676974696d67732f7374617470696e672e706e67)

[Statping](https://github.com/hunterlong/statping) es una herramienta open-source que permite gestionar el estado de sitios web y aplicaciones. Statping automáticamente obtiene la aplicación y le muestra una página de estado con funciones que permiten visualizar y gestión el estado del sitio web. Puede ser utilizado con motores de bases de datos como MySQL, Postgres o SQLite en múltiples sistemas operativos.


## Configuración
Statping permite la gestión de los estados mediante un servicio estadístico que muestra en tiempo real la actividad del sitio web o aplicación realizando peticiones automáticas dado un determinado tiempo.

![Statping](https://raw.githubusercontent.com/Miavega/healt_check_gestion/master/estadisticas.gif)

Así mismo, permite almacenar logs para llevar una trazabilidad de los estados de la aplicación. Para esto es necesario darle una base de datos en la cual pueda guardar la información, en este caso se configuró una base de datos PosgreSQL.

![Statping](https://raw.githubusercontent.com/Miavega/healt_check_gestion/master/base_datos.png)

### UNIVERSIDAD DISTRITAL FRANCISCO JOSÉ DE CALDAS
### 2019
