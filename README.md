# 📚 Planificador PAU 2026 – Asturias

Planificador interactivo de estudio para la PAU 2026, Ciencias Sociales, Asturias.

## 🚀 Acceso rápido

> **URL:** `https://TU_USUARIO.github.io/pau2026/planificador_pau2026.html`

---

## 🔧 Instalación en GitHub Pages

### Paso 1 – Crear repositorio en GitHub
1. Ve a [github.com](https://github.com) e inicia sesión (crea cuenta gratis si no tienes)
2. Pulsa el botón verde **New** (nuevo repositorio)
3. Nombre: `pau2026` · Visibilidad: **Public** · Pulsa **Create repository**

### Paso 2 – Subir los archivos a GitHub
Sube **estos archivos** (y solo estos — NO subas `firebase-config.js`):

| Archivo | Subir a GitHub |
|---|---|
| `planificador_pau2026.html` | ✅ Sí |
| `manifest.json` | ✅ Sí |
| `sw.js` | ✅ Sí |
| `icon-192.png` | ✅ Sí |
| `icon-512.png` | ✅ Sí |
| `.nojekyll` | ✅ Sí |
| `.gitignore` | ✅ Sí |
| `firebase-config.js` | ❌ NO — contiene tus claves privadas |

En el repositorio pulsa **Add file → Upload files**, selecciona los archivos correctos y pulsa **Commit changes**.

### Paso 3 – Activar GitHub Pages
1. Ve a **Settings** (pestaña del repositorio)
2. En el menú izquierdo: **Pages**
3. Source: **Deploy from a branch** → Branch: **main** · Folder: **/ (root)** → **Save**
4. Espera ~2 minutos. Tu URL será: `https://TU_USUARIO.github.io/pau2026/planificador_pau2026.html`

---

## 🔥 Configurar Firebase (sync PC ↔ móvil)

### Paso 1 – Crear proyecto Firebase
1. Ve a [console.firebase.google.com](https://console.firebase.google.com)
2. **Add project** → nombre: `pau2026` → desactiva Google Analytics → **Create project**

### Paso 2 – Crear Realtime Database
1. Menú izquierdo: **Build → Realtime Database** → **Create Database**
2. Región: **Europe West (Belgium)**
3. Modo: **Start in test mode** → **Enable**

### Paso 3 – Obtener tu configuración
1. ⚙️ **Project settings** → pestaña **General** → scroll abajo → **Your apps** → icono `</>`
2. App nickname: `pau2026-web` → **Register app**
3. Copia el objeto `firebaseConfig` completo

### Paso 4 – Rellenar firebase-config.js (solo en tu PC/móvil)
Abre el archivo `firebase-config.js` con cualquier editor de texto y sustituye
los valores `"PEGA_AQUI_TU_..."` por los reales de tu proyecto Firebase.

> ⚠️ **NUNCA subas `firebase-config.js` a GitHub.** El `.gitignore` ya lo excluye automáticamente si usas Git.

### Paso 5 – Acceder desde cada dispositivo
- En tu **PC**: abre `planificador_pau2026.html` directamente desde la carpeta local
  (necesitas `firebase-config.js` en la misma carpeta).
- En tu **móvil**: usa la URL de GitHub Pages (el móvil no tiene acceso al archivo local,
  por eso usamos GitHub Pages como servidor).

> Para que el móvil también use Firebase, el `firebase-config.js` debe estar accesible.
> **Opción segura**: usa las reglas de Firebase para restringir el acceso solo a tu IP o
> añade autenticación (ver más abajo).

### Alternativa: Variables de entorno con GitHub Actions (avanzado)
Si quieres despliegue automático con claves seguras, puedes usar GitHub Actions + Secrets
para inyectar la config en el HTML durante el build. Pregúntale a tu asistente de IA.

---

## 🔒 Seguridad Firebase (recomendado)

En la consola Firebase → **Realtime Database → Rules**, cambia las reglas a:

```json
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null"
  }
}
```

Luego activa **Authentication → Email/Password** y crea tu usuario.

---

## 📱 Instalar como app en el móvil

1. Abre la URL de GitHub Pages en **Chrome para Android** o **Safari en iPhone**
2. Chrome: menú ⋮ → **Añadir a pantalla de inicio**
3. Safari: botón compartir → **Añadir a pantalla de inicio**
4. Se instala como app nativa con icono propio

---

## Archivos del proyecto

| Archivo | Descripción | Subir a GitHub |
|---|---|---|
| `planificador_pau2026.html` | App principal | ✅ |
| `manifest.json` | Config PWA | ✅ |
| `sw.js` | Service Worker offline | ✅ |
| `icon-192.png` / `icon-512.png` | Iconos app | ✅ |
| `.nojekyll` | GitHub Pages | ✅ |
| `.gitignore` | Excluye claves | ✅ |
| `firebase-config.js` | 🔑 Tus claves Firebase | ❌ Solo en tu PC/móvil |
