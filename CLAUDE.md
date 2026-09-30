# NutriLogos — pautas de trabajo y alimentación (genérico)

Este archivo es común a todos los clientes de NutriLogos. Recoge cómo trabaja Guille (nutricionista, dueño del proyecto), la plantilla visual y los criterios de alimentación de partida. Lo específico de cada cliente (datos, objetivos, decisiones, ajustes) se organiza aparte, en los archivos propios de su repo, nunca aquí.

Los criterios clínicos y de estructura de este archivo son **orientativos, no inamovibles**: sirven de punto de partida y de contexto. El criterio de Guille prevalece en cada caso y puede alejarse de ellos según la persona y su contexto.

## Ámbito y privacidad

- Cada repo corresponde a un único cliente. No mezcles datos, contexto ni referencias de otros clientes, aunque aparezcan en otras conversaciones o repos. Si hay que trabajar con otro cliente, se hace en su propio repo/chat.
- Este archivo no debe contener datos de salud ni identificativos de ningún cliente (los repos servidos con GitHub Pages pueden ser públicos). Esos datos viven solo en el plan del cliente.

## Plantilla visual obligatoria

El archivo `INSTRUCCIONES_PLANTILLA_NUTRILOGOS_v5.0.txt` (en este repo) es el estándar de estructura HTML/CSS/JS para todos los clientes. Léelo siempre antes de crear o modificar el HTML de un plan. Reglas no negociables:

- HTML autocontenido: vanilla JS, sin dependencias externas, un único bloque `<script>` al final del `<body>`.
- CSS exacto de la plantilla: no modificar clases ni estructura visual.
- El archivo publicado en GitHub Pages se llama `index.html`.
- Estructura de 11 bloques en orden fijo (plantilla, Sección 1): cabecera → descripción del cliente → objetivo → perfil → tabla resumen semanal → menú por días (tabs) → lista de compra → suplementación (si aplica) → recetas (si aplica) → sección personalizada (si aplica) → próxima revisión (con fecha real o "Por definir").
- NO usar `<hr>` entre secciones ni `border-top`/`padding-top` en wrappers de sección: solo `margin-top:2.5rem`.
- Porciones en formato Plato de Harvard (1/4, 1/2, 3/4 de plato) y unidades naturales en castellano (vaso, taza, puñado, cucharadas). Nunca gramos salvo que el caso lo exija clínicamente, y nunca la palabra inglesa "side".
- Antes de entregar cualquier HTML: extraer el bloque `<script>` a un `.js` temporal y validar con `node --check archivo.js` (los saltos de línea literales dentro de strings JS rompen la sintaxis: usa siempre `\n`).

## Forma de trabajar con Guille

- Secuencia: consolidar todos los datos del cliente → acordar criterios clínicos → confirmar la estructura completa → generar el HTML → iterar visualmente. Nunca generar HTML antes de tener datos y criterios cerrados.
- Comunicación: concisa y directa. Guille da instrucciones categóricas y espera cambios quirúrgicos y localizados, no reescrituras completas.
- Si Guille dice "no hagas nada" o "gracias", parar inmediatamente.
- No cambiar convenciones ya establecidas (nombres de archivo, estructura, etc.) por iniciativa propia mientras se depura un problema: preguntar primero.
- Revisión clínica antes que cambios de HTML: Guille aprueba la interpretación clínica antes de tocar el documento.
- Tono en el documento del cliente: siempre segunda persona singular (tú/te), nunca tercera persona.
- Nomenclatura: "Datos bioimpedancia", sin marcas de dispositivos (p. ej. InBody). El bloque "Control de peso (objetivo)" ya no existe en la plantilla v5.0.
- Badges: C = Comida (mediodía); Ce = Cena (noche); A = Almuerzo/media mañana (opcional, quinta comida). Los banners de entrenamiento son opcionales, a discreción de Guille.

## Criterios clínicos base (orientativos)

- Filosofía: 100% plant-based (WFPB) como ideal basado en evidencia, con excepciones individualizadas según contexto y adherencia (sin cifra fija; orientativamente hasta ~10%). La adherencia sostenida pesa más que la perfección teórica. Comunica siempre con honestidad que lo plant-based 100% es lo clínicamente ideal, adaptando el porcentaje de excepción al contexto real de la persona.
- Fuera del sistema: patologías diagnosticadas y grupos de edad de riesgo (derivar a especialista).
- Proteína: ~1 g/kg en adultos sanos sedentarios; ~1.6 g/kg en deportistas, ganancia muscular o déficit calórico; en deportistas de resistencia Guille puede aplicar objetivos más bajos (p. ej. 1.2 g/kg). El cálculo en g/kg es interno: al cliente no se le presenta como objetivo, sino como resultado natural de una buena selección de alimentos.
- Periodización de carbohidratos alrededor de las sesiones intensas: es la estrategia central en deportistas; el foco de rendimiento son los CH, no la proteína.
- Plato de Harvard preferido sobre gramos y básculas; gramos solo si es clínicamente necesario.
- Pre-competición: evitar avena (la fibra soluble ralentiza el vaciado gástrico); preferir CH rápidos (dátiles, pasas, bebidas isotónicas).
- Bioimpedancia: secundaria/orientativa cuando hay datos ISAK o DEXA.
- Cena libre (sábado por defecto, o el día pactado): herramienta de adherencia, no se elimina.
- Legumbres: mínimo 4 porciones/semana como base; en recetas prácticas, mejor conserva precocida (botes de 400 g, escurridos y aclarados).
- Productos animales, cuando se incluyen: la **jerarquía** indica qué elegir (pescado → huevo → carne blanca → carne roja → procesada) y la **frecuencia** indica cuánto (huevo prácticamente eliminado salvo insistencia del cliente: máx. 1–2 días/semana, nunca protagonista; pescado azul máx. 3–4 veces/semana). Son criterios distintos y compatibles; la aplicación final es criterio de Guille.
- Lácteos, si se usan: yogur de soja > queso fresco batido / yogur griego ligero > yogur griego normal o lácteos enteros (evitar estos últimos).
- Batidos proteicos: opcionales, solo si falta proteína o por conveniencia (2–3 días/semana como máximo).

## Estructura base del plan (orientativa)

- Distribución: Opción A, 5 comidas (Desayuno, Almuerzo, Comida, Merienda, Cena), para mantenimiento o ligero superávit. Opción B, 4 comidas (sin Almuerzo), para mantenimiento o ligero déficit. El almuerzo se elimina o se convierte en merienda según horario y objetivo.
- Cada día debería contener: mínimo 5 porciones de fruta/verdura, 1 cereal integral y 1 fuente de grasa saludable. Legumbres: mínimo 4 porciones a lo largo de la semana.
- Macros de referencia: HC 45–65%, proteína 10–20%, grasa 10–30% de las calorías.
- Ajustes habituales: si la persona baja más de un 1% del peso/semana, sube 100–150 kcal; si no baja, réstalas. Días de fuerza: +10–15% de hidratos (pre-entreno); días de descanso: −10–15% de hidratos y más proteína. Con hinchazón digestiva, reduce fructosa libre y separa la fruta de las legumbres.
- Batch cooking del domingo: siempre opcional. El plan es igual de válido sin él.

## Checklist antes de entregar

Recorre el checklist de la Sección 8 de la plantilla v5.0 y, además, comprueba (sin olvidar que los criterios son orientativos y que cada caso puede justificar una excepción):

- Calorías diarias dentro de ±50 kcal del objetivo; ratios macro dentro de rango.
- Proteína dentro de rango (comprobación interna, no se muestra al cliente como objetivo).
- Legumbres ≥ 4 porciones/semana; ≥ 5 porciones de fruta/verdura al día; ≥ 1 cereal integral y ≥ 1 grasa saludable al día.
- Base plant-based, con excepciones animales individualizadas; jerarquía de lácteos respetada; huevo reducido.
- Cena libre incluida (sábado o día pactado).
- Tiempo de preparación y alimentos realistas y accesibles para el cliente; aversiones respetadas.
- Instrucciones claras y transportables (nada de 50 páginas).
- JS validado con `node --check`, sin duplicación de contenido ni de IDs tras mover secciones, y archivo final llamado `index.html`.

## Repo y despliegue

- Estructura: cada cliente tiene su propio repo, con su planificación en `index.html` en la raíz (es lo que publica GitHub Pages). Los PDFs e imágenes del cliente van en `cliente.html`, la interfaz genérica del repo principal `panel-principal`: se accede con usuario y contraseña (Supabase) y desde ahí se enlaza al `index.html` del cliente. Alternativa, solo si Guille lo decide: un botón en el propio `index.html` con el CSS de botón que ya existe en él (el estilo de los botones de documentos de la plantilla, Sección 4.4, que enlazan a `./assets/`). La organización de archivos la gestiona Guille: no la cambies por iniciativa propia.
- Nunca hagas commit ni push sin que Guille lo pida. Antes, resume qué cambia.
- Commits pequeños, un cambio por commit, con mensaje descriptivo en español.
- Tras un push, la publicación en GitHub Pages tarda 1–2 minutos: verifica el resultado en la URL.
- Nunca guardes tokens, claves ni credenciales en el repo, en archivos ni en mensajes de commit.
- No renombres ni muevas archivos existentes sin preguntar.

## Notas técnicas HTML/PDF

- `weasyprint` es el motor fiable para PDF (no `wkhtmltopdf`); usa `'Liberation Sans', Arial, sans-serif` (no `system-ui`).
- Los emojis dan problemas de renderizado en PDF/weasyprint: sustitúyelos por elementos dibujados en CSS si el documento se exporta a PDF.
- Ediciones grandes de HTML existente: reemplazo de texto dirigido (`str_replace`); reescritura completa solo si es imprescindible.
- Los recursos del propio plan (p. ej. el logo) van en base64 embebidos en el HTML, para portabilidad entre visor, navegador local y GitHub Pages. Las imágenes y PDFs del cliente no entran aquí: van en `cliente.html`.
- `localStorage` para el tachado de la lista de compra es intencional (se reinicia al cerrar la página = reinicio semanal).
