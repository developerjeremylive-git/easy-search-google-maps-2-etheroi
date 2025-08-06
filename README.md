# Google Maps 3D Interactive Application

Esta aplicación es una implementación interactiva de Google Maps 3D que permite visualizar y manipular las coordenas por medio de click en un entorno de mapa satelital.

## Características

- ✅ Mapa 3D interactivo con vista satelital
- ✅ Controles de posición (latitud, longitud, altitud)
- ✅ Diferentes modos de vista (Satélite, Híbrido, Terreno)
- ✅ Interfaz intuitiva con paneles de control

## Requisitos Previos

1. **Google Maps API Key**: Necesitas una clave de API de Google Maps con los siguientes servicios habilitados:
   - Maps JavaScript API
   - Earth Engine API
2. **Servidor web local**: Recomendado para evitar problemas de CORS

## TODO

- ✅ Implementar la funcionalidad de búsqueda de coordenadas
- [ ] Implementar el colab de Earth Engine Google Maps para la obtencion de datos de satelite
- [ ] Implementar la funcionalidad de visualizacion de datos de satelite


## API Earth Engine Google Maps
https://colab.research.google.com/drive/14m0skX-Amxz5yz7Dpo2rJLD-fxxHXk7x?usp=sharing

## Instalación y Configuración

### 1. Obtener la API Key de Google Maps

1. Ve a [Google Cloud Console](https://console.cloud.google.com/)
2. Crea un nuevo proyecto o selecciona uno existente
3. Habilita las siguientes APIs:
   - Maps JavaScript API
   - Earth Engine API
4. Crea credenciales (API Key)
5. Restringe la API Key a tu dominio (recomendado)

### 2. Configurar la Aplicación

✅ **¡API Key ya configurada automáticamente!**

La aplicación ahora carga la API Key desde el archivo `.env`, por lo que **no necesitas modificar cada archivo HTML manualmente**.

1. **Crea el archivo `.env` en la raíz del proyecto**:
   ```
   GOOGLE_MAPS_API_KEY=tu_clave_real_aqui
   ```

2. **Verifica la configuración**:
   - Abre `http://localhost:8000/api-test.html`
   - La aplicación cargará automáticamente tu clave desde el archivo `.env`

**⚠️ NOTA**: Si no tienes el archivo `.env` configurado, verás una alerta con instrucciones en la aplicación.

### 3. Ejecutar la Aplicación

#### Opción 1: Python (recomendado)
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

#### Opción 2: Node.js
```bash
# Instalar servidor http-server globalmente
npm install -g http-server

# Ejecutar
http-server -p 8000
```

#### Opción 3: Live Server (VS Code)
1. Instala la extensión "Live Server" en VS Code
2. Abre el proyecto en VS Code
3. Haz clic derecho en `index.html` y selecciona "Open with Live Server"

### 4. Abrir la Aplicación

Una vez iniciado el servidor, abre tu navegador y ve a:
```
http://localhost:8000
```

#### Para ver todas las demos disponibles:\```
http://localhost:8000/index-demo.html
```

Este archivo incluye enlaces a:
- **Aplicación principal completa** (`index.html`)
- **Ejemplos de documentación** (`examples.html`)
- **Demo rápida** (`quick-demo.html`)
- **Herramienta de prueba API** (`api-test.html`)

## Uso de la Aplicación

### Controles del Mapa
- **Latitud/Longitud**: Ajusta la posición del centro del mapa
- **Altitud**: Controla la altura de la cámara (0-5000 metros)
- **Modo de Vista**: Cambia entre Satélite, Híbrido y Terreno

## Solución de Problemas

### ❌ Error: Failed to load Google Maps API

**Síntoma**: `Failed to load: https://maps.googleapis.com/maps/api/mapsjs/gen_204?csp_test=true`

**Causas comunes**:
1. **API Key inválida o no configurada**
2. **Servicios de API no habilitados**
3. **Restricciones de dominio incorrectas**
4. **Problemas de facturación en Google Cloud**

**Solución paso a paso**:

#### 1. Verificar la API Key
- Abre `index.html` y busca la línea 338
- Reemplaza `SyCtA5WnjZnY03AIzaSyCtA5WnjZnY03` con tu clave real
- **NO uses la clave proporcionada** - es solo un ejemplo

#### 2. Verificar servicios habilitados
En [Google Cloud Console](https://console.cloud.google.com/):
1. Ve a "APIs y servicios" → "Biblioteca"
2. Busca y habilita:
   - ✅ Maps JavaScript API
   - ✅ Maps SDK for JavaScript

#### 3. Configurar restricciones
1. Ve a "Credenciales" → Selecciona tu API Key
2. En "Restricciones de aplicación" selecciona "Sitios web"
3. Agrega estos orígenes:
   - `http://localhost:8000`
   - `http://localhost:*`
   - Tu dominio real (cuando esté en producción)

#### 4. Verificar facturación
1. Ve a "Facturación" en Google Cloud Console
2. Asegúrate de tener una cuenta de facturación activa
3. Google Maps requiere facturación habilitada

#### 5. Probar la API Key
Abre esta URL en tu navegador (reemplaza con tu clave):
```
https://maps.googleapis.com/maps/api/js?key=TU_CLAVE_AQUI&callback=console.log&v=beta&libraries=maps3d
```
Debe mostrar un mensaje de éxito o error específico.

### Error de API Key
- Verifica que tu API Key esté correctamente configurada
- Asegúrate de que los servicios necesarios estén habilitados
- Comprueba las restricciones de dominio en tu API Key

### Problemas de CORS
- Siempre usa un servidor local (no abras el archivo directamente)
- Verifica que tu API Key esté configurada para tu dominio local

### Modelos no se muestran
- Verifica tu conexión a internet
- Comprueba la consola del navegador para errores
- Asegúrate de que los modelos estén cargando correctamente

## Estructura del Proyecto

```
HackatonGoogleMapsAPI/
├── index.html          # Aplicación principal completa
├── README.md           # Este archivo
```

## Tecnologías Utilizadas

- **Google Maps JavaScript API v3 (beta)**
- **HTML5** y **CSS3**
- **JavaScript ES6+**

## Notas Importantes

- Requiere una conexión a internet estable
- El rendimiento puede variar según el dispositivo

## Recursos Adicionales

- [Ejemplos de Google Maps](https://developers.google.com/maps/documentation/javascript/examples)
- [Google Cloud Console](https://console.cloud.google.com/)

## Licencia

Este proyecto es para uso educativo y demostración. Asegúrate de cumplir con los [términos de servicio de Google Maps](https://cloud.google.com/maps-platform/terms/).