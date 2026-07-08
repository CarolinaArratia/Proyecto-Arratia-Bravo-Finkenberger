# Entrega 06 - Webstory: Especies al Límite

## Titular del reportaje
**Especies al Límite: La doble extinción de la fauna chilena**

## Resumen del reportaje
Este reportaje de periodismo de datos explora un fenómeno silencioso que afecta a la fauna chilena: la "doble extinción". A través de una narrativa interactiva, la webstory evidencia cómo, mientras íconos animales como el huemul o el pingüino de Humboldt dominan nuestro imaginario y el espacio mediático, decenas de especies endémicas (como el Borrachito o el Caracol de Paposo) no solo enfrentan la extinción biológica por la pérdida de su hábitat, sino también una profunda "extinción digital e informativa". El proyecto busca visibilizar a estas especies ignoradas por la falta de carisma mediático.

## Análisis de Hipótesis
**Hipótesis inicial:** Las especies con menor "carisma" o atractivo visual reciben significativamente menos atención pública y mediática, lo que las relega a un segundo plano en los esfuerzos de conservación y en la memoria colectiva del país, sufriendo una doble vulnerabilidad.

**Evolución:** El desarrollo del reportaje y la comprensión de los datos atravesaron tres etapas clave:
- **Punto de partida**: El proyecto comenzó bajo la premisa de que los animales "atractivos" (por tamaño, color o simpatía) se transformaban en símbolos reconocibles de la biodiversidad, dejando fuera del foco a los organismos menos familiares. El concepto de "carisma" se entendía de forma superficial, asociado únicamente a la apariencia física.

- **Punto de quiebre**: Al procesar las métricas de tráfico en Wikipedia, la hipótesis estética colapsó. El hecho de que un pequeño roedor (chinchilla) críticamente amenazado superara drásticamente en clics al huemul (emblema del escudo nacional) o al pingüino de Humboldt reveló variables ocultas. Tras investigar la literatura científica, identificamos que la presión comercial histórica (la industria peletera de los siglos XIX y XX) y el éxito del animal en el mercado global de mascotas en cautiverio eran los verdaderos motores de su popularidad digital.

- **La resignificación**: La narrativa evolucionó para integrar el concepto científico de "extinción virtual". Comprendimos que el "carisma mediático" no es solo un atributo visual, sino un fenómeno de factores desconocidos que altera que altera el ecosistema de la información. La curva plana del fondo del gráfico sí demostró la asfixia de peces, insectos y reptiles, pero el pico de la chinchilla demostró que la popularidad en internet puede ocultar trágicamente la inminente desaparición real de una especie en su hábitat natural.

**Hipótesis final:** Existen factores indeterminados ajenos al riesgo ecológico o la estética que condicionan la fama digital de la fauna, marginando a la mayoría de las especies de la conversación social.

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