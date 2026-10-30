# Las Moharras · Código original para GitHub y Vercel

Este paquete conserva los archivos de la última versión aprobada: fotografías reales, amenities del loft actualizados y ninguna escena generada con IA. No se rediseñó ni se reescribió la web. No se creó un repositorio remoto ni se desplegó un sitio.

## La forma más simple de usarlo

1. Descomprimí el ZIP.
2. Entrá a la carpeta `las-moharras-github-vercel`.
3. Creá en GitHub un repositorio para el proyecto, por ejemplo `las-moharras`.
4. Subí **el contenido de esta carpeta** con la opción de cargar archivos del repositorio. Incluí las carpetas `dist`, `referencia`, `documentacion` y los archivos de la raíz. No subas solamente el ZIP.
5. Comprobá que `vercel.json` esté en la raíz del repositorio, al mismo nivel que `README.md` y `dist`.
6. En Vercel, creá un proyecto e importá ese repositorio de GitHub. Vercel aloja la web; GitHub conserva su código.
7. Revisá las opciones de la tabla y elegí desplegar cuando quieras que el sitio quede alojado. Esta entrega no lo publica automáticamente.

| Configuración | Valor |
| --- | --- |
| Root Directory | Raíz del repositorio: `.` |
| Framework Preset | `Other` |
| Build Command | Vacío / omitir la compilación |
| Install Command | Vacío / omitir instalación |
| Output Directory | `dist` |
| Variables de entorno | Ninguna |

`vercel.json` ya declara framework, comandos y carpeta de salida. No selecciones `dist` como Root Directory además de usarlo como Output Directory. Si subiste una carpeta contenedora adicional al repositorio, Root Directory deberá apuntar a esa carpeta, donde está `vercel.json`.

No hace falta un prompt para importar este código directamente en Vercel. `PROMPT_PARA_ASISTENTE.txt` sirve si vas a usar v0, Copilot u otro asistente: entregale también los archivos reales o acceso al repositorio. El prompt solo no reproduce las fotos ni el código.

## Archivos principales

- `dist/index.html`: todas las secciones y textos estáticos.
- `dist/styles.css`: diseño original y adaptación a distintos tamaños de pantalla.
- `dist/contenido.js`: datos comerciales, amenities y fotografías editables.
- `dist/app.js`: galería, menú, propuestas de estadía y formulario de WhatsApp.
- `dist/assets/`: todas las fotografías y el favicon originales de esta versión.
- `dist/editar.html`: editor que descarga una nueva configuración; no modifica el servidor ni el repositorio por sí solo.
- `dist/robots.txt`: configuración de indexación del prototipo.
- `referencia/Las_Moharras_Prototipo.html`: versión independiente aprobada, con imágenes integradas, para comparar visualmente. No es la entrada del despliegue.
- `ORIGINALES_SHA256.json`: huellas de los archivos originales de `dist` y la referencia, para verificar que no cambiaron.
- `documentacion/`: notas previas del proyecto y procedencia del material.
- `crear-prototipo.py`: herramienta opcional para generar otro HTML independiente a partir de `dist`; no se ejecuta en Vercel.

Vercel sirve únicamente `dist`. La documentación, la referencia y el prompt quedan fuera de la carpeta publicada.

## Ver antes de subir

Abrí `dist/index.html` en tu navegador o abrí el HTML de `referencia`. Para servirlo localmente, si tenés Python instalado, ejecutá desde la raíz:

```sh
python -m http.server 8000 --directory dist
```

Después abrí `http://localhost:8000`. No se necesitan Node, npm ni una instalación de dependencias para usar la web.

## Qué comprobar al desplegar

- Portada con la foto diurna real, colores, tipografías y espaciados intactos.
- Menú y diseño en celular y computadora.
- 15 fotografías reales ampliables en la galería y foto real del museo en su sección.
- Dos cabañas de hasta 4 personas cada una y loft de hasta 12; equipamiento del loft equivalente y horno a gas adicional.
- Propuestas de una, dos y tres noches.
- Validación de fechas y generación de consulta por WhatsApp al número `5492477671982`.
- No se simulan disponibilidad, pagos ni confirmaciones de reserva.

## Estado conservado del prototipo

Se mantiene `noindex,nofollow` y el bloqueo de rastreo de `robots.txt`, tal como estaba. Esto no hace privado al sitio: si necesitás acceso restringido, configurá la protección de acceso en el alojamiento. Habilitar indexación comercial es una decisión posterior y no es necesario para que la profesora lo recorra.

No se inventaron coordenadas, dirección de calle, dominio, política de cancelación ni redes sociales faltantes. Las condiciones específicas de cancelación siguen pendientes de confirmación. La web mantiene enlaces reales a WhatsApp y redes; no envía mensajes automáticamente.

## Documentación técnica consultada

- Vercel: https://vercel.com/docs/builds/configure-a-build
- Vercel: https://vercel.com/docs/project-configuration/vercel-json
- GitHub: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

Configuración preparada el 30 de octubre de 2026. Se verificaron los archivos localmente; no se probó un despliegue real en Vercel.
