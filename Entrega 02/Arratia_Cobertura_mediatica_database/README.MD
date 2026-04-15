# Documentación
###### Historial de procesos y decisiones

## 1. Elección y Curaduría de la Muestra:
La base de datos original del Ministerio del Medio Ambiente es el punto de partida. Para nuestra investigación, el criterio de selección fue el estado de vulnerabilidad:

**Foco en la Urgencia:** Se analizaron especies en Peligro Crítico (CR). La muestra de 70 especies permitió rastrear no solo animales "famosos", sino también insectos, caracoles y anfibios que suelen ser invisibles para la prensa nacional.

**Consistencia del equipo:** Esta lista es el "corazón" del trabajo grupal. Al mantener los mismos IDs (del 1 al 70), aseguramos que cuando juntemos las bases de datos de Wikipedia y Prensa, los resultados sean comparables.

## 2. Estrategia de búsqueda y limpieza de ruido:
El principal desafío fue la **Ambigüedad Mediática**. Muchos nombres comunes en Chile se usan de forma genérica para distintas especies.

**El "Caso Araña Pollito" (ID 24):** Durante la limpieza, encontramos una noticia de *El Morrocotudo* titulada "Araña pollito: El mapa de las regiones...". Aunque el nombre común coincidía con nuestro ID 24 (*Euathlus parvulus*), el texto mencionaba científicamente a la *Grammostola rosea*. 
**Decisión tomada:** Aplicamos rigor periodístico y **descartamos la noticia**. Como la especie descrita no era la de nuestra lista oficial, incluirla habría inflado falsamente los datos de cobertura para una especie que, en la realidad, sigue siendo invisible.

## 3. Proceso de limpieza manual (Sin automatización):
A diferencia de otros procesos, decidimos **no utilizar Python ni herramientas de limpieza automatizada** para el análisis final. 

**Razón:** La detección de la "ceguera mediática" requiere una lectura humana. Una máquina podría contar una mención a "reptiles" como válida, pero nuestra metodología solo acepta menciones específicas. Revisamos cada URL manualmente para verificar:
1. Que la noticia fuera de un medio chileno.
2. Que la fecha estuviera dentro del rango (septiembre 2025 - marzo 2026).
3. Que la especie fuera realmente la protagonista o una mención relevante, descartando menciones en "menús" de navegación o publicidad.

## 4. Resultados del análisis (Muestra limpia):
Tras el proceso de limpieza, la base de datos pasó de un bruto de 190 resultados a una selección final de **21 registros de análisis**. 

**Hallazgos de la limpieza:**
* **Especies Estrella:** El Picaflor de Arica (ID 25) y el Lagarto Gruñidor de Álvaro (ID 45) acaparan casi el 80% de las noticias válidas.
* **Ceguera Absoluta:** Especies como el Caracol de Hualpén (ID 43) o el Sapo de Danko (ID 62) no registraron ni una sola mención en el semestre, confirmando nuestra tesis inicial.

## 5. Uso de valores 0 y 1:
Mantenemos el formato de 1 (Sí) y 0 (No) para las variables de análisis. Esto nos permite usar Tablas Dinámicas en Excel para responder preguntas complejas sin necesidad de contar manualmente. Por ejemplo, pudimos determinar rápidamente que el 100% de las noticias sobre el Picaflor de Arica incluyen foto, mientras que las noticias sobre caracoles terrestres (ID 17) carecen de apoyo visual.

## 6. Fuentes utilizadas y por qué:
**SerpApi (Google News):** Fue la herramienta elegida para la captura. La elegimos porque indexa tanto medios grandes (EMOL, BioBio) como medios regionales. Esto nos permitió ver que especies como el Caracol de Paposo (ID 17) solo aparecen cuando hay alertas gubernamentales nacionales, desapareciendo de la agenda regional el resto del tiempo.

### Preguntas que nuestra base de datos puede responder:

1. **¿Existe un sesgo de belleza?** Podemos cruzar el ID de la especie con la columna "Tiene foto" para demostrar si los animales "bonitos" (aves) tienen más presencia visual que los "feos" (insectos o caracoles).
2. **¿Quién educa más?** Al filtrar por "Usa N. Científico", podemos ver qué medios (nacionales vs regionales) contribuyen más a la alfabetización científica de la población.
3. **¿La prensa solo reacciona a la tragedia?** Cruzando el "Tono" con las fechas de publicación, la base muestra que el Lagarto Gruñidor solo aparece vinculado a incendios forestales (Tono: Alerta), demostrando que no hay una cobertura educativa constante, sino reactiva.
