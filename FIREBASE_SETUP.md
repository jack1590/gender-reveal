# Configuración de Firebase - Pasos Finales

## 🔥 Crear la Base de Datos en Firebase

Si aún no has creado la Realtime Database, sigue estos pasos:

### 1. Ve a Firebase Console

https://console.firebase.google.com/project/gender-reveal-d667e

### 2. Crear Realtime Database

1. En el menú lateral, click en **"Build"** → **"Realtime Database"**
2. Click en **"Create Database"**
3. Selecciona ubicación: **"United States (us-central1)"** (recomendado)
4. Modo de seguridad: Selecciona **"Start in test mode"** por ahora
5. Click **"Enable"**

### 3. Aplicar las Reglas de Seguridad

Una vez creada la database:

1. Ve a la pestaña **"Rules"**
2. Reemplaza todo el contenido con esto:

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

3. Click en **"Publish"**

### 4. Inicializar los Votos (Opcional)

Para empezar con contador en 0:

1. En la pestaña **"Data"**
2. Click en el ícono **"+"** junto al nombre de tu base de datos
3. Crea este estructura:

```
votes
  ├─ girl: 0
  └─ boy: 0
```

**Cómo hacerlo:**

- Nombre: `votes`
- Click en "+" para agregar child
  - Nombre: `girl`, Valor: `0`
- Click en "+" para agregar otro child
  - Nombre: `boy`, Valor: `0`

### 5. Verifica la URL de la Database

Tu URL debería ser:

```
https://gender-reveal-d667e-default-rtdb.firebaseio.com
```

Esta URL ya está configurada en tu código HTML.

---

## ✅ Verificación Rápida

Una vez configurado todo, abre `code.html` en tu navegador y:

1. Abre la consola del navegador (F12)
2. Busca el mensaje: `🎉 Gender Reveal Page Loaded Successfully!`
3. Si no ves errores en rojo, ¡todo está funcionando!

---

## 🧪 Prueba las Funcionalidades

### Test 1: Votos

1. Click en "Team Girl" o "Team Boy"
2. Deberías ver una notificación verde
3. Refresca la página - el contador debería mantener el nuevo número
4. Abre la página en otra pestaña - debería mostrar el mismo número

### Test 2: RSVP

1. Completa el formulario
2. Ingresa tu email cuando se te pida
3. Verifica que lleguen 2 emails:
   - Uno a **jcarl.30@gmail.com** (notificación)
   - Uno a tu email (confirmación)

---

## 🔧 Si algo no funciona

### Error: "Firebase is not defined"

- Verifica tu conexión a internet
- Los scripts de Firebase se cargan desde CDN

### Error: "Permission denied"

- Verifica que aplicaste las reglas correctamente
- Asegúrate de que la base de datos esté creada

### Los emails no llegan

- Ve a: https://dashboard.emailjs.com/admin/logs
- Revisa el historial de emails enviados
- Verifica el límite de emails (200/mes en plan gratuito)

---

## 📊 Monitoreo en Tiempo Real

### Ver actividad en vivo:

1. Ve a Firebase Console → Realtime Database
2. Deja la pestaña abierta
3. Cuando alguien vote o confirme asistencia, verás los cambios instantáneamente

---

¡Todo listo! 🎉
