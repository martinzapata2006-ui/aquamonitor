# FlowGuard — Guía de instalación

## Archivos incluidos
- `index.html` → La app completa
- `manifest.json` → Configuración PWA (nombre, ícono, colores)
- `sw.js` → Service Worker (funciona sin internet + notificaciones)
- `icons/` → Carpeta para los íconos (ver paso 2)

---

## Paso 1 — Crear ícono de la app

Necesitas dos imágenes PNG del ícono de tu app:
- `icons/icon-192.png` (192×192 px)
- `icons/icon-512.png` (512×512 px)

Puedes crear íconos gratis en: https://www.canva.com o https://favicon.io

---

## Paso 2 — Subir a Netlify (gratis, 2 minutos)

1. Entra a https://netlify.com y crea una cuenta gratuita
2. En el panel principal, arrastra la carpeta `flowguard` completa
3. Netlify te entregará una URL tipo: `https://flowguard-abc123.netlify.app`
4. ¡Listo! La app ya está en internet

---

## Paso 3 — Instalar en iPhone (Safari)

1. Abre Safari en el iPhone (debe ser Safari, no Chrome)
2. Entra a tu URL de Netlify
3. Toca el botón de compartir (cuadrado con flecha hacia arriba)
4. Toca "Añadir a pantalla de inicio"
5. Ponle nombre y toca "Añadir"

La app aparecerá como ícono en tu pantalla de inicio, igual que una app nativa.

---

## Paso 4 — Instalar en Android (Chrome)

1. Abre Chrome y entra a tu URL
2. Aparecerá automáticamente un banner "Instalar FlowGuard"
3. Toca "Instalar"

También puedes ir al menú (tres puntos) → "Añadir a pantalla de inicio"

---

## Próximos pasos (cuando tengas sensores reales)

Para conectar sensores físicos necesitarás:
1. Un backend (Node.js, Python Flask, etc.) que reciba los datos del sensor
2. Reemplazar la función `startLive()` en `index.html` por llamadas a tu API
3. Para notificaciones push reales: servidor con Web Push Protocol

---

## Seguridad implementada

- Verificación de correo corporativo por código OTP
- Token JWT simulado (listo para conectar a backend real)
- Cifrado AES-256 (referenciado en UI, implementar en backend)
- Acceso exclusivo por empresa tras verificación

---

Contacto de soporte: agregar cuando el sistema esté en producción
