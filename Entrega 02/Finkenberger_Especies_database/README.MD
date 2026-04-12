# 4. Documentación

- Limpieza de datos

El proceso se realizó a partir de una nómina inicial de especies sin limpiar, proveniente de los registros oficiales. A partir de esta base, se trabajó utilizando herramientas de hoja de cálculo, específicamente mediante la creación de distintas pestañas dentro de un mismo archivo para organizar las etapas del proceso.
En una primera etapa, se construyó una base de datos reducida, seleccionando únicamente las variables consideradas relevantes para el análisis: nombre común, nombre científico, reino, clase, endemismo respecto de Chile, distribución por regiones y categoría de conservación vigente.
Sobre esta base, se aplicaron criterios de filtrado. Se seleccionaron únicamente las especies correspondientes al reino Animalia y aquellas que fueran endémicas de Chile. En cuanto a la categoría de conservación, se filtraron exclusivamente las especies clasificadas en peligro crítico (CR), incluyendo todas sus variantes. Como resultado, se obtuvo una base de datos compuesta por 70 especies.
Posteriormente, a partir de esta primera base, se construyó una segunda base de datos en la que las especies en categoría de peligro crítico fueron organizadas según su distribución por regiones. Para ello, se replicaron los registros de especies en cada una de las regiones en las que se encuentran presentes, lo que permitió analizar la concentración territorial de estas. Como resultado, se obtuvieron 84 registros asociados a presencia de especies en distintas regiones del país. Asimismo, se identificaron regiones sin presencia de especies en esta categoría, como Aysén, Insular, Antártica, Isla de Pascua y Salas y Gómez.
En una tercera etapa, se replicó este mismo procedimiento para las especies clasificadas en la categoría de “En Peligro” (EN). Durante el proceso, se mantuvieron algunas categorías específicas presentes en la base original, como “ENR” (en peligro rara), con el fin de conservar información relevante sobre la condición de ciertas especies. En este caso, se obtuvo una base de 136 especies, la cual posteriormente fue organizada por región, alcanzando un total de 225 registros. Al igual que en el caso anterior, no se observó registro en algunas regiones, como la Antártica, Isla de Pascua y Salas y Gómez.
De esta forma, se construyó una base consolidada que integra tanto las especies en peligro crítico (CR) como aquellas en peligro (EN), alcanzando un total de 206 especies. Al distribuir estas por región, se obtuvo un total de 309 registros.
Finalmente, se identificaron casos con ausencia de información (“sin datos”), los cuales fueron mantenidos en la base para no alterar la integridad de los registros. Estos corresponden a casos específicos, como _Phymaturus vociferator_ en la región de Ñuble, en estado CR, y _Cheirodon kiliani_ en la región de La Araucanía, clasificado en la categoría EN-RARA, denominación que se prefirió por mayor claridad en lugar de EN-R.

- Fuente de datos utilizada

La base de datos utilizada proviene del Ministerio del Medio Ambiente de Chile, específicamente de los registros oficiales del Reglamento de Clasificación de Especies (RCE). Esta fuente fue seleccionada por su carácter oficial y su confiabilidad, ya que contiene información validada sobre el estado de conservación de la biodiversidad en el país.

- Preguntas que se pueden responder con la base de datos

1. ¿Qué regiones de Chile concentran una mayor cantidad de especies en peligro crítico y en peligro de extinción?
2. ¿Existen regiones que no presentan especies en estas categorías de amenaza?
3. ¿Cuántas veces aparece una especie en distintas regiones del país?
