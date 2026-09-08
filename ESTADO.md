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

## Corrección importante (tras feedback del usuario)
La primera versión (fase 4/5 inicial) era solo "inspirada" en drevia/bleame y
el usuario la rechazó por no parecerse a la referencia real. Se rehizo para
clonar la anatomía real de getdrevia.com (capturas de pantalla del usuario)
bloque a bloque, cambiando solo color/copys al tono del producto:
- Header de Dawn: logo centrado (serif cursiva verde), menú en cajón,
  buscador y carrito a la derecha (`sections/header-group.json`).
- Paleta única verde oscuro (#1F4D34) + blanco + negro (sin la mezcla
  crema/salvia/rojo de la v1) vía `config/settings_data.json` y
  `assets/mt-theme.css`.
- Galería: carrusel con flechas/puntos + tira de miniaturas (no grid fijo).
- Rating + título + checklist de checks verdes (no emoji sueltos).
- Compra: tarjetas de variante tipo "bundle" (radio, precio real por
  variante, badge en el pack), trío de iconos de confianza, botón grande con
  flecha, texto de devolución, iconos de métodos de pago, barra de urgencia
  con % editable.
- Reseñas cortas en carrusel deslizable (no lista apilada).
- Acordeón con icono por pregunta.
- Bloques narrativos reutilizables (`mt-transformation`, usado 3 veces:
  story1/story2/story3) para imitar los titulares tipo "problema/causa raíz"
  de Drevia.
- Cita destacada en carrusel con icono de comillas.
- Comparador antes/después arrastrable (`mt-before-after`) — usa fotos reales
  del producto como marcador de posición hasta que haya fotos antes/después
  reales; no se han inventado afirmaciones de limpieza.
- No se han inventado precios tachados ni "% vendido" falsos: el precio
  tachado solo aparece si existe compare_at_price real en la variante: la
  barra de urgencia es un ajuste editable, no un dato inventado como hecho.

## Segunda corrección (layout de 2 columnas + extras)
El usuario señaló que faltaban piezas del layout real de Drevia en escritorio:
- Fotos a la izquierda y TODO lo demás (título, checklist, oferta, compra,
  reseñas, acordeón) en una columna a la derecha, no apilado a ancho completo.
  Se fusionó en una sola sección `mt-product-main.liquid` con CSS grid de 2
  columnas (se apila en móvil).
- Cuenta atrás editable (horas configurables, persistida por visitante en
  localStorage para que no cambie en cada recarga).
- Botón "Comprar ahora" nativo de Shopify (`{{ form | payment_button }}`)
  junto a "Añadir al carrito", dentro de un `{% form 'product', product %}`
  real (antes solo tenía fetch a mano).
- Barra de anuncios: se repite el bloque de mensajes 10 veces (antes 2) para
  que el marquee sea un bucle continuo sin huecos ni parón visible.
- Acordeón alineado a las 4 categorías reales de Drevia: "Modo de uso",
  "Envío y entrega", "Sobre el producto", "Atención al cliente".

## Tercera corrección (franja fija arriba, cómo se usa, comentarios finales)
- Franja fija (no animada) bajo el marquee con cuenta atrás + "Envío gratis
  24-48h", siempre visible sin necesidad de hacer scroll. Comparte la misma
  cuenta atrás (localStorage `mt_offer_countdown`) que la de la caja de
  compra, para que ambas muestren siempre el mismo tiempo.
- Nueva sección "Así de fácil se usa" justo después de antes/después, con
  el contenido EXACTO (textos y fotos) que ya tenías en el tema publicado
  actualmente (Helio - Réplica Drevia, Horizon), leído directamente de su
  `templates/product.json` con la Admin API.
- Nueva sección de comentarios/reseñas de clientes en cuadrícula al final
  de toda la página.
- Nuevo orden: anuncios → ficha (galería+compra) → narrativa 1 → narrativa 2
  → cita destacada → antes/después → cómo se usa → narrativa de cierre →
  comentarios finales.

## Cuarta corrección (barra de anuncios por encima del logo)
La barra de anuncios (marquee + franja fija de cuenta atrás/envío) se movió
de la plantilla de producto al `sections/header-group.json` del tema, antes
de "header". Así queda por encima del logo VitaReva en TODAS las páginas
(no solo la de producto), tal como pidió el usuario señalando la captura.

## Quinta corrección (solo la franja fija va arriba del logo, el marquee vuelve abajo)
Separado en dos secciones: `mt-top-strip` (solo cuenta atrás + envío gratis,
fija, sin animación) va ANTES del logo; `mt-announcement-bar` (la barra que
se mueve) vuelve a ir DESPUÉS del logo, dentro del mismo header-group.
Ambas comparten la cuenta atrás vía localStorage `mt_offer_countdown`.

## Sexta corrección (fotos reales en antes/después)
El comparador antes/después usaba de momento dos fotos de producto como
marcador de posición. Ahora usa las fotos REALES de "ranura sucia" / "ranura
limpia" que ya existían en el tema publicado (Helio - Réplica Drevia),
mismas referencias `shopify://shop_images/...` copiadas de ahí.

## ⚠️ Cambio importante: el tema pasó a estar PUBLICADO
El usuario publicó "VitaReva - Diseno IA" (gid://shopify/OnlineStoreTheme/207033532754,
role MAIN) desde el editor de Shopify. A partir de ahí, esta sesión ya NO
puede escribir directamente sobre ese tema (bloqueado por seguridad:
"Theme file writes against the live storefront are blocked"). Se duplicó
como nuevo tema NO publicado para seguir trabajando:
- ID: gid://shopify/OnlineStoreTheme/207046803794
- Nombre: "VitaReva - Diseno IA (borrador)"
- Enlace de previsualización:
  https://3xhcyv-yu.myshopify.com/products/cepillo-limpiador-de-ranuras-para-ventanas-y-rieles-2-en-1?preview_theme_id=207046803794
Todos los cambios a partir de ahora se hacen en este borrador. El usuario
debe revisarlo y publicarlo él mismo cuando esté conforme (Shopify admin →
Temas → ⋯ → Publicar), igual que hizo con el anterior.

## Séptima corrección (portada/home)
La portada por defecto de Dawn ("Browse our latest products" con
ilustración genérica) se sustituyó por `mt-home-hero`: imagen a pantalla
completa con la foto REAL del producto (la misma que ya se usaba de fondo
en la portada del otro tema publicado), tarjeta con titular + subtítulo +
botón "Comprar ahora" que lleva a la ficha de producto. Aplicado en el tema
borrador (207046803794), no en el que está en vivo.

## Fase actual
- Fase 0 (entorno): OK
- Fase 1 (conexión + sondeo): OK
- Fase 2 (proyecto/tema base): tema creado y procesado en Shopify
- Fase 3 (brief): recibido del usuario, corregido tras su feedback — ver
  "Corrección importante" arriba
- Fase 3b (fotos IA): pendiente de que el usuario adjunte las fotos
- Fase 4-5 (secciones + plantilla): reconstruidas para clonar la anatomía de
  Drevia; `templates/product.json` del tema sobrescrito (tema NO publicado,
  el tema en vivo no se toca). Pendiente: footer y páginas legales.
- Enlace de previsualización (tema no publicado, no afecta a la tienda en
  vivo):
  https://3xhcyv-yu.myshopify.com/products/cepillo-limpiador-de-ranuras-para-ventanas-y-rieles-2-en-1?preview_theme_id=207033532754
- Fase 6 (publicación): pendiente de revisión del usuario y de su clic de
  "Publicar" (esta sesión tiene bloqueada la mutación themePublish por
  seguridad).
