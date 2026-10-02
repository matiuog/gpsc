# GPS a WhatsApp 📍💬

[![Vercel](https://img.shields.io/badge/Deploy-Vercel-black?style=for-the-badge&logo=vercel)](https://gpsc-beta.vercel.app)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)

Aplicación web ultra ligera, responsiva y **mobile-first** construida en un único archivo `index.html` con Tailwind CSS. Permite a los usuarios obtener sus coordenadas GPS satelitales de alta precisión y compartirlas de inmediato en WhatsApp con un solo clic.

Especialmente adaptada y optimizada para **adultos mayores y personas con poca experiencia tecnológica**.

🚀 **Demo en Vivo:** [https://gpsc-beta.vercel.app](https://gpsc-beta.vercel.app)

---

##  Características Principales

* 📡 **GPS Satelital Real:** Utiliza `navigator.geolocation.watchPosition` con `enableHighAccuracy: true` y `maximumAge: 0` para obtener la posición satelital exacta (precisión de 5 a 15 metros), eliminando estimaciones erróneas por IP.
* ⚡ **Redirección en 1 Toque:** Al pulsar el botón, en cuanto se fija la posición, redirige automáticamente a WhatsApp con el mensaje y el pin de Google Maps listo para enviar.
* 👴 **Diseño Accesible (Modo Sencillo):** Botón verde gigante, tipografía de alto contraste e instrucciones claras paso a paso.
* 🔗 **Parámetro de URL para Grupos:** Permite compartir un enlace preconfigurado con el número de destino (ej. `?to=50375801638`), ocultando formularios y dejando solo el botón de envío.
* 🍎 **Optimizado para iOS y Android:** Manejo nativo de permisos y protocolos de apertura de WhatsApp (`wa.me`).
* ☁️ **Serverless & Listo para Vercel:** Despliegue estático instantáneo con HTTPS gratuito (obligatorio para geolocalización en navegadores móviles).

---

## 👥 Uso con Enlace Preconfigurado para Grupos

Para enviar a un grupo de WhatsApp y que los participantes compartan su ubicación hacia un número en 1 toque:

```text
https://gpsc-beta.vercel.app/?to=50375801638
```

1. La persona entra al enlace desde su móvil.
2. Toca el botón verde gigante: **"TOCAR AQUÍ PARA ENVIAR"**.
3. Presiona **"Permitir"** cuando el navegador solicite acceso a la ubicación.
4. WhatsApp se abrirá automáticamente con el mapa de Google Maps listo para enviar.

---

## 🚀 Despliegue en Vercel

```bash
# Instalar Vercel CLI y desplegar a producción
npx vercel --prod
```

## 💻 Desarrollo Local

```bash
# Iniciar servidor local
npm start
# o con Python
python3 -m http.server 3000
```

Visita [http://localhost:3000](http://localhost:3000) en tu navegador.

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Libre para uso personal o comercial.
