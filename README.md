# Luma Studio

Página bilingüe EN/ES, adaptable al celular, con enlaces de WhatsApp y correo.

## Subir a GitHub
1. Descomprime el ZIP.
2. Crea un repositorio en GitHub, por ejemplo `luma-studio`.
3. Usa Add file → Upload files y sube el contenido de esta carpeta: `public`, `wrangler.jsonc` y `README.md`. No subas el ZIP ni una carpeta adicional que envuelva todo.
4. Guarda los cambios con Commit changes.

## Publicar en Cloudflare Workers desde GitHub
1. En Cloudflare abre Workers & Pages y crea un Worker conectado a GitHub.
2. Selecciona tu repositorio y la rama `main`.
3. Nombre del Worker: `luma-studio` (debe coincidir con `name` en wrangler.jsonc; si eliges otro, cambia ambos).
4. Directorio raíz: la raíz del repositorio.
5. Build command: vacío; esta página no necesita compilación.
6. Deploy command: `npx wrangler@latest deploy`.
7. Publica y abre la URL workers.dev que te entregue Cloudflare.

La ubicación/nombre de algunos controles puede variar en el panel.

## Publicar desde tu computadora (alternativa)
Con Node.js instalado, abre una terminal en esta carpeta:

```sh
npx wrangler@latest login
npx wrangler@latest deploy
```

## Editar
Todo el diseño, CSS y JavaScript vive en `public/index.html`.
Los atributos `data-en` y `data-es` contienen cada traducción.
El formulario abre WhatsApp con un borrador; el visitante debe pulsar Enviar. No guarda solicitudes ni envía correos automáticamente.
Los datos de contacto no se muestran como texto, pero están en el código y los destinos de los botones.
Los proyectos usan representaciones estilizadas, no capturas reales.
Luma Studio sigue siendo un nombre provisional; falta verificar disponibilidad de marca y dominio.
Las fuentes se cargan desde Google Fonts; si no están disponibles, se usa la fuente de respaldo.

## Documentación
https://developers.cloudflare.com/workers/static-assets/get-started/
https://developers.cloudflare.com/workers/ci-cd/builds/configuration/
