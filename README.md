# LimpiFresh - Proyecto React

Proyecto de e-commerce para productos de limpieza desarrollado con React y Vite.

## 🚀 Despliegue en GitHub Pages

Este proyecto está configurado para desplegarse automáticamente en GitHub Pages.

### Configuración Inicial

1. **Asegúrate de tener el repositorio en GitHub:**
   ```bash
   git remote -v
   ```
   Si no tienes un remoto configurado:
   ```bash
   git remote add origin https://github.com/TU_USUARIO/TU_REPOSITORIO.git
   ```

2. **Verifica que el nombre del repositorio coincida con la configuración:**
   - En `package.json`, el campo `homepage` debe ser: `https://TU_USUARIO.github.io/NOMBRE_REPOSITORIO/`
   - En `vite.config.js`, el campo `base` debe ser: `/NOMBRE_REPOSITORIO`

### Despliegue

Para desplegar tu aplicación en GitHub Pages, ejecuta:

```bash
npm run deploy
```

Este comando:
1. Ejecuta `predeploy` que construye la aplicación (`npm run build`)
2. Ejecuta `deploy` que despliega la carpeta `dist` a la rama `gh-pages` usando `gh-pages`

### Configuración en GitHub

1. Ve a tu repositorio en GitHub
2. Haz clic en **Settings** (Configuración)
3. En el menú lateral, ve a **Pages**
4. En **Source** (Fuente), selecciona:
   - **Branch**: `gh-pages`
   - **Folder**: `/ (root)`
5. Haz clic en **Save**

### Acceso a tu sitio

Tu sitio estará disponible en:
```
https://lattafa.github.io/ProyectoLimpiezaReact/
```

**Repositorio:** [https://github.com/Lattafa/ProyectoLimpiezaReact](https://github.com/Lattafa/ProyectoLimpiezaReact)

**Nota:** Puede tomar unos minutos para que el sitio esté disponible después del primer despliegue.

## 📦 Scripts Disponibles

- `npm run dev` - Inicia el servidor de desarrollo
- `npm run build` - Construye la aplicación para producción
- `npm run preview` - Previsualiza la build de producción
- `npm run deploy` - Despliega a GitHub Pages
- `npm run test` - Ejecuta los tests
- `npm run lint` - Ejecuta el linter

## 🛠️ Tecnologías

- React 19
- Vite
- React Router
- Bootstrap 5
- Axios
