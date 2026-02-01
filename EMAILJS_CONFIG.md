# 📧 Configuración de Templates de EmailJS

Esta guía te ayuda a verificar que tus templates de EmailJS estén configurados correctamente.

---

## 🔑 Credenciales Configuradas

```
Service ID: service_y1ngbpb
Public Key: YOmVhs9fDFCrvbXrD
Email Admin: jcarl.30@gmail.com
```

---

## 📝 Template 1: Admin Notification

**Template ID:** `template_xchd5rh`

**Para:** jcarl.30@gmail.com (tú recibes notificación)

**Subject:**

```
Nueva confirmación: {{guest_name}}
```

**Body:**

```
Hola,

Has recibido una nueva confirmación de asistencia:

Nombre: {{guest_name}}
Número de invitados: {{guest_count}}
Mensaje: {{message}}

---
Esta confirmación fue enviada automáticamente desde tu página de Gender Reveal.
```

### Variables que se envían desde el código:

- `guest_name` - Nombre del invitado
- `guest_count` - Número de personas
- `message` - Mensaje especial (o "Sin mensaje")
- `to_email` - jcarl.30@gmail.com

---

## 📝 Template 2: Guest Confirmation

**Template ID:** `template_icgf8ur`

**Para:** Email del invitado

**Subject:**

```
¡Confirmación de Asistencia - Gender Reveal! 🎉
```

**Body:**

```
Hola {{guest_name}},

¡Gracias por confirmar tu asistencia a nuestro Gender Reveal!

📅 Fecha: Domingo, 8 de Febrero 2026
🕐 Hora: 2:00 PM (Hora de Colombia)
📍 Ubicación: Ver mapa → https://maps.google.com/?q=4.848623032684249,-74.04543487709674

Número de invitados confirmados: {{guest_count}}

{{#if message}}
Tu mensaje: "{{message}}"
{{/if}}

¡Estamos muy emocionados de compartir este momento especial contigo!

Puedes agregar el evento a tu calendario usando el archivo adjunto que recibirás por separado.

Con cariño,
La familia Pérez-García

---
💙 Team Boy o 💗 Team Girl? ¡Ya votaste en la página!
```

### Variables que se envían desde el código:

- `guest_name` - Nombre del invitado
- `guest_count` - Número de personas
- `message` - Mensaje especial
- `to_email` - Email del invitado
- `calendar_link` - Link para agregar al calendario de Google

---

## ✅ Verificar Configuración

### Paso 1: Verificar Service

1. Ve a: https://dashboard.emailjs.com/admin
2. Click en "Email Services"
3. Verifica que `service_y1ngbpb` esté activo y conectado

### Paso 2: Verificar Templates

1. Ve a: https://dashboard.emailjs.com/admin/templates
2. Verifica que existan ambos templates:
   - `template_xchd5rh` (Admin Notification)
   - `template_icgf8ur` (Guest Confirmation)

### Paso 3: Probar Templates

1. En cada template, click en "Test It"
2. Completa los campos de prueba:
   ```
   guest_name: Juan Pérez
   guest_count: 2
   message: ¡Qué emoción!
   to_email: tu-email@example.com
   ```
3. Click "Send Test Email"
4. Verifica que llegue el email

---

## 🔧 Si los emails no llegan

### Checklist:

- [ ] El Service está conectado y activo
- [ ] Los Template IDs son correctos
- [ ] El Public Key es correcto
- [ ] Verifica el historial: https://dashboard.emailjs.com/admin/logs
- [ ] Revisa el spam/correo no deseado
- [ ] Verifica el límite de emails (200/mes en plan gratuito)

### Ver historial de emails:

https://dashboard.emailjs.com/admin/logs

Aquí puedes ver:

- ✅ Emails enviados exitosamente
- ❌ Emails que fallaron (con el error)
- 📊 Estadísticas de uso

---

## 📊 Límites del Plan Gratuito

EmailJS Plan Gratuito incluye:

- ✅ 200 emails por mes
- ✅ 2 servicios de email
- ✅ Plantillas ilimitadas
- ✅ Soporte básico

**Cálculo para tu evento:**

- Supongamos 50 invitados confirman
- Cada confirmación = 2 emails (1 a ti + 1 al invitado)
- Total = 100 emails
- ✅ Estás dentro del límite

---

## 🧪 Probar el Flujo Completo

### Test End-to-End:

1. Abre `code.html` en tu navegador
2. Ve a la sección RSVP
3. Completa el formulario:
   ```
   Nombre: Test Usuario
   Invitados: 2 personas
   Mensaje: Esto es una prueba
   ```
4. Ingresa tu email cuando se te pida
5. Click "Confirmar mi Asistencia"

### Verificar:

- [ ] Aparece mensaje de éxito con confetti
- [ ] Recibes email en jcarl.30@gmail.com con notificación
- [ ] Recibes email de confirmación en tu email de prueba
- [ ] El email tiene el link al calendario
- [ ] En Firebase aparece el nuevo RSVP

---

## 💡 Tips Adicionales

### Personalizar los emails:

1. Ve a EmailJS dashboard
2. Edita los templates
3. Agrega logos, colores, o más información
4. Los cambios se aplican inmediatamente (no necesitas actualizar el código)

### Agregar CC o BCC:

En EmailJS, puedes configurar que todos los emails también se envíen a otro email como backup.

### Respuestas automáticas:

EmailJS soporta reply-to addresses para que los invitados puedan responder directamente.

---

## 🎉 ¡Todo Listo!

Si completaste todos los pasos de verificación, tu sistema de emails está 100% funcional.

**Próximos pasos:**

1. ✅ Verifica Firebase (ver `FIREBASE_SETUP.md`)
2. ✅ Publica la página (ver `QUICK_START.md`)
3. ✅ ¡Comparte con tus invitados!

---

## 📞 Links Útiles

- Dashboard EmailJS: https://dashboard.emailjs.com/admin
- Historial de Emails: https://dashboard.emailjs.com/admin/logs
- Documentación: https://www.emailjs.com/docs/
- Templates: https://dashboard.emailjs.com/admin/templates
