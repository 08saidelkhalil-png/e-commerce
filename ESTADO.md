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
  entorno en la nube. **Solución adoptada: no usamos el CLI para nada.**
  Construimos y subimos el tema entero vía la Admin API GraphQL (mutaciones
  `themeCreate` / `themeFilesUpsert`), ya autenticada por el conector Shopify
  de esta sesión. No hace falta contraseña de Theme Access.
- Descarga de cdn.shopify.com bloqueada por política de red de este entorno
  → no afecta: `themeCreate` usa una URL pública (el ZIP de Dawn en GitHub)
  que el propio Shopify descarga en sus servidores, no en el nuestro.
- Publicar el tema (pasar de "no publicado" a "en vivo") está bloqueado para
  esta sesión por seguridad → lo hará el usuario con un clic desde el enlace
  de previsualización cuando esté listo (fase 6).
- Clave de generación de imágenes (OpenAI) proporcionada por el usuario:
  guardada solo en el entorno de esta sesión (no se sube al repo). Para poder
  mejorar las fotos REALES del producto con IA necesito que el usuario las
  adjunte directamente en el chat (la descarga automática desde el CDN de
  Shopify está bloqueada por la política de red de este entorno).

## Tema de trabajo
- ID: gid://shopify/OnlineStoreTheme/207033532754
- Nombre: "VitaReva - Diseno IA"
- Rol: UNPUBLISHED (creado desde Shopify/dawn main.zip)

## Brief de diseño (dado por el usuario)
- Referencias de estilo: getdrevia.com, Bleame, Gruns (estética DTC premium,
  cuidado personal/hogar, fondos claros, tarjetas redondeadas, confianza).
- Estructura obligatoria de la página de producto/landing (de un tablero Miro
  del usuario, "ANATOMIA DE UNA WEB QUE VENDE"), en este orden:
  1. Barra de anuncios (envío gratis 24h / oferta -50% termina hoy)
  2. Logo limpio
  3. Foto limpia de producto (héroe, fondo limpio) + 9. Infografías (cómo
     funciona / antes-después / medidas / uso) — en la misma franja
  4. Título de características (qué es y qué hace)
  5. Emoji benefits
  5b. Barra de confianza: ⭐4.9/5 (2.340 valoraciones) · Envío 24h · Garantía
      30d · +10.000 vendidos
  6. Oferta con precio tachado y % de descuento
  7. Añadir al carrito
  8. Reseñas cortas justo bajo el carrito
  10. Acordeón (envío/garantía, cómo se usa, qué pasa si no funciona,
      materiales/medidas)
  11. Descripción-transformación (le habla AL CLIENTE, no al producto)
  12. Garantía + prueba social (30 días, devolución gratis, pago seguro +
      fotos reales de clientes)
  13. Reseñas finales largas con fotos, para indecisos
  Barra "Añadir al carrito" pegajosa (sticky) al final
  Regla de oro: cada bloque quita un miedo o responde una pregunta. Prueba
  arriba → deseo en medio → confianza abajo → cierre.
- Usar las 7 fotos reales del producto, mejoradas con IA (pendiente de que el
  usuario las adjunte en el chat).

## Fase actual
- Fase 0 (entorno): OK
- Fase 1 (conexión + sondeo): OK
- Fase 2 (proyecto/tema base): tema creado y procesado en Shopify
- Fase 3 (brief): recibido del usuario directamente — ver "Brief de diseño"
- Fase 3b (fotos IA): pendiente de que el usuario adjunte las fotos
- Fase 4 (secciones mt-*): 12 secciones construidas y subidas al tema
  (announcement-bar, hero-gallery, feature-title, emoji-benefits, trust-bar,
  offer-buybox, mini-reviews, faq-accordion, transformation, guarantee-social,
  reviews-long, sticky-atc)
- Fase 5 (plantilla de producto): `templates/product.json` del tema
  sobrescrito con las 12 secciones en el orden del brief (dentro del tema NO
  publicado; el tema en vivo no se toca). Pendiente: header/footer/legales/
  colores globales (carrito, búsqueda).
- Enlace de previsualización (tema no publicado, no afecta a la tienda en
  vivo):
  https://3xhcyv-yu.myshopify.com/products/cepillo-limpiador-de-ranuras-para-ventanas-y-rieles-2-en-1?preview_theme_id=207033532754
- Fase 6 (publicación): pendiente de revisión del usuario y de su clic de
  "Publicar" (esta sesión tiene bloqueada la mutación themePublish por
  seguridad).
