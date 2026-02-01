# Gender Reveal Invitation Page 🎉

Una hermosa página web interactiva para invitar a amigos y familia a tu Gender Reveal.

## ✨ Características

- ✅ **Video Player**: Reproducción de video personalizado
- ✅ **Mapa Interactivo**: Integración con Google Maps
- ✅ **Sistema de Votación en Tiempo Real**: Usando Firebase Realtime Database
- ✅ **Formulario RSVP**: Con confirmación por email vía EmailJS
- ✅ **Contador Regresivo**: Hasta el día del evento
- ✅ **Emails Automáticos**: Notificación al admin y confirmación al invitado
- ✅ **Link de Calendario**: Para agregar el evento a Google Calendar
- ✅ **Animaciones**: Efectos de confetti al confirmar asistencia
- ✅ **Diseño Responsive**: Se adapta a móviles, tablets y desktop

## 📋 Detalles del Evento

- **Fecha**: 8 de Febrero, 2026
- **Hora**: 2:00 PM (Hora de Colombia)
- **Ubicación**: Bogotá, Colombia

## 🚀 Cómo Usar

### 1. Abrir la Página

Simplemente abre el archivo `code.html` en tu navegador web.

### 2. Prueba las Funcionalidades

#### Video:

- Click en el botón de play para reproducir el video
- Click en la barra de progreso para saltar a una parte específica
- Click en el video para pausar/reproducir

#### Votación:

- Cada persona puede votar UNA vez (se guarda en el navegador)
- Los votos se actualizan en tiempo real para todos los visitantes
- Los votos se almacenan en Firebase

#### RSVP (Confirmar Asistencia):

1. Completa el formulario con tu nombre
2. Selecciona el número de invitados
3. Agrega un mensaje opcional
4. Click en "Confirmar mi Asistencia"
5. Ingresa tu email cuando se te pida
6. Recibirás un email de confirmación con link al calendario

## 🔧 Servicios Configurados

### Firebase Realtime Database

- **Proyecto**: gender-reveal-d667e
- **Almacena**: Votos en tiempo real y RSVPs
- **Acceso**: Lectura pública, escritura controlada

### EmailJS

- **Service ID**: service_y1ngbpb
- **Template Admin**: template_xchd5rh (envía notificación a jcarl.30@gmail.com)
- **Template Guest**: template_icgf8ur (envía confirmación al invitado)

### Google Maps

- **Ubicación**: 4.848623032684249, -74.04543487709674
- **Integrado**: Con iframe embebido

## 📧 Emails que se Envían

### Email al Admin (tú):

Cuando alguien confirma asistencia, recibes un email con:

- Nombre del invitado
- Número de personas
- Mensaje especial (si lo dejaron)

### Email al Invitado:

El invitado recibe:

- Confirmación de asistencia
- Detalles del evento (fecha, hora, ubicación)
- Link directo a Google Maps
- Link para agregar al calendario

## 🎨 Personalización

### Cambiar Colores:

Los colores están definidos en el config de Tailwind (líneas 14-22):

```javascript
"primary-lavender": "#E1D5E7",
"accent-lavender": "#B39DDB",
"soft-pink": "#FCE4EC",
"deep-pink": "#F06292",
"soft-blue": "#E3F2FD",
"deep-blue": "#64B5F6",
```

### Cambiar Textos:

Simplemente edita el HTML en las secciones correspondientes.

### Cambiar Video:

Reemplaza el archivo `video.mov` con tu video (mantén el mismo nombre o actualiza el src en el HTML).

## 🔒 Seguridad

### Firebase Rules Aplicadas:

```json
{
  "rules": {
    "votes": {
      ".read": true,
      "girl": {
        ".write": true,
        ".validate": "newData.isNumber() && newData.val() >= 0"
      },
      "boy": {
        ".write": true,
        ".validate": "newData.isNumber() && newData.val() >= 0"
      }
    },
    "rsvps": {
      ".read": true,
      "$rsvpId": {
        ".write": true,
        ".validate": "newData.hasChildren(['name', 'guests', 'timestamp'])"
      }
    }
  }
}
```

### Prevención de Spam:

- Los votos están limitados a 1 por navegador (localStorage)
- Para más seguridad, considera agregar validación por IP en Firebase

## 📊 Ver los Datos

### Ver Votos y RSVPs:

1. Ve a: https://console.firebase.google.com/
2. Selecciona tu proyecto: "gender-reveal-d667e"
3. Click en "Realtime Database"
4. Verás todos los votos y confirmaciones

### Ver Emails Enviados:

1. Ve a: https://dashboard.emailjs.com/
2. Click en "Email History"
3. Verás el historial de todos los emails enviados

## 🌐 Hosting (Publicar en Internet)

Para compartir la página con tus invitados, puedes subirla a:

### Opción 1: Firebase Hosting (Gratis)

```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

### Opción 2: Netlify (Gratis, más fácil)

1. Ve a: https://www.netlify.com/
2. Arrastra la carpeta con tus archivos
3. ¡Listo! Te dan un link automáticamente

### Opción 3: GitHub Pages (Gratis)

1. Sube los archivos a un repositorio de GitHub
2. Activa GitHub Pages en la configuración
3. Tu página estará en: `https://tu-usuario.github.io/repo-name`

## 📱 Compartir con Invitados

Una vez publicada, comparte el link por:

- WhatsApp
- Email
- Redes sociales
- Mensaje de texto

## 🐛 Solución de Problemas

### El video no carga:

- Verifica que `video.mov` esté en la misma carpeta que `code.html`
- Algunos navegadores no soportan formato .mov, considera convertir a .mp4

### Los votos no se actualizan:

- Verifica que las reglas de Firebase estén aplicadas correctamente
- Revisa la consola del navegador (F12) para ver errores

### Los emails no llegan:

- Verifica que los IDs de EmailJS sean correctos
- Revisa el spam/correo no deseado
- Verifica el historial en el dashboard de EmailJS

### El mapa no se ve:

- Verifica tu conexión a internet
- El API key de Google Maps está en uso

## 📞 Soporte

Si tienes problemas:

1. Abre la consola del navegador (F12)
2. Revisa los errores en la pestaña "Console"
3. Verifica que todos los servicios externos estén activos

## 🎉 ¡Disfruta tu Gender Reveal!

Esperamos que esta página haga tu evento aún más especial. ¡Felicidades! 👶💙💗
