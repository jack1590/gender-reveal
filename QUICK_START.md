# 🚀 Guía Rápida de Inicio

## ¿Qué acabo de recibir?

Una página web completamente funcional para tu Gender Reveal con:
- ✅ Reproductor de video
- ✅ Votación en tiempo real
- ✅ Mapa de ubicación
- ✅ Formulario de confirmación
- ✅ Emails automáticos
- ✅ Contador regresivo

---

## ⚡ Inicio Rápido (3 pasos)

### Paso 1: Configurar Firebase Database

1. Ve a: https://console.firebase.google.com/project/gender-reveal-d667e/database
2. Click en "Create Database" (Realtime Database)
3. Aplica las reglas que están en `FIREBASE_SETUP.md`

**¿Ya está hecho?** ✅ Continúa al paso 2

---

### Paso 2: Probar Localmente

1. Abre el archivo `code.html` en tu navegador
2. Prueba todas las funcionalidades:
   - Play del video ✅
   - Vota en Team Girl o Team Boy ✅
   - Llena el formulario RSVP ✅
   - Verifica que lleguen los emails ✅

**¿Todo funciona?** ✅ Continúa al paso 3

---

### Paso 3: Publicar en Internet

**Opción más fácil - Netlify (5 minutos):**

1. Ve a: https://app.netlify.com/drop
2. Arrastra toda la carpeta `GenderReveal`
3. ¡Listo! Te dan un link como: `https://nombre-aleatorio.netlify.app`
4. Puedes cambiar el nombre en: Site settings → Change site name

**Comparte el link con tus invitados:**
- WhatsApp ✅
- Email ✅
- Facebook ✅
- Instagram Stories ✅

---

## 📋 Checklist Pre-Evento

Antes de compartir con tus invitados, verifica:

- [ ] Firebase Database creada y con reglas aplicadas
- [ ] Video `video.mov` está en la carpeta
- [ ] Probaste votar (aparece la notificación)
- [ ] Probaste el formulario RSVP
- [ ] Llegaron los 2 emails (admin + guest)
- [ ] El mapa se ve correctamente
- [ ] El contador regresivo muestra la fecha correcta
- [ ] La página está publicada en internet

---

## 🎨 Personalizar (Opcional)

### Cambiar los nombres de la familia:
Busca en `code.html` y reemplaza:
- "familia" por tu nombre

### Cambiar colores:
Edita las líneas 20-26 de `code.html` con tus colores favoritos

### Agregar más información:
Edita el HTML directamente - ¡es fácil!

---

## 📊 Durante el Evento

### Ver los votos en vivo:
https://console.firebase.google.com/project/gender-reveal-d667e/database

Deja esta página abierta en una tablet o computadora durante el evento para ver los votos llegando en tiempo real! 📊

### Ver confirmaciones:
En la misma página de Firebase, ve la sección `rsvps` para ver quién ha confirmado.

---

## 💡 Tips

1. **Comparte el link con anticipación**: Al menos 2 semanas antes
2. **Recuérdales confirmar**: Manda un mensaje 1 semana antes
3. **Proyecta los votos**: Muestra la página en un TV durante el evento
4. **Guarda los datos**: Exporta los RSVPs desde Firebase como backup

---

## 🆘 ¿Necesitas Ayuda?

### Problemas comunes:

**"No se ven los votos"**
→ Verifica que Firebase Database esté creada

**"No llegan los emails"**
→ Revisa https://dashboard.emailjs.com/admin/logs

**"El video no carga"**
→ Verifica que video.mov esté en la misma carpeta que code.html

**Otros problemas:**
→ Lee `FIREBASE_SETUP.md` para soluciones detalladas

---

## 🎉 ¡Listo!

Tu página está lista para usar. Solo falta:
1. Configurar Firebase (2 minutos)
2. Publicar en Netlify (3 minutos)
3. ¡Compartir con tus invitados!

**¡Disfruta tu Gender Reveal! 👶💙💗**

---

## 📁 Archivos Importantes

- `code.html` - Tu página web (este es el principal)
- `video.mov` - Tu video (debe estar en la misma carpeta)
- `README.md` - Documentación completa
- `FIREBASE_SETUP.md` - Guía de configuración de Firebase
- `QUICK_START.md` - Esta guía (inicio rápido)
