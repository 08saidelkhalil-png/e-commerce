# Estado del proyecto — Tienda VitaReva

## Tienda
- Nombre: VitaReva
- Dominio público: www.vitareva.net
- Dominio interno: 3xhcyv-yu.myshopify.com
- Plan: Basic · Moneda: EUR · País: España
- Conexión a datos de la tienda: OK, vía conector Shopify ya autorizado en esta sesión
  (no ha hecho falta login adicional para leer/escribir productos).

## Producto principal detectado
- ID: gid://shopify/Product/11114963861842
- Handle: cepillo-limpiador-de-ranuras-para-ventanas-y-rieles-2-en-1
- Título: Cepillo Limpiador de Ranuras para Ventanas y Rieles 2 en 1
- Precio: 8,90 € (variantes Gris/Verde/Beige) · Pack de 2 uds: 16,90 €
- Stock: 40 uds totales
- 7 imágenes en el catálogo (URLs en Shopify CDN, ver más abajo)
- Descripción: cepillo 2 en 1 (cerdas en cuña + almohadilla de microfibra) para
  limpiar ranuras/rieles de ventanas, puertas correderas, duchas, armarios,
  teclados, rejillas de ventilación. Enfoque: soluciona un problema doméstico
  común sin dañarse las uñas ni rayar aluminio/PVC. Reutilizable/lavable.

### Imágenes del producto (Shopify CDN)
1. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/f07d97b3c43cb20810d1753f6939cf67.jpg
2. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/9dc9451d60546abc263dcf4494f3a000.jpg
3. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/69b5eb404132374752ff006adefecf0a.jpg
4. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/217a35173ac7430759ac5c8d0d2949a2.jpg
5. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/39973dce35d3c1a44ac193da21c1254a.jpg
6. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/a9774dfffdc638f3285cd6e35734b310.jpg
7. https://cdn.shopify.com/s/files/1/1107/5898/6066/files/abdec3782032248af0a6e99f274528af.jpg

Nota técnica: la descarga local de estas imágenes (para inspección/edición IA)
está bloqueada por la política de red de este entorno (cdn.shopify.com
devuelve 403 en este contenedor). No afecta al tema: la tienda las carga
directamente desde Shopify. Sí limita generar variantes editadas de las fotos
reales; se puede compensar generando imágenes nuevas desde texto.

## Entorno técnico
- Node v22.22.2, npm 10.9.7, Shopify CLI 4.7.1 — instalados en este entorno.
- Login de tema por navegador (OAuth) del Shopify CLI falla con 403 en este
  entorno en la nube (bloqueo del propio servicio de autorización de Shopify,
  no de nuestra política de red). Alternativa: usar contraseña de la app
  "Theme Access" (flag --password / SHOPIFY_CLI_THEME_TOKEN), pendiente de que
  el usuario la genere.
- Clave de generación de imágenes (OpenAI) proporcionada por el usuario:
  guardada solo en el entorno de esta sesión para fase 3b (no se sube al repo).

## Fase actual
- Fase 0 (entorno): OK
- Fase 1 (conexión + sondeo): datos de tienda y producto OK. Falta la
  contraseña de Theme Access para poder subir/publicar el tema.
- Fase 2 en adelante: pendiente de confirmación de estilo (mensaje 2) y de la
  contraseña de Theme Access.

## Decisiones de diseño
- Pendiente de propuesta / confirmación del usuario (ver mensaje 2).
