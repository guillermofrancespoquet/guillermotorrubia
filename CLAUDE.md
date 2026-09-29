# NutriLogos — contexto de trabajo

Este repo contiene planificaciones nutricionales de clientes de NutriLogos, entregadas como HTML autocontenido y publicadas en GitHub Pages. Este archivo se carga automáticamente al abrir este proyecto: contiene la forma de trabajar de Guille (nutricionista, dueño del proyecto) y los criterios clínicos que rigen cada plan.

**Importante — un repo por cliente:** este repositorio corresponde a un único cliente. No mezcles datos, contexto ni referencias de otros clientes aquí, aunque aparezcan en otras conversaciones o repos. Si necesitas trabajar con otro cliente, hazlo en su propio repo/chat.

## Plantilla visual obligatoria

El archivo `INSTRUCCIONES_PLANTILLA_NUTRILOGOS_v5.0.txt` en este mismo repo es el estándar de estructura HTML/CSS/JS para todos los clientes NutriLogos. Léelo siempre antes de crear o modificar el HTML de un plan. Resumen de reglas no negociables:

- HTML autocontenido: vanilla JS, sin dependencias externas, un único bloque `<script>` al final del `<body>`.
- CSS exacto de la plantilla — no modificar clases ni estructura visual.
- El archivo publicado en GitHub Pages debe llamarse `index.html` (requisito de GitHub Pages para servir en la raíz).
- Estructura de 11 bloques en orden fijo (ver plantilla, Sección 1): cabecera → descripción cliente → objetivo → perfil → tabla resumen semanal → menú por días (tabs) → lista de compra/guía de elección → suplementación (si aplica) → recetas (si aplica) → sección personalizada (si aplica) → próxima revisión (omitir si el cliente no la usa, como es el caso aquí).
- NO usar `<hr>` entre secciones ni `border-top`/`padding-top` en wrappers de sección — solo `margin-top:2.5rem`.
- Portanciones en formato Plato de Harvard (1/4, 1/2, 3/4 de plato) y unidades naturales en castellano (vaso, taza, puñado, cucharadas) — nunca gramos salvo que el caso lo exija clínicamente, y nunca la palabra inglesa "side".
- Antes de entregar cualquier HTML: extraer el bloque `<script>` a un `.js` temporal y validar con `node --check archivo.js` (los saltos de línea literales dentro de strings JS rompen la sintaxis — usar siempre `\n`).

## Forma de trabajar con Guille

- Secuencia: primero consolidar todos los datos del cliente en el chat → acordar criterios clínicos → confirmar estructura completa → generar el HTML → iterar visualmente. Nunca generar HTML antes de tener datos y criterios cerrados.
- Comunicación: concisa y directa. Guille da instrucciones categóricas y espera cambios quirúrgicos y localizados, no reescrituras completas del documento.
- Si Guille dice "no hagas nada" o "gracias", parar inmediatamente.
- No cambiar convenciones ya establecidas (nombres de archivo, estructura, etc.) por iniciativa propia mientras se depura un problema — preguntar primero.
- Revisión clínica siempre antes que cambios de HTML: Guille aprueba la interpretación clínica antes de tocar el documento.
- Nunca mezclar datos de distintos clientes entre archivos (de ahí que cada cliente tenga su propio repo).
- Tono en el documento del cliente: siempre en segunda persona singular (tú/te), nunca en tercera persona.
- Nomenclatura de secciones: "Datos bioimpedancia" y "Control de peso (objetivo)" — nunca mencionar marcas de dispositivos (p. ej. InBody).
- Sistema de badges: C = Comida (mediodía); Ce = Cena (noche); A = Almuerzo/media mañana (opcional, quinta comida); los banners de entrenamiento son opcionales, a discreción de Guille.

## Criterios clínicos base

- Filosofía: 100% plant-based (WFPB) como ideal basado en evidencia, con excepciones individualizadas según contexto y adherencia del cliente — la adherencia sostenida en el tiempo pesa más que la perfección teórica. Siempre comunicar con honestidad que lo plant-based 100% es lo clínicamente ideal, pero adaptando el porcentaje de excepción al contexto real de cada persona (sin cifra fija).
- Proteína: ~1 g/kg para adultos sanos sedentarios; ~1.6 g/kg para deportistas o en déficit calórico; en deportistas de resistencia, Guille puede aplicar objetivos más bajos (p. ej. 1.2 g/kg) según su criterio clínico. La proteína no se plantea como objetivo explícito en g/kg de cara al cliente — se presenta como resultado natural de una buena selección de alimentos.
- Periodización de carbohidratos alrededor de sesiones intensas es la estrategia central en clientes deportistas; el foco de rendimiento es el CH, no la proteína.
- Plato de Harvard preferido sobre gramos/básculas para la mayoría de clientes; gramos solo cuando es clínicamente necesario.
- Pre-competición: evitar avena (la fibra soluble ralentiza el vaciado gástrico); preferir CH rápidos (dátiles, pasas, bebidas isotónicas).
- Bioimpedancia tratada como secundaria/orientativa cuando hay datos ISAK o DEXA disponibles.
- Cena libre del sábado es una herramienta de adherencia no negociable en la mayoría de planes.
- Legumbres mínimo 4x/semana como objetivo base; priorizar conserva precocida (botes de 400g, escurridos y aclarados) para recetas prácticas.
- Jerarquía de proteína animal cuando se incluye: pescado → huevo → carne blanca → carne roja → procesada.
- Jerarquía de lácteos cuando se incluyen: yogur de soja > queso fresco batido/yogur griego ligero > yogur griego normal o lácteos enteros (evitar estos últimos).
- Huevo prácticamente eliminado de la planificación base salvo insistencia del cliente (máx. 1-2 días/semana, nunca protagonista).

## Notas técnicas HTML/PDF

- `weasyprint` es el motor fiable para PDF (no `wkhtmltopdf`); usar `'Liberation Sans', Arial, sans-serif` como stack de fuente en PDF (no `system-ui`).
- Los emojis dan problemas de renderizado en PDF/weasyprint — sustituir por elementos dibujados en CSS si el documento va a exportarse a PDF.
- Para ediciones grandes de HTML ya existente: usar reemplazo de texto dirigido (`str_replace`), reservar la reescritura completa solo cuando sea imprescindible.
- Imágenes en base64 embebidas directamente en el HTML para portabilidad entre visor de chat, navegador local y GitHub Pages.
- `localStorage` para el tachado de la lista de compra es intencional (se resetea al cerrar la página = reinicio semanal).
- Botones de PDF usan rutas relativas de GitHub Pages (`./assets/nombre.pdf`).

## Al generar o modificar el plan de este cliente

1. Confirmar con Guille cualquier dato nuevo o cambio de criterio antes de tocar el HTML.
2. Seguir al pie de la letra la plantilla v5.0 (estructura, CSS, JS).
3. Validar el JS con `node --check` antes de dar por terminado cualquier cambio.
4. Comprobar que no hay duplicación de contenido ni de IDs tras mover o reestructurar secciones.
5. El archivo final para publicar en GitHub Pages debe llamarse `index.html`.
