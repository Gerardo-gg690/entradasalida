# TimeCore — GitHub Pages + Supabase

Esta versión sí puede abrirse desde varios teléfonos y compartir los mismos empleados y marcaciones.

## 1. Crear Supabase
1. Crea una cuenta/proyecto en Supabase.
2. En SQL Editor pega TODO el contenido de `supabase.sql` y pulsa Run.
3. En el proyecto abre Connect o Settings > API Keys.
4. Copia el **Project URL** y la **Publishable key**. NO uses Secret key ni service_role.
5. Abre `config.js` y pega ambos valores.

## 2. Subir a GitHub
Sube a la raíz del repositorio: `index.html`, `style.css`, `script.js`, `config.js`.
Puedes dejar `supabase.sql` y este README también.

En GitHub: Settings > Pages > Deploy from a branch > main / root > Save.
Luego abre el enlace de GitHub Pages desde cualquier teléfono.

## 3. Primera vez
Pulsa “Panel de la jefa”. Si todavía no existe cuenta, el sistema permitirá crear el usuario y contraseña de administradora. Después agrega empleados y PIN personales.

## Seguridad
- Los PIN y contraseña se convierten en hashes dentro de PostgreSQL con pgcrypto.
- Las tablas tienen RLS y no se da acceso directo a `anon`; el navegador usa funciones RPC limitadas.
- `config.js` lleva una Publishable key pública, que puede estar en GitHub Pages.
- NUNCA pegues una Secret key o service_role en GitHub.
