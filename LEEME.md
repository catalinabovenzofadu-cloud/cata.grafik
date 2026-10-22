# Cata.grafik — versión gratuita para publicar

Esta carpeta es una versión estática del catálogo que se puede alojar gratis en GitHub Pages, Netlify o Cloudflare Pages. Conserva los recursos de marca y estilos del proyecto original. Incluye los cuatro productos que estaban publicados en los datos iniciales del proyecto; los dos productos sin precio/nombre confirmados permanecen fuera del catálogo para no inventar información.

## Ver en tu computadora

La forma más simple es publicar la carpeta o ejecutar un servidor local desde esta carpeta:

```bash
python3 -m http.server 8000
```

Abrí `http://localhost:8000`. No abras `index.html` con doble clic porque el navegador puede bloquear la carga del JSON.

## Publicar gratis con GitHub Pages

1. Creá una cuenta gratuita en GitHub y un repositorio nuevo.
2. Subí **todo el contenido de esta carpeta** al nivel raíz del repositorio (index.html, data/, assets/ y este archivo).
3. En el repositorio, abrí **Settings → Pages**.
4. En **Build and deployment**, elegí **Deploy from a branch**, seleccioná `main` y `/ (root)`, y guardá.
5. Esperá la URL que GitHub Pages muestra en esa misma pantalla.

No necesita base de datos, tarjeta, build ni instalar dependencias.

## Actualizar productos, precios o fotos

- Editá `data/products.json` con un editor de texto. Mantené el formato JSON y guardá los precios como números (por ejemplo `5000`, sin `$` ni separadores).
- Para una foto nueva, copiá el archivo a `assets/products/` y actualizá el nombre en `image` y `gallery`.
- Para ocultar un producto, cambiá `"published": true` por `false`.
- Subí los cambios al repositorio de GitHub; la web se actualiza sola al terminar el despliegue.
- El número de WhatsApp está en `assets/catalog.js`, en la constante `WHATSAPP`, en formato internacional solo con números. El valor se tomó de la configuración del proyecto existente.

## Qué pierde esta versión

La versión gratuita estática **no incluye el panel `/admin`**, inicio de sesión, carga de fotos desde la web ni importación de Excel con vista previa. La edición se hace modificando `data/products.json` y subiendo las fotos al repositorio. Tampoco hay carrito ni pagos, igual que en el proyecto original.

## Proyecto original

La carpeta principal del ZIP conserva la aplicación Node.js/SQLite con panel administrativo y actualización por Excel. Sus 34 pruebas automatizadas pasan en Node.js 22.16.0. Para usar ese panel necesitás ejecutar el servidor con Node.js 22.13+ y un hosting que mantenga el disco persistente; muchos hostings gratuitos reinician o borran el almacenamiento, por eso esta versión estática es la alternativa más simple para publicar sin costo.
