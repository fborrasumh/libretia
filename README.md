# LibretIA

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22166211.svg)](https://doi.org/10.5281/zenodo.22166211)

**Cuaderno de investigación con IA y citas verificadas**, al estilo NotebookLM, en un único fichero HTML que funciona entero en el navegador: sin servidor, sin instalación y sin base de datos remota.

**Usar la app:** https://fborrasumh.github.io/libretia/

**Idiomas:** español (por defecto), inglés y portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- **Cuadernos** con fuentes, chat, notas y resumen en audio, guardados en el navegador (IndexedDB).
- **Fuentes**: PDF con texto, Word (.docx), PowerPoint (.pptx), TXT, Markdown y CSV leídos en el navegador; texto pegado; enlaces (Tavily Extract) y descubrimiento web (Tavily Search) con selección previa de resultados.
- **Búsqueda local**: cada fuente se trocea en fragmentos y se indexa en el propio navegador con BM25. Para indexar no se envía nada a ningún proveedor.
- **Chat con citas**: ante cada pregunta se recuperan los fragmentos más parecidos de las fuentes seleccionadas y solo esos se envían a la IA, que responde marcando `[1]`, `[2]`…; cada marcador abre el pasaje exacto enviado.
- **Comprobación por código** de cada respuesta y cada nota: marcadores que no corresponden a ningún fragmento enviado, frases entrecomilladas que no aparecen literalmente en el material, cifras que no están en él (incluidos importes con separador de miles) y respuestas sin ninguna cita.
- **Estudio**: resumen ejecutivo, guía de estudio, preguntas frecuentes, cronología, documento informativo, mapa conceptual, métodos e instrucción propia; preguntas sugeridas.
- **Resumen en audio**: guion a dos voces locutado con las voces del navegador (sin coste) o con `tts-1` de OpenAI para obtener un WAV descargable. Las cifras del guion que no están en las fuentes se señalan.
- **Exportación** del cuaderno (o de una nota) a Word y Markdown, con los avisos de verificación. El Word se genera en el navegador, sin red.
- **Ejemplo sin clave** en los tres idiomas, con fuentes ficticias marcadas como tales.

## Cómo se usa la IA

Con la propia clave de **OpenAI, Google Gemini o Anthropic Claude** (botón «IA»), con un desplegable de los modelos disponibles para esa clave. La clave de Tavily (opcional) se configura en el mismo panel. Las claves se guardan solo en el `localStorage` del navegador y se envían únicamente a cada proveedor, en la cabecera de la petición.

## Privacidad

- En el navegador: cuadernos, fuentes, índice de búsqueda, notas, audios y claves.
- Hacia el proveedor de IA: la pregunta y los fragmentos recuperados (o, en el estudio y el audio, un extracto de las fuentes seleccionadas), con correos, DNI/NIE y teléfonos enmascarados. Antes del primer envío de cada sesión se muestra una muestra de lo que sale y hay que confirmarlo.
- Hacia Tavily (solo si se usa): las búsquedas y los enlaces. Hacia OpenAI (solo para el WAV): el guion del audio.

## Límites

- La búsqueda es por palabras (BM25), no semántica: preguntas en otro idioma que las fuentes o con sinónimos pueden no recuperar el fragmento adecuado. Si no hay coincidencias se envía el comienzo de cada fuente.
- Que una cita exista no garantiza que la IA la haya interpretado bien: hay que leer el pasaje. El código comprueba existencia, literalidad y cifras, no el sentido.
- Los PDF escaneados (sin capa de texto) no se pueden leer. Las imágenes de los documentos no se usan.
- El material de estudio y el audio resumen; no sustituyen a leer las fuentes.
- Probado con IA, Tavily y voz de OpenAI **simulados** (Playwright); no se ha probado con claves reales en esta versión.

## Novedades de la versión 2.0.0

Reescrita sobre el sistema Forja: OpenAI, Gemini o Claude; búsqueda local BM25 en lugar de embeddings de OpenAI; comprobación por código de citas, entrecomillados y cifras; aviso previo con datos personales enmascarados; español, inglés y portugués; ejemplo sin clave; exportación a Word. Los cuadernos guardados con la versión 1.0 se migran automáticamente al abrir la app.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche). ORCID: [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

**Origen de la idea:** inspirada en el skill [`open-notebook`](https://github.com/K-Dense-AI/scientific-agent-skills/tree/main/skills/open-notebook) de K-Dense AI y en el proyecto [open-notebook](https://github.com/lfnovo/open-notebook), alternativas abiertas a NotebookLM. LibretIA no reutiliza su código.

Catálogo: <https://fborrasumh.github.io/ia/>

## Cómo citar

Borrás Rocher, F. (2026). *LibretIA* (v2.0.0) [Software]. Zenodo. https://doi.org/10.5281/zenodo.22166211

## Licencia

MIT. Véase [LICENSE](LICENSE).
