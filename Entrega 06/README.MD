# Entrega 06 - Webstory: Especies al Límite

## Titular del reportaje
**Especies al Límite: La doble extinción de la fauna chilena**

## Resumen del reportaje
Este reportaje de periodismo de datos explora un fenómeno silencioso que afecta a la fauna chilena: la "doble extinción". A través de una narrativa interactiva, la webstory evidencia cómo, mientras íconos animales como el huemul o el pingüino de Humboldt dominan nuestro imaginario y el espacio mediático, decenas de especies endémicas (como el Borrachito o el Caracol de Paposo) no solo enfrentan la extinción biológica por la pérdida de su hábitat, sino también una profunda "extinción digital e informativa". El proyecto busca visibilizar a estas especies ignoradas por la falta de carisma mediático.

## Análisis de Hipótesis
**Hipótesis inicial:** Las especies con menor "carisma" o atractivo visual reciben significativamente menos atención pública y mediática, lo que las relega a un segundo plano en los esfuerzos de conservación y en la memoria colectiva del país, sufriendo una doble vulnerabilidad.

**Evolución:** A lo largo de la investigación y el cruce de datos, la hipótesis no solo se demostró, sino que se complejizó. Descubrimos fenómenos paralelos como la "paradoja del carisma" (donde especies como la Chinchilla lideran las búsquedas en Wikipedia no por preocupación ecológica, sino por su valor como mascotas) y la "asfixia del espacio mediático", donde una especie popular acapara el 100% del protagonismo en las noticias, dejando en la invisibilidad absoluta a especies con el mismo nivel de riesgo crítico, como la ranita de Darwin del Norte.

## Proceso de Construcción de la Página Web
El desarrollo técnico y la maquetación de la webstory fue un proceso iterativo de mucho ensayo y error. Tuvimos que tomar decisiones de código (HTML/CSS/JS) para que la tecnología no entorpeciera la narrativa, sino que la potenciara:

1. Comenzamos estructurando la página bajo un concepto de "contenedor estrecho" (`max-width: 800px`), imitando el formato de lectura de las revistas de periodismo narrativo para evitar la fatiga visual en pantallas grandes. Creamos una paleta de colores personalizada mediante variables CSS (`:root`) usando tonos crema (`#FBF8F0`) para el fondo y azules oscuros para el texto, asegurando la legibilidad. Para la inmersión, programamos un *Splash Screen* (pantalla de inicio) a pantalla completa con un fondo oscurecido que bloquea el *scroll* nativo y obliga al usuario a interactuar (hacer clic) para revelar el reportaje mediante una transición suave.

2. La integración de los gráficos fue el mayor reto técnico. Los JSON generados por Vega-Lite venían con dimensiones rígidas (`width` y `height` fijos) que rompían la responsividad de la página en distintas pantallas. Además, lidiamos con problemas de escala en la codificación visual: en el gráfico de dispersión (extinción virtual), el valor de las burbujas (`size: 260`) generaba una mancha enorme (el "huevo gigante") que tapaba el resto de los datos. Lo solucionamos "limpiando" el código JSON: eliminamos las medidas estáticas, recalibramos las escalas (bajando el *size* a 60), y creamos la clase CSS `.vega-embed-container` forzando a los *canvas* a ocupar el 100% de su contenedor (`width: 100% !important`), logrando gráficos nítidos y adaptables.

3. Intentamos implementar un modelo complejo de *scrollytelling* usando `position: sticky` para que los gráficos quedaran anclados mientras el texto flotaba sobre ellos. Sin embargo, esto generó severos problemas de superposición: los gráficos tapaban los párrafos anteriores y las capas de `z-index` se desconfiguraron. Finalmente, optamos por refactorizar el CSS hacia un diseño más limpio y robusto: un flujo lineal en bloques, asegurando que cada gráfico tuviera su espacio de respiración (`margin-top/bottom`) sin solapamientos.

4. Al integrar los *scripts* de Vega, la consola de JavaScript arrojaba errores críticos porque los archivos de texto originales traían saltos de línea ocultos. Tras depurar la sintaxis de los tres JSON e insertarlos en sus respectivos contenedores, la página estabilizó. Finalmente, para no saturar la lectura con la taxonomía y datos duros de cada animal, programamos "Fichas Técnicas" dinámicas mediante botones de acordeón en JavaScript, ocultando la información técnica hasta que el usuario decida desplegarla.

## Tabla de Autoría

| Elemento / Componente del Reportaje | Martina | Virginia | Carolina |
|:---|:---:|:---:|:---:|
| **Investigación y Base de Datos Ecológica (MMA)** | X | | |
| **Investigación y Base de Datos Digital (Wikipedia)** | | X | |
| **Investigación y Base de Datos Mediática (Prensa)** | | | X |
| **Redacción de Crónica (Sección 1: Regio y Fichas)** | X | | |
| **Redacción de Crónica (Sección 2: Paradoja del Carisma)** | | X | |
| **Redacción de Crónica (Sección 3: Asfixia del Espacio)** | | | X |
| **Construcción de Estructura y Semántica HTML** | **X** | **X** | **X** |
| **Maquetación, Diseño Visual y Estilos CSS** | **X** | **X** | **X** |
| **Programación de Interactividad (Splash Screen y Acordeones JS)** | **X** | **X** | **X** |
| **Integración, Depuración y Responsividad de Visualizaciones** | **X** | **X** | **X** |

*(Nota de autoría: Si bien cada integrante lideró el levantamiento inicial de una base de datos y la redacción de su respectiva sección, la construcción del sitio web, la resolución de conflictos responsivos en CSS, el diseño de la interfaz y la depuración del código de los gráficos de Vega-Lite se realizaron de manera colaborativa).*