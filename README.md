# API Gateway

Este es un API Gateway personalizado construido con NGINX para el proyecto League Platform. Maneja el enrutamiento del tráfico HTTP a varios microservicios backend y soporta entornos de QA y producción.

## Estructura del Proyecto

El proyecto tiene la siguiente estructura de archivos:

```
api-gateway
├── nginx
│   ├── nginx.conf          # Configuración global de NGINX
│   └── conf.d
│       └── default.conf    # Configuración principal de NGINX
├── scripts
│   └── setup.sh            # Script de instalación e inicialización
├── docker
│   └── Dockerfile          # Definición de la imagen de Docker
├── .env.example             # Ejemplo de variables de entorno
├── docker-compose.yml       # Orquestador de servicios
├── README.md                # Documentación del proyecto
└── docs
    └── architecture.md      # Documentación sobre la arquitectura del proyecto
```

## Características

- Configuración de proxy inverso con NGINX
- Enrutamiento centralizado para microservicios
- Listo para despliegue en Docker
- Fácil separación de entornos (QA/Prod)

## Uso

Clona el repositorio y despliega a través de Docker:

```bash
docker compose up -d
```

## Documentación

Para más detalles sobre la arquitectura del proyecto, consulta el archivo [architecture.md](docs/architecture.md).