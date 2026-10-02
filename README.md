# GPS a WhatsApp 📍💬 (Listo para Vercel)

Aplicación web ultra ligera, responsiva y mobile-first construida en un único archivo `index.html` con Tailwind CSS para obtener coordenadas GPS de alta precisión y compartirlas directamente a través de WhatsApp.

Optimizada para **desplegarse en Vercel** en segundos y compartir un enlace en grupos de WhatsApp donde los miembros pueden enviar sus coordenadas con **un solo clic**.

---

## ⚡ Cómo Desplegar en Vercel

Vercel ofrece hosting gratuito con **HTTPS automático**, lo cual es indispensable para que los navegadores en teléfonos móviles (iOS Safari, Android Chrome) permitan el acceso al GPS.

### Opción A: Desde la Terminal (Recomendada y más rápida)
En la carpeta del proyecto, ejecuta:
```bash
npx vercel
```
1. Si te pide iniciar sesión, pulsa Enter para autenticarte en tu navegador.
2. Acepta las opciones por defecto (`Set up and deploy? [Y]`, `scope`, `link to existing project? [N]`).
3. ¡Listo! Vercel te entregará una URL como `https://gpsc-whatsapp.vercel.app`.

Para desplegar a producción definitiva:
```bash
npx vercel --prod
```

### Opción B: Con GitHub + Vercel Web
1. Crea un repositorio en [GitHub](https://github.com/new).
2. Sube tu código:
   ```bash
   git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
   git branch -M main
   git push -u origin main
   ```
3. Ve a [vercel.com/new](https://vercel.com/new), selecciona tu repositorio y haz clic en **Deploy**.

---

## 👥 Cómo Enviar el Enlace a un Grupo de WhatsApp

### 1. Con tu número preconfigurado (Experiencia de 1 Clic para los miembros):
Si quieres que las personas del grupo te envíen su ubicación a ti, añade tu número con código de país al final del link:
```text
https://tu-proyecto.vercel.app/?to=34612345678
```
> *(Reemplaza `34612345678` por tu número completo sin signos ni espacios).*

**¿Qué verá la persona al abrir tu link en WhatsApp?**
1. Abre el enlace en su móvil.
2. Verá un banner: *"📍 Solicitud de ubicación: Pulsa el botón para enviar tus coordenadas a +34 612 345 678"*.
3. Pulsa el botón **"Compartir mi ubicación"** (1 solo toque).
4. Su teléfono obtiene el GPS de alta precisión y abre WhatsApp enviándote la ubicación con enlace directo a Google Maps.

*(Nota: La misma aplicación incluye una herramienta interna plegable que genera y copia este enlace con tu número automáticamente).*

### 2. Enlace genérico (Para que cada persona elija a qué chat o grupo enviarlo):
Si envías el enlace limpio:
```text
https://tu-proyecto.vercel.app/
```
Las personas pueden ingresar un número específico o activar **"¿Elegir chat/grupo al enviar?"**, lo que abrirá el selector nativo de WhatsApp para enviar sus coordenadas al grupo o contacto que deseen.

---

## 🛠️ Pruebas en Local

Si deseas probar antes de desplegar:
```bash
python3 -m http.server 3000
# o
npm start
```
Abre en tu navegador: [http://localhost:3000](http://localhost:3000)
