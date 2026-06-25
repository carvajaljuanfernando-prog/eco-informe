# Cómo leer un informe de ecocardiograma — manual interactivo

Página web autónoma (un solo `index.html`, sin frameworks ni dependencias de build) para enseñar a médicos no cardiólogos a interpretar los datos numéricos de un informe de ecocardiograma transtorácico.

**Autor:** Dr. Juan Fernando Carvajal Estupiñán — Cardiólogo Internista.

## Qué incluye

- Navegación lateral con 10 secciones (VI, función sistólica, AI, diástole, VD/presión pulmonar, válvulas, caso resuelto, referencia rápida, autoevaluación).
- **Clasificador interactivo de geometría del VI** (concéntrica / excéntrica) con cuadrante en vivo.
- **Asistente de función diastólica** (regla de mayoría sobre 4 variables).
- **Estimador de PSAP** a partir de la velocidad de RT y la VCI.
- Glosario en contexto (tooltips), tablas de referencia plegables y **autoevaluación con banco de 42 preguntas** en tres niveles de dificultad (básico, intermedio, avanzado o mixto), longitud configurable, reporte de desempeño por nivel y **no repetición** de preguntas entre intentos hasta agotar el banco.
- Diseño responsivo (funciona en celular) y diagramas en SVG (no requiere imágenes externas).

> Nota sobre la no repetición: el progreso de preguntas vistas se guarda en el navegador del usuario (`localStorage`). Si el usuario cambia de dispositivo o navegador, el conteo arranca de nuevo. Hay botones para reiniciar un nivel o todas las preguntas vistas.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en tu cuenta (`carvajaljuanfernando-prog`), por ejemplo **`eco-informe`**.
2. Sube el archivo `index.html` a la raíz del repo (arrastrar y soltar desde *Add file → Upload files*, o por `git`).
3. Ve a **Settings → Pages**.
4. En *Source* selecciona **Deploy from a branch**, rama **main** y carpeta **/ (root)**. Guarda.
5. En 1–2 minutos quedará publicado en:
   `https://carvajaljuanfernando-prog.github.io/eco-informe/`

Por git:
```bash
git init
git add index.html README.md
git commit -m "Manual interactivo de interpretación de ecocardiograma"
git branch -M main
git remote add origin https://github.com/carvajaljuanfernando-prog/eco-informe.git
git push -u origin main
```

## Añadir imágenes reales de ecocardiograma (opcional)

Los diagramas actuales son esquemas SVG (sin problemas de derechos ni de carga). Si más adelante quieres incluir clips/imágenes reales:

1. **Anonimízalos primero**: elimina metadatos DICOM con datos del paciente y, sobre todo, las anotaciones "quemadas" en la imagen (nombre, fecha). Confirma la base legal de uso (consentimiento / aval institucional).
2. Crea una carpeta `img/` en el repo y sube los archivos (PNG/JPG o MP4 para clips).
3. Reemplaza el bloque `<figure>...</figure>` correspondiente por `<img src="img/tu-archivo.png" alt="...">` o `<video src="img/tu-clip.mp4" controls muted loop>`.

## Notas

Metodología de adquisición y medición revisada según la guía **ASE 2019** de ecocardiograma transtorácico completo en adultos (Mitchell et al., JASE). Las cifras de referencia siguen ASE/EACVI 2015 (cuantificación de cámaras) y ASE/EACVI 2016 (función diastólica), que esa guía referencia. Material educativo; no sustituye el juicio clínico ni la valoración especializada.
