# Servicio de notificaciones

Genera y almacena notificaciones dentro de la aplicación a partir de eventos de reservas y pagos.

## Responsabilidades

- Consume eventos de dominio y ofrece consultas de notificaciones y preferencias.
- El servicio no implementa envío por correo electrónico ni notificaciones push.

## Tecnologías

TypeScript, NestJS, PostgreSQL y RabbitMQ.

## Arquitectura C4

El diagrama muestra una **vista de contenedores C4** centrada en este componente y sus relaciones relevantes. Se genera desde [Structurizr DSL](docs/architecture/workspace.dsl) con los estilos predeterminados, sin colores personalizados. Las flechas indican la dirección de cada interacción. El diagrama se conserva en inglés.

![Diagrama C4 de Servicio de notificaciones](docs/architecture/containers.svg)

Para consultar o regenerar el diagrama, abra `docs/architecture/workspace.dsl` en Structurizr. Con Structurizr CLI y Graphviz instalados:

```sh
structurizr.sh validate -workspace docs/architecture/workspace.dsl
mkdir -p /tmp/parklink-diagram
structurizr.sh export -workspace docs/architecture/workspace.dsl -format dot -output /tmp/parklink-diagram
dot -Tsvg /tmp/parklink-diagram/structurizr-Containers.dot -o docs/architecture/containers.svg
```

## Compilación en el espacio integrado

```sh
npm ci
npm run build:shared
npm run build -w @parklink/notification-service
```

## Relación con el proyecto

Este repositorio es una copia independiente de `services/notification-service` en [parklink-platform](https://github.com/1ASI0728-2620-16363-ParkLink/parklink-platform). Use el espacio integrado para la configuración npm, las dependencias compartidas, el contexto de Docker, las pruebas y la infraestructura local. Los repositorios no se sincronizan automáticamente.
