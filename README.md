# LibretIA

**Cuaderno de investigación con IA** al estilo NotebookLM, en un único fichero HTML que
funciona entero en el navegador: sin servidor, sin build y sin base de datos remota.

Reproduce de forma navegable el comportamiento del skill
[`open-notebook`](https://github.com/K-Dense-AI/scientific-agent-skills/tree/main/skills/open-notebook)
(K-Dense AI), que a su vez orquesta el proyecto [open-notebook](https://github.com/lfnovo/open-notebook).

## Qué hace

- **Cuadernos** con fuentes, chat y notas, guardados en IndexedDB (todo local).
- **Fuentes**: PDF, DOCX, TXT/MD/CSV, texto pegado, enlaces (Tavily Extract) y
  descubrimiento web (Tavily Search) con selección previa de resultados.
- **Búsqueda vectorial**: troceado e indexado con `text-embedding-3-small` y
  recuperación por similitud coseno reforzada léxicamente.
- **Chat con citas verificables**: `gpt-6-luna` responde solo sobre los extractos
  recuperados y marca `[1]`, `[2]`; cada marcador abre el pasaje literal y su URL.
- **Estudio**: resumen ejecutivo, guía de estudio, FAQ, cronología, documento
  informativo, mapa conceptual, métodos e instrucciones propias.
- **Resumen en audio**: guion a dos voces locutado con las voces del propio navegador
  (`speechSynthesis`, sin coste) o con `tts-1` de OpenAI si se quiere un WAV descargable.
- **Exportación** del cuaderno completo a Markdown.

## Uso

1. Abre `https://fborrasumh.github.io/libretia/` (o sirve `index.html` por http).
2. En **Ajustes**, pega tu clave de OpenAI y, si quieres fuentes web, la de Tavily.
   Se guardan solo en el `localStorage` de tu navegador.
3. Crea un cuaderno, añade fuentes y pregunta.

> Las claves viajan directamente desde tu navegador a OpenAI y Tavily. No uses este
> despliegue público con claves de organización sin restricciones de gasto.

## Autoría

Fernando Borrás Rocher — Universidad Miguel Hernández de Elche
ORCID [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)
Catálogo: <https://fborrasumh.github.io/ia/>

Licencia MIT.
