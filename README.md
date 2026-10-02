# GPS a WhatsApp 📍💬

Aplicación web ligera, responsiva y mobile-first construida en un único archivo `index.html` con Tailwind CSS para obtener las coordenadas GPS del dispositivo con alta precisión y compartirlas directamente a través de WhatsApp con enlace a Google Maps.

## 🚀 Inicio Rápido (Servidor Local)

Para acceder a la API de geolocalización de los navegadores modernos (`navigator.geolocation`), se requiere que la página se sirva desde un entorno seguro (`localhost` o `https://`).

### Opción 1: Con Python 3 (Sin instalar nada)
```bash
python3 -m http.server 3000
```
Luego abre en tu navegador: [http://localhost:3000](http://localhost:3000)

### Opción 2: Con Node / NPM
```bash
npm start
# O si prefieres:
npx serve -l 3000 .
```

---

## 📱 Probar en un teléfono móvil real

Si deseas probar la aplicación en tu propio smartphone conectado a la misma red Wi-Fi:

1. Inicia el servidor local:
   ```bash
   python3 -m http.server 3000
   ```
2. Obtén la IP local de tu ordenador (por ejemplo, en Mac: `ipconfig getifaddr en0` o revisa Ajustes de Red).
3. Abre en tu móvil: `http://TU_IP_LOCAL:3000`.
   > **Nota importante sobre móviles:** Los navegadores móviles modernos (iOS Safari y Android Chrome) exigen HTTPS para geolocalización fuera de `localhost`. Para desarrollo móvil puedes utilizar herramientas con túnel HTTPS automático como:
   > ```bash
   > npx cloudflared tunnel --url http://localhost:3000
   > # o
   > npx ngrok http 3000
   > ```

---

## 🛠️ Características Técnicas

- **Diseño Mobile-First**: Estilos modernos con Tailwind CSS vía CDN, animaciones tipo radar de satélite y soporte táctil (`active:scale-[0.98]`).
- **Geolocalización de Alta Precisión**:
  - `enableHighAccuracy: true`
  - `timeout: 10000` (10 segundos)
  - `maximumAge: 0` (fuerza lectura en tiempo real sin caché)
- **Manejo de Estados**:
  - **Carga**: Spinner y animación radar con mensajes descriptivos.
  - **Éxito**: Muestra latitud, longitud, badge de precisión en metros (`±X m`), botón para copiar coordenadas y botón de vista previa en Google Maps.
  - **Errores amigables**: Diferenciación de permiso denegado, GPS no disponible, timeout y navegador no compatible.
- **Integración con WhatsApp**:
  - Sanitización automática del número (código internacional sin signos ni espacios).
  - Enlace universal `https://wa.me/<NUMERO>?text=<MENSAJE>` codificado con `encodeURIComponent`.
  - Enlace directo a Google Maps (`https://maps.google.com/?q=LAT,LON`).
- **Persistencia**: Recuerda el último número ingresado y código de país en `localStorage`.
