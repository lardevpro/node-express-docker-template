# Phantom Intelligence - Microservicio de Monitorización

Este repositorio contiene el microservicio base desarrollado en **Node.js** con el framework **Express**, diseñado específicamente para las pruebas de despliegue del módulo **MF0490_3** (Programación de sistemas microinformáticos). 

La aplicación se encuentra completamente contenedorizada utilizando **Docker** y optimizada con una imagen ligera de Linux (`Alpine`) para garantizar un despliegue ágil, aislado y eficiente a través de **Docker Compose**.

## 📁 Estructura y Componentes del Código

El proyecto está compuesto por los siguientes archivos clave:

*   `app.js`: Lógica del servidor Express, configuración del puerto `3000` y definición de las rutas de la API en formato JSON.
*   `Dockerfile`: Fichero de configuración de Docker que utiliza la estrategia de caché de capas (separando la instalación de dependencias `npm install` de la copia del código fuente) sobre la base `node:20-alpine`.
*   `compose.yaml`: Fichero de orquestación de Docker Compose que automatiza la construcción y el mapeo de puertos (`3000:3000`) del servicio `phantom`.
*   `package.json`: Configuración del proyecto, definición del script de inicio (`npm start`) y gestión de dependencias (Express 5.x).

## 🚀 Endpoints de la API

Una vez levantado el servicio, la API expone los siguientes puntos de acceso locales:

*   **Estado del Sistema:** `GET http://localhost:3000/`
    *   Devuelve información básica del entorno de simulación en línea.
*   **Módulo de Monitorización:** `GET http://localhost:3000/objetivos`
    *   Devuelve el listado de registros del sistema con sus respectivos niveles de riesgo y estados.

## 🛠️ Instrucciones de Despliegue Rápido

Para poner en marcha este microservicio en cualquier entorno local, asegúrate de tener instalado [Docker Desktop](https://docker.com) y sigue estos pasos:

1. **Clonar o descargar el proyecto:**
   ```bash
   cd <ruta_de_tu_proyecto>
   ```

2. **Construir y levantar el contenedor:**
   Este comando compilará la imagen optimizada e iniciará el servidor Express automáticamente.
   ```bash
   docker compose up --build
   ```

3. **Ejecutar en segundo plano (Modo Detached):**
   Si prefieres liberar la terminal mientras se ejecuta el servicio, añade el flag `-d`:
   ```bash
   docker compose up -d --build
   ```

## 🐳 Comandos de Mantenimiento

*   **Verificar logs del servicio:**
    ```bash
    docker compose logs -f phantom
    ```
*   **Detener y eliminar los contenedores activos:**
    ```bash
    docker compose down
    ```

## 📝 Especificaciones del Módulo
Este proyecto sirve como artefacto técnico verificable para la gestión y despliegue de servicios en el sistema informático dentro del marco formativo correspondiente.
