# Arquitectura del Proyecto API Gateway

## Introducción

Este documento describe la arquitectura del API Gateway desarrollado para el proyecto League Platform. El API Gateway actúa como un intermediario entre los clientes y los microservicios, gestionando el enrutamiento de las solicitudes y proporcionando una capa de abstracción.

## Componentes Principales

1. **NGINX**: 
   - Se utiliza como un servidor proxy inverso para manejar el tráfico HTTP.
   - La configuración global se encuentra en `nginx/nginx.conf`, donde se definen las directivas generales y configuraciones de rendimiento.
   - Las rutas y el comportamiento del proxy se configuran en `nginx/conf.d/default.conf`, donde se especifican los microservicios a los que se redirige el tráfico.

2. **Scripts**:
   - El script `scripts/setup.sh` se encarga de la instalación y configuración inicial del proyecto, facilitando la preparación del entorno de desarrollo o producción.

3. **Docker**:
   - El archivo `docker/Dockerfile` define la imagen de Docker necesaria para levantar el API Gateway con NGINX, especificando las instrucciones para construir la imagen.
   - `docker-compose.yml` orquesta el levantamiento del servicio de NGINX y otros contenedores requeridos para el funcionamiento del proyecto.

4. **Documentación**:
   - La documentación del proyecto se encuentra en `README.md`, que incluye instrucciones de uso, características y detalles sobre la implementación.
   - El archivo `.env.example` proporciona un ejemplo de las variables de entorno necesarias, que pueden ser personalizadas según el entorno.

## Interacción entre Componentes

El flujo de trabajo típico es el siguiente:

1. Los clientes envían solicitudes HTTP al API Gateway.
2. NGINX recibe estas solicitudes y, basado en la configuración en `default.conf`, las redirige al microservicio correspondiente.
3. Los microservicios procesan las solicitudes y devuelven las respuestas al API Gateway.
4. NGINX envía las respuestas de vuelta a los clientes.

## Conclusión

La arquitectura del API Gateway está diseñada para ser modular y escalable, permitiendo la fácil adición de nuevos microservicios y la gestión eficiente del tráfico. La separación de configuraciones y scripts facilita el mantenimiento y la implementación en diferentes entornos.