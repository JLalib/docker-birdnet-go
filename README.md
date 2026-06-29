# Docker BirdNET-Go 🐦

BirdNET-Go es un analizador de paisaje sonoro en tiempo real que identifica aves, murciélagos y vida silvestre por su sonido usando IA local. Escucha el micrófono de tu computadora (o un micrófono USB externo) y detecta automáticamente qué aves están cantando, enviándote alertas en tiempo real.

## 🚀 Características Principales

- **Identificación en tiempo real:** Más de 6,500 especies de aves con el modelo BirdNET v2.4.
- **Múltiples modelos IA:** Soporta BirdNET v2.4 y Google Perch v2 (hasta 14,795 especies de fauna).
- **Deep Detection:** Confirmación de detección para reducir falsos positivos.
- **Filtro Geográfico:** Basado en coordenadas GPS para detectar solo aves de tu zona.
- **Alertas Multicanal:** Notificaciones vía Discord, Slack, Telegram, ntfy, Pushover, Gotify, Matrix, webhooks, MQTT y scripts de shell.
- **Dashboard Web:** Visualización en tiempo real, histórico de detecciones y espectrogramas.
- **Integración con BirdWeather:** Comparte tus detecciones con la red global de ciencia ciudadana.
- **Bajo Consumo:** Diseñado para correr 24/7 en Raspberry Pi 3 o superior.

## 🛠️ Requisitos del Sistema

- **Hardware:** Raspberry Pi 3 o equivalente (Arquitectura ARM 64-bit). Se recomienda Pi 4 para un análisis más rápido.
- **RAM:** Mínimo 1-2 GB (SQLite), recomendado 2-4 GB (MySQL).
- **Almacenamiento:** 5 GB o más para base de datos y modelos.
- **Audio:** Micrófono USB externo recomendado.
- **Software:** Docker y Docker Compose instalados.

## 📦 Instalación con Docker Compose

### 1. Clonar el repositorio o crear la carpeta
```bash
mkdir birdnet-go && cd birdnet-go
```

### 2. Crear el archivo `docker-compose.yml`
Copia el contenido del archivo `docker-compose.yml` incluido en este repositorio.

### 3. Desplegar el servicio
```bash
docker compose up -d
```

### 4. Acceder al Dashboard
Abre tu navegador y entra en: `http://localhost:8080`

## ⚙️ Primeros Pasos

1. **Configuración Inicial:** Sigue el asistente (Wizard) al entrar por primera vez.
2. **Ubicación:** Ve a `Settings → Location` e ingresa tus coordenadas GPS para activar el filtro regional.
3. **Modelo IA:** En `Analysis → Model Selection`, elige entre BirdNET v2.4 o Google Perch v2.
4. **Fuente de Audio:** En `Settings → Audio Input`, selecciona tu micrófono y ajusta la sensibilidad usando el VU meter.
5. **Alertas:** Configura tu destino preferido en `Settings → Notifications → Alerts`.

## 🛡️ Seguridad y Mantenimiento

- **Logs:** `docker logs -f birdnet-go`
- **Backup:** `docker exec birdnet-go cp /data/birdnet.db /data/birdnet-backup-$(date +%Y%m%d).db`
- **Actualización:** `docker compose pull && docker compose up -d`
- **Estadísticas:** `docker stats birdnet-go`

---
*Basado en el tutorial de [Genbyte](https://genbyte.blogspot.com/)*
