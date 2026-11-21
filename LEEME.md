# Sitio de GMTO

La página de GMTO con el apartado de NICO, el video y la descarga del instalador.

- Todos los archivos van sueltos, sin carpetas: `index.html`, el aviso de privacidad, los términos, los estilos, la letra Inter, las imágenes y el video (todo con datos ficticios).
- `render.yaml` le dice a Render cómo publicarla (sitio estático, gratis) y a dónde lleva el botón «Descargar el instalador» (`/descargar`).
- El instalador no va en esta carpeta: pesa unos 125 megabytes y vive en GitHub Releases, que lo sirve por https.

## Publicarla, solo con clics

1. **Arma el instalador 0.9.4.** Doble clic en `instalador\Armar instalador.bat`. Sale `instalador\salida\NICO-instalador-0.9.4.exe`.
2. **Crea el repositorio en GitHub.** En github.com, con la cuenta medtecdeoccidente-prog: botón verde «New».
   Nombre: `gmto-sitio`. Elige **Public**, porque si es privado nadie puede bajar el instalador. Luego «Create repository».
3. **Sube la página.** En el repositorio nuevo: «uploading an existing file». En «choose your files» selecciona todos los archivos de esta carpeta
   y da «Commit changes».
4. **Sube el instalador.** En el repositorio: «Releases», luego «Create a new release».
   - En «Choose a tag» escribe `v0.9.4` y elige «Create new tag».
   - Título: `NICO 0.9.4`.
   - Arrastra `NICO-instalador-0.9.4.exe` al recuadro de archivos y da «Publish release».
5. **Publica en Render.** En dashboard.render.com: «New», luego «Blueprint». Elige `gmto-sitio` y da «Apply».
   - Si no aparece, da «Configure account» y dale a Render acceso a ese repositorio.
   - Queda en una dirección como gmto.onrender.com. Si ese nombre ya está tomado, Render le agrega letras al final.
6. **Actualización automática.** En tu panel de GMTO, «Versiones», publica la 0.9.4 con esta dirección:
   https://github.com/medtecdeoccidente-prog/gmto-sitio/releases/download/v0.9.4/NICO-instalador-0.9.4.exe

## Cada versión nueva

1. Crea otro «release» con su etiqueta (por ejemplo `v0.9.5`) y su instalador.
2. En `render.yaml`, cambia la línea `destination` con la versión nueva.
3. En `index.html`, cambia el texto «Versión 0.9.4».
4. Sube los dos archivos con «Add file», luego «Upload files». Render vuelve a publicar solo.

## Dominio propio

Cuando compres uno (por ejemplo gmto.mx), en Render ve a Settings, luego Custom Domains, y agrégalo. Render te dice qué
registros poner donde lo compraste y pone el https solo.
