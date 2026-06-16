# Configuración EmailJS para FlowGuard

## Paso 1 — Crear cuenta
Ve a https://emailjs.com y crea cuenta gratuita (200 correos/mes gratis)

## Paso 2 — Conectar tu correo (Email Service)
1. En el panel → "Email Services" → "Add New Service"
2. Elige Gmail (o el que uses)
3. Conecta tu cuenta de Google
4. Copia el **Service ID** (ej: service_abc123)

## Paso 3 — Crear plantilla (Email Template)
1. Panel → "Email Templates" → "Create New Template"
2. Configura así:

### Asunto:
{{tipo}} - FlowGuard · {{empresa}}

### Cuerpo del correo:
Hola {{to_name}},

{{mensaje}}

---
Tubería afectada: {{tuberia}}
Flujo actual: {{flujo}}

---
Este mensaje fue generado automáticamente por FlowGuard.
Sistema de monitoreo de tuberías industriales.

3. En "To Email" pon: {{to_email}}
4. Guarda y copia el **Template ID** (ej: template_xyz789)

## Paso 4 — Obtener Public Key
1. Panel → "Account" → "General"
2. Copia tu **Public Key** (ej: aBcDeFgHiJkLmNoP)

## Paso 5 — Pegar en el código
Abre index.html y busca estas 3 líneas cerca del final (línea ~420):

  const EMAILJS_PUBLIC_KEY  = 'TU_PUBLIC_KEY';
  const EMAILJS_SERVICE_ID  = 'TU_SERVICE_ID';
  const EMAILJS_TEMPLATE_ID = 'TU_TEMPLATE_ID';

Reemplaza los valores entre comillas con tus datos reales:

  const EMAILJS_PUBLIC_KEY  = 'aBcDeFgHiJkLmNoP';
  const EMAILJS_SERVICE_ID  = 'service_abc123';
  const EMAILJS_TEMPLATE_ID = 'template_xyz789';

## Paso 6 — Volver a subir a Netlify
Arrastra nuevamente la carpeta flowguard a Netlify.
¡Listo! Los correos llegarán de verdad.

---

## ¿Qué correos envía la app?

1. CÓDIGO OTP — Al crear cuenta, llega el código de verificación de 6 dígitos
2. ALERTA DE SENSOR — Al tocar "Notificar al equipo", llega el estado del flujo y la alerta
3. MANTENCIÓN COMPLETA — Al marcar "✅ Mantención lista", llega confirmación al correo
