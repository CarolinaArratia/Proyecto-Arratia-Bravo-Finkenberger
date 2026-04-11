# Documentación
###### Historial de procesos y decisiones

## 1. Elección y Curaduría de la Muestra:
La base de datos original del Ministerio del Medio Ambiente contenía miles de registros de diversas categorías. Para los fines de esta investigación, el equipo decidió realizar un filtro crítico bajo los siguientes criterios:

**Prioridad Ecológica:** Se seleccionaron únicamente especies clasificadas en Peligro Crítico (CR), por ser las que requieren mayor visibilidad mediática inmediata.

**Manejabilidad y Foco:** Se redujo la lista a 70 especies para permitir un análisis profundo y manual de la cobertura de prensa, Wikipedia y Google Trends, asegurando que cada dato recolectado fuera verificado y no solo un conteo automático.

**Consistencia del equipo:** Esta selección fue la base compartida para las tres integrantes del grupo. Mientras una parte del equipo se enfocó en la presencia en la enciclopedia Wikipedia, la otra (cobertura de medios) utilizó esta misma lista para rastrear la huella digital en la prensa chilena, garantizando que ambos análisis se crucen sobre los mismos sujetos de estudio.


## 2. Estrategia de búsqueda y limpieza de ruido:
Uno de los mayores obstáculos fue la ambigüedad de los nombres. Especies como el "Caracol" o el "Borrachito" generaban miles de resultados que no tenían nada que ver con la biodiversidad (restaurantes, canciones o noticias policiales).

**Decisión tomada:** En lugar de aceptar los resultados masivos, se optó por usar operadores de exclusión. Por ejemplo, para el caracol, se configuró la búsqueda como "caracol" -música -canción -receta. Esto permitió "limpiar" la base antes de que los datos ingresaran al Excel, asegurando que cada número de mención sea real.

**Herramientas:** Se utilizó el Playground de SerpApi para testear estas exclusiones antes de descargar los archivos finales.

## 3. Justificación de la estructura ID y cruce de datos:
Para esta entrega, decidimos que cada especie tuviera una sola fila pero múltiples archivos de respaldo.

**¿Por qué?:** Si una especie (como el ID 45) tiene un archivo para su nombre común y otro para el científico, podemos analizar por qué un nombre "vende" más que otro en la prensa.

**Organización:** Se mantuvo el mismo orden de ID que los datos de Wikipedia y Google Trends de los otros integrantes del grupo. Esto asegura que, al final del semestre, podamos unir todas las tablas sin que se produzcan inconsistencias o se dupliquen especies.

## 4. Clasificación de medios (Nacional vs. Regional):
Se tomó la decisión editorial de separar las menciones por alcance.

**Decisión tomada:** Esto responde a la hipótesis de que existe un centralismo mediático. Al separar los datos, podemos ver si los medios de Santiago solo hablan de animales "famosos" (como el Picaflor de Arica) mientras los medios regionales son los únicos que cubren especies menos conocidas (como la Araña Pollito).

## 5. Uso de valores 0 y 1:
Aunque para una persona es más fácil leer "Sí" o "No", decidimos usar el formato 1 (Sí) y 0 (No).

**Razón técnica:** Esto permite que la base de datos sea "procesable". Al tener números, podemos sacar porcentajes rápidos (ej: "Solo el 10% de las especies tienen foto en las noticias") y permite que el archivo sea compatible con herramientas de visualización de datos más avanzadas.

## 6. Fuentes utilizadas y por qué:

**SerpApi (Google News):** Fue elegida porque captura la "huella digital" de la prensa. Si una noticia no aparece aquí, es muy probable que el ciudadano común nunca se entere de la existencia de esa especie.

**Nómina MMA:** Se eligieron solo especies en Peligro Crítico (CR) para poner a prueba la eficiencia de la prensa: si un animal está a punto de desaparecer y nadie habla de él, estamos frente a una falla grave de la comunicación ambiental.

### Preguntas que nuestra base de datos puede responder:

1. ¿Es verdad que las especies "carismáticas" (las que se ven bonitas o tiernas) tienen más fotos en la prensa que los insectos o caracoles?

2. ¿Cuántas especies en peligro crítico son totalmente invisibles para los medios de comunicación en un semestre completo?

3. ¿La prensa nacional usa nombres científicos para sonar más profesional, o prefiere los nombres comunes para llegar a más gente?