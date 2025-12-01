# Guía de Despliegue en GitHub Pages

## 📋 Requisitos Previos

1. Tener una cuenta de GitHub
2. Tener el proyecto subido a un repositorio de GitHub
3. Tener Node.js y npm instalados

## 🔧 Configuración del Proyecto

Tu proyecto ya está configurado con:
- ✅ `gh-pages` instalado como dependencia
- ✅ Scripts de despliegue configurados en `package.json`
- ✅ Base path configurado en `vite.config.js`

### Verificar Configuración

**1. Verifica el `package.json`:**
```json
{
  "homepage": "https://TU_USUARIO.github.io/NOMBRE_REPOSITORIO/",
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  }
}
```

**2. Verifica el `vite.config.js`:**
```js
export default defineConfig({
  base: '/NOMBRE_REPOSITORIO',  // Debe coincidir con el nombre del repo
  // ...
})
```

**Importante:** El nombre del repositorio en GitHub debe coincidir con:
- El path en `homepage` (después de `.github.io/`)
- El valor de `base` en `vite.config.js`

## 🚀 Pasos para Desplegar

### Paso 1: Preparar el Repositorio

```bash
# Asegúrate de estar en la rama main/master
git checkout main

# Asegúrate de tener todos los cambios guardados
git add .
git commit -m "Preparar para despliegue"
git push origin main
```

### Paso 2: Instalar Dependencias (si no lo has hecho)

```bash
npm install
```

### Paso 3: Desplegar

```bash
npm run deploy
```

Este comando:
1. Ejecuta `npm run build` para crear la versión de producción
2. Crea/actualiza la rama `gh-pages` con el contenido de `dist`
3. Sube los cambios a GitHub

### Paso 4: Configurar GitHub Pages

1. Ve a tu repositorio en GitHub: `https://github.com/TU_USUARIO/TU_REPOSITORIO`
2. Haz clic en **Settings** (Configuración)
3. En el menú lateral izquierdo, busca y haz clic en **Pages**
4. En la sección **Source**:
   - Selecciona **Branch**: `gh-pages`
   - Selecciona **Folder**: `/ (root)`
5. Haz clic en **Save**

### Paso 5: Esperar y Verificar

- GitHub puede tardar 1-5 minutos en publicar tu sitio
- Recibirás una notificación cuando esté listo
- Tu sitio estará disponible en: `https://TU_USUARIO.github.io/NOMBRE_REPOSITORIO/`

## 🔄 Actualizar el Sitio

Cada vez que quieras actualizar tu sitio:

```bash
# 1. Haz tus cambios y commitea
git add .
git commit -m "Descripción de los cambios"
git push origin main

# 2. Despliega
npm run deploy
```

## ⚠️ Solución de Problemas

### Error: "gh-pages command not found"
```bash
npm install --save-dev gh-pages
```

### Error: "Repository not found"
- Verifica que el repositorio existe en GitHub
- Verifica que tienes permisos de escritura
- Verifica la URL del remoto: `git remote -v`

### El sitio no carga o muestra 404
- Verifica que el nombre del repositorio en GitHub coincide con el `base` en `vite.config.js`
- Verifica que la rama `gh-pages` existe: `git branch -a`
- Espera unos minutos más, GitHub puede tardar

### Las rutas no funcionan (404 en rutas internas)
- Asegúrate de que `base` en `vite.config.js` esté configurado correctamente
- Si usas React Router, verifica que esté configurado con el `basename` correcto

### El sitio muestra contenido en blanco
- Abre la consola del navegador (F12) y revisa errores
- Verifica que todos los assets estén siendo cargados correctamente
- Asegúrate de que el build se completó sin errores

## 📝 Notas Importantes

1. **La rama `gh-pages` se crea automáticamente** - No necesitas crearla manualmente
2. **No edites directamente la rama `gh-pages`** - Siempre usa `npm run deploy`
3. **El build se genera en la carpeta `dist`** - Esta carpeta está en `.gitignore` y no debe subirse a `main`
4. **Cada despliegue sobrescribe el anterior** - No hay historial en `gh-pages`

## 🔗 Enlaces Útiles

- [Documentación de GitHub Pages](https://docs.github.com/en/pages)
- [Documentación de gh-pages](https://github.com/tschaub/gh-pages)
- [Documentación de Vite](https://vitejs.dev/)

