# Análisis del Diseño de la Historia

## 1. Diseño de la Información e Interacción
La estructura narrativa se diseñó bajo el formato de **Scrollytelling**. El recorrido del usuario está fríamente calculado para atrapar la atención y no abrumar con datos duros desde el inicio:
* **Splash Screen Inmersivo:** El usuario es recibido por una pantalla que ocupa el 100% del viewport bloqueando el scroll, forzando un clic interactivo para "descubrir" la historia.
* **Estructura Lineal y Contextual:** Pasamos de lo macro (qué es una región y cuántas especies hay) a lo micro (el desinterés digital y la falta de prensa).
* **Scrollytelling:** Los gráficos de Vega-Lite se fijan en el fondo de la pantalla (`position: sticky`), mientras tarjetas de texto semi-transparentes flotan sobre ellos al hacer scroll. Esto permite diseccionar gráficos complejos (como el de Wikipedia) en pequeñas pastillas de información legibles.
* **Lectura a doble capa (Acordeones):** Para no interrumpir la narrativa principal con datos taxonómicos aburridos, diseñamos componentes interactivos desplegables (Acordeones de Fichas) al final de cada sección. Si el usuario quiere saber más del Borrachito o la Chinchilla, profundiza por voluntad propia.

## 2. Comentarios sobre la Crónica y Textos
El tono de la redacción busca ser periodístico, empático y explicativo. 
* **Estilo narrativo:** Evitamos el tono enciclopédico. Humanizamos a las especies con metáforas cotidianas (ej. comparar el ecosistema mediático con "un hermano que roba la atención en reuniones familiares" o describir al Borrachito como alguien ebrio caminando torpemente).
* **Refuerzo Visual-Narrativo:** Los textos de las tarjetas del scrollytelling están redactados para dirigir la mirada del lector hacia hallazgos específicos en el gráfico que tienen de fondo ("Al mirar el gráfico...", "Mientras la aristocracia digital captura los clics...").

## 3. Decisiones sobre Elementos Visuales
La identidad visual fue codificada en variables CSS (`:root`) para mantener consistencia:
* **Paleta de colores:** Elegimos tonos que evocan la naturaleza y la seriedad del periodismo de datos, pero con suficiente contraste web:
    * **Fondo (`#FBF8F0`):** Un tono hueso/crema que reduce la fatiga visual en lecturas largas, imitando el papel editorial.
    * **Texto principal (`#1F3D5B`):** Azul oscuro casi negro, mucho más suave de leer que el negro puro.
    * **Acentos y Títulos (`#91532B` / `#86223E`):** Tonos tierra y burgundy para alertar sobre la crisis y el "peligro".
    * **Interfaz (`#187670`):** Un verde/turquesa utilizado para guiar las interacciones (botones, líneas, menú).
* **Tipografía:** * Para titulares usamos **Capriola** (sans-serif), que aporta un tono distintivo, moderno y orgánico.
    * Para el cuerpo del texto utilizamos **Lora** (serif), una fuente diseñada específicamente para mantener una excelente legibilidad en historias largas y reportajes en pantallas.
* **Layout:** Se optó por una lectura en "contenedor estrecho" (`max-width: 850px` y `680px` para textos), imitando las columnas de revistas de periodismo narrativo, asegurando que el ojo no se canse leyendo líneas demasiado largas de borde a borde de la pantalla.