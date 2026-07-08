# Análisis de Visualizaciones

## 1. Análisis de las visualizaciones y la historia
Nuestra webstory utiliza tres visualizaciones de datos clave, cada una diseñada para comunicar una dimensión específica de nuestra hipótesis sobre la "doble extinción":

* **Vis 1: El contexto biológico (Gráfico de barras horizontales).** Muestra la cantidad de especies amenazadas (CR, EN, EN-RARA) agrupadas por región. El mensaje principal es dimensionar la vulnerabilidad endémica de Chile. Usamos barras horizontales para facilitar la lectura de los nombres de las regiones y evidenciar rápidamente qué zonas concentran el mayor riesgo.
* **Vis 2: La extinción virtual (Gráfico de burbujas/dispersión).** Contrasta el volumen de visitas en Wikipedia con diferentes especies amenazadas. El mensaje es romper suposiciones: muestra la "paradoja del carisma", donde la Chinchilla domina por interés doméstico, mientras la "aristocracia digital" (Huemul, Pingüino) deja en el piso absoluto (0 visitas) a insectos y reptiles.
* **Vis 3: La asfixia mediática (Gráfico de distribución/barras apiladas horizontales).** Mide el porcentaje de protagonismo en noticias. Comunica visualmente cómo el espacio mediático es finito: el Pingüino de Humboldt ocupa grandes bloques de atención, ahogando a especies invisibles como el Picaflor de Juan Fernández o el Caracol de Paposo, representados por porciones minúsculas.

## 2. Generación y Código
Las tres visualizaciones fueron desarrolladas utilizando la librería **Vega-Lite** embebida en JavaScript. A continuación se detallan las especificaciones JSON utilizadas para la renderización interactiva de cada gráfico, incluyendo sus respectivas bases de datos tabuladas:

### Gráfico 1: Especies amenazadas por región (Desarrollado por Martina)
Se utilizó una concatenación vertical (vconcat) para incluir un resumen superior y un mark: bar codificando el eje Y con las Regiones y el color según categoría de conservación.

```json
{
  "config": {
    "view": {"continuousWidth": 300, "continuousHeight": 300, "stroke": null},
    "axis": {"labelColor": "#1A2C46", "titleColor": "#1A2C46"},
    "legend": {"labelColor": "#1A2C46", "titleColor": "#1A2C46"},
    "title": {"color": "#1A2C46", "fontSize": 20}
  },
  "vconcat": [
    {
      "data": {"name": "data-f8523f23d62a8f59d07c08580ddbc375"},
      "mark": {"type": "text", "align": "left", "color": "#1A2C46", "fontSize": 16},
      "encoding": {"text": {"field": "texto", "type": "nominal"}},
      "height": 40,
      "width": 800
    },
    {
      "data": {"name": "data-3e97910a1153d7b010473dbac440d445"},
      "mark": {"type": "bar"},
      "encoding": {
        "color": {
          "field": "CATEGORÍA VIGENTE",
          "scale": {
            "domain": ["CR", "EN", "EN-RARA"],
            "range": ["#8F2A3F", "#EFEDA0", "#1A2C46"]
          },
          "title": "Categoría",
          "type": "nominal"
        },
        "tooltip": [
          {"field": "REGIÓN", "title": "Región", "type": "nominal"},
          {"field": "CATEGORÍA VIGENTE", "title": "Categoría", "type": "nominal"},
          {"field": "TOTAL", "title": "Cantidad", "type": "quantitative"}
        ],
        "x": {"field": "TOTAL", "title": "Cantidad de especies", "type": "quantitative"},
        "y": {"field": "REGIÓN", "sort": "-x", "title": "Región", "type": "nominal"}
      },
      "height": 500,
      "title": "Especies amenazadas por región según categoría de conservación",
      "width": 800
    }
  ],
  "$schema": "[https://vega.github.io/schema/vega-lite/v5.20.1.json](https://vega.github.io/schema/vega-lite/v5.20.1.json)",
  "datasets": {
    "data-f8523f23d62a8f59d07c08580ddbc375": [
      {"texto": "CR: 82 especies   | EN: 227 especies   |   EN-RARA: 27 especies   | Total: 336 especies"}
    ],
    "data-3e97910a1153d7b010473dbac440d445": [
      {"REGIÓN": "Antofagasta (II)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 15},
      {"REGIÓN": "Antofagasta (II)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 15},
      {"REGIÓN": "Araucanía (IX)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 3},
      {"REGIÓN": "Araucanía (IX)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 17},
      {"REGIÓN": "Araucanía (IX)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 4},
      {"REGIÓN": "Arica y Parinacota (XV)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 2},
      {"REGIÓN": "Arica y Parinacota (XV)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 7},
      {"REGIÓN": "Arica y Parinacota (XV)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 4},
      {"REGIÓN": "Atacama (III)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 2},
      {"REGIÓN": "Atacama (III)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 9},
      {"REGIÓN": "Aysén (XI)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 3},
      {"REGIÓN": "Bío-Bío (VIII)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 9},
      {"REGIÓN": "Bío-Bío (VIII)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 22},
      {"REGIÓN": "Bío-Bío (VIII)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 5},
      {"REGIÓN": "Coquimbo (IV)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 3},
      {"REGIÓN": "Coquimbo (IV)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 14},
      {"REGIÓN": "De Los Lagos (X)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 11},
      {"REGIÓN": "De Los Lagos (X)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 1},
      {"REGIÓN": "De Los Ríos (XIV)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 2},
      {"REGIÓN": "De Los Ríos (XIV)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 14},
      {"REGIÓN": "De Los Ríos (XIV)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 3},
      {"REGIÓN": "Desventuradas", "CATEGORÍA VIGENTE": "CR", "TOTAL": 3},
      {"REGIÓN": "Desventuradas", "CATEGORÍA VIGENTE": "EN", "TOTAL": 2},
      {"REGIÓN": "Insular", "CATEGORÍA VIGENTE": "EN", "TOTAL": 3},
      {"REGIÓN": "Isla de Pascua", "CATEGORÍA VIGENTE": "EN", "TOTAL": 2},
      {"REGIÓN": "Juan Fernández", "CATEGORÍA VIGENTE": "CR", "TOTAL": 19},
      {"REGIÓN": "Juan Fernández", "CATEGORÍA VIGENTE": "EN", "TOTAL": 33},
      {"REGIÓN": "Juan Fernández", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 1},
      {"REGIÓN": "Maule (VII)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 3},
      {"REGIÓN": "Maule (VII)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 17},
      {"REGIÓN": "Maule (VII)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 1},
      {"REGIÓN": "Metropolitana (RM)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 5},
      {"REGIÓN": "Metropolitana (RM)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 18},
      {"REGIÓN": "Metropolitana (RM)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 3},
      {"REGIÓN": "O'Higgins (VI)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 6},
      {"REGIÓN": "O'Higgins (VI)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 10},
      {"REGIÓN": "O'Higgins (VI)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 3},
      {"REGIÓN": "Tarapaca (I)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 3},
      {"REGIÓN": "Tarapaca (I)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 4},
      {"REGIÓN": "Tarapaca (I)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 1},
      {"REGIÓN": "Valparaíso continental (V)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 5},
      {"REGIÓN": "Valparaíso continental (V)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 13},
      {"REGIÓN": "Valparaíso continental (V)", "CATEGORÍA VIGENTE": "EN-RARA", "TOTAL": 1},
      {"REGIÓN": "Ñuble  (XVI)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 1},
      {"REGIÓN": "Ñuble  (XVI)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 12},
      {"REGIÓN": "Ñuble (XVI)", "CATEGORÍA VIGENTE": "CR", "TOTAL": 1},
      {"REGIÓN": "Ñuble (XVI)", "CATEGORÍA VIGENTE": "EN", "TOTAL": 1}
    ]
  }
}
```

### Gráfico 2: Extinción Virtual (Desarrollado por Virginia)
Se utilizó un mark: circle ajustando la opacidad y asignando la variable tamaño (size) para diferenciar los grupos según volumen de visitas en Wikipedia.

```json
{
  "config": {
    "view": {"continuousWidth": 300, "continuousHeight": 300, "stroke": null},
    "axis": {
      "gridColor": "#EFEDA0",
      "gridOpacity": 0.6,
      "labelColor": "#1F3D5B",
      "labelFontSize": 13,
      "titleColor": "#1F3D5B",
      "titleFontSize": 14
    },
    "legend": {
      "labelColor": "#1F3D5B",
      "labelFontSize": 13,
      "symbolSize": 180,
      "titleFontSize": 14
    },
    "title": {
      "anchor": "start",
      "color": "#91532B",
      "fontSize": 22,
      "offset": 20,
      "subtitleColor": "#1F3D5B",
      "subtitleFontSize": 14
    }
  },
  "data": {"name": "data-403a539f6085133a54b9b0bdafd8c9de"},
  "mark": {"type": "circle", "opacity": 0.9, "size": 260},
  "encoding": {
    "color": {
      "field": "Grupo",
      "legend": {"orient": "top-right"},
      "scale": {
        "domain": ["Más visitadas", "Especies mediáticas", "Menos visitadas"],
        "range": ["#0695D1", "#86223E", "#1F3D5B"]
      },
      "title": "",
      "type": "nominal"
    },
    "tooltip": [
      {"field": "Nombre Científico", "title": "Nombre científico", "type": "nominal"},
      {"field": "Nombre Común", "title": "Nombre común", "type": "nominal"},
      {"field": "Clase", "title": "Clase", "type": "nominal"},
      {"field": "RCE", "title": "Categoría", "type": "nominal"},
      {"field": "Total Visitas (periodo seis meses)", "title": "Visitas", "type": "quantitative"}
    ],
    "x": {
      "field": "Total Visitas (periodo seis meses)",
      "title": "Total de visitas en Wikipedia (6 meses)",
      "type": "quantitative"
    },
    "y": {
      "axis": {"labelLimit": 500},
      "field": "Etiqueta",
      "sort": [
        "Pez (Genérico)",
        "Gusano Aterciopelado",
        "Lagartija Negro Azulada",
        "Liguay",
        "Ranita De Darwin",
        "Pingüino De Humboldt",
        "Huemul",
        "Lagartija De Fabián",
        "Zorro De Chiloé",
        "Chinchilla Costina"
      ],
      "title": "",
      "type": "nominal"
    }
  },
  "height": 450,
  "title": {
    "text": "Las especies amenazadas que sí vemos y las que ignoramos",
    "subtitle": ["Contraste de interés ciudadano y volumen de visitas digitales en Wikipedia"]
  },
  "width": 800,
  "$schema": "[https://vega.github.io/schema/vega-lite/v5.20.1.json](https://vega.github.io/schema/vega-lite/v5.20.1.json)",
  "datasets": {
    "data-403a539f6085133a54b9b0bdafd8c9de": [
      {
        "ID": 112,
        "Nombre Científico": "Chinchilla lanigera",
        "Nombre Común": "Chinchilla costina",
        "Clase": "Mammalia",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 9259.0,
        "Promedio Diario": "51",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Chinchilla_lanigera](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Chinchilla_lanigera) ",
        "Etiqueta": "Chinchilla Costina",
        "Grupo": "Más visitadas"
      },
      {
        "ID": 167,
        "Nombre Científico": "Lycalopex fulvipes",
        "Nombre Común": "Zorro de Chiloé",
        "Clase": "Mammalia",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 2152.0,
        "Promedio Diario": "12",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Lycalopex_fulvipes](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Lycalopex_fulvipes) ",
        "Etiqueta": "Zorro De Chiloé",
        "Grupo": "Más visitadas"
      },
      {
        "ID": 154,
        "Nombre Científico": "Liolaemus fabiani",
        "Nombre Común": "Lagartija de Fabián",
        "Clase": "Reptilia",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 1311.0,
        "Promedio Diario": "7",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Liolaemus_fabiani](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Liolaemus_fabiani) ",
        "Etiqueta": "Lagartija De Fabián",
        "Grupo": "Más visitadas"
      },
      {
        "ID": 214,
        "Nombre Científico": "Hippocamelus bisulcus",
        "Nombre Común": "huemul, taruca, wümul, güemul, shoan, shoen, trula, hueque, ciervo sur andino",
        "Clase": "Mammalia",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 988.0,
        "Promedio Diario": "5",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Hippocamelus_bisulcus](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Hippocamelus_bisulcus) ",
        "Etiqueta": "Huemul",
        "Grupo": "Especies mediáticas"
      },
      {
        "ID": 216,
        "Nombre Científico": "Spheniscus humboldti",
        "Nombre Común": "pingüino de Humboldt, pingüino, pájaro niño, patranka, Humboldt Penguin (inglés), Peruvian penguin (inglés)",
        "Clase": "Aves",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 952.0,
        "Promedio Diario": "5",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Spheniscus_humboldti](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Spheniscus_humboldti) ",
        "Etiqueta": "Pingüino De Humboldt",
        "Grupo": "Especies mediáticas"
      },
      {
        "ID": 87,
        "Nombre Científico": "Americobdella valdiviana",
        "Nombre Común": "Liguay, sanguijuela gigante valdiviana",
        "Clase": "Clitellata",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 15.0,
        "Promedio Diario": "0",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Americobdella_valdiviana](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Americobdella_valdiviana) ",
        "Etiqueta": "Liguay",
        "Grupo": "Menos visitadas"
      },
      {
        "ID": 160,
        "Nombre Científico": "Liolaemus nigrocoeruleus",
        "Nombre Común": "Lagartija negro azulada, Black Bluish Lizard (Inglés)",
        "Clase": "Reptilia",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 13.0,
        "Promedio Diario": "0",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Liolaemus_nigrocoeruleus](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Liolaemus_nigrocoeruleus) ",
        "Etiqueta": "Lagartija Negro Azulada",
        "Grupo": "Menos visitadas"
      },
      {
        "ID": 181,
        "Nombre Científico": "Paropisthopatus umbrinus",
        "Nombre Común": "Gusano aterciopelado, onicóforo (genérico)",
        "Clase": "Udeonycophora",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 8.0,
        "Promedio Diario": "0",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Paropisthopatus_umbrinus](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Paropisthopatus_umbrinus) ",
        "Etiqueta": "Gusano Aterciopelado",
        "Grupo": "Menos visitadas"
      },
      {
        "ID": 46,
        "Nombre Científico": "Pseudorestias lirimensis",
        "Nombre Común": "pez (genérico)",
        "Clase": "Actinopterygii",
        "RCE": "CR",
        "Total Visitas (periodo seis meses)": 5.0,
        "Promedio Diario": "0",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Pseudorestias_lirimensis](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Pseudorestias_lirimensis)",
        "Etiqueta": "Pez (Genérico)",
        "Grupo": "Menos visitadas"
      },
      {
        "ID": 215,
        "Nombre Científico": "Rhinoderma darwinii",
        "Nombre Común": "ranita de Darwin",
        "Clase": "Amphibia",
        "RCE": "EN",
        "Total Visitas (periodo seis meses)": 380.0,
        "Promedio Diario": "2",
        "URL Fuente": "[https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Rhinoderma_darwinii](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2025-09-25&end=2026-03-25&pages=Rhinoderma_darwinii) ",
        "Etiqueta": "Ranita De Darwin",
        "Grupo": "Especies mediáticas"
      }
    ]
  }
}
```

### Gráfico 3: La asfixia mediática (Desarrollado por Carolina)
Se estructuró mediante capas (layer) usando mark: rect para definir las proporciones exactas de protagonismo mediático y textos superpuestos (mark: text) para las etiquetas de las especies.

```json
{
  "config": {
    "view": {"continuousWidth": 300, "continuousHeight": 300},
    "background": "#FBF8F0"
  },
  "layer": [
    {
      "mark": {"type": "rect", "stroke": "white", "strokeWidth": 1},
      "encoding": {
        "color": {
          "field": "RCE",
          "scale": {"domain": ["CR", "EN"], "range": ["#86223E", "#91532B"]},
          "title": "Categoría de Riesgo",
          "type": "nominal"
        },
        "tooltip": [
          {"field": "Nombre común", "title": "Nombre Común", "type": "nominal"},
          {"field": "Nombre científico", "title": "Nombre Científico", "type": "nominal"},
          {"field": "RCE", "title": "Estado de Conservación", "type": "nominal"},
          {"field": "Ficha técnica", "title": "Ficha Técnica Descriptiva", "type": "nominal"}
        ],
        "x": {
          "axis": {"format": "%"},
          "field": "x0",
          "title": "Distribución del Espacio Mediático",
          "type": "quantitative"
        },
        "x2": {"field": "x1"},
        "y": {"value": 50},
        "y2": {"value": 350}
      }
    },
    {
      "mark": {
        "type": "text",
        "align": "center",
        "angle": 270,
        "baseline": "middle",
        "color": "white",
        "fontSize": 12,
        "fontWeight": "bold"
      },
      "encoding": {
        "text": {"field": "etiqueta_grafico", "type": "nominal"},
        "x": {"field": "xmid", "type": "quantitative"},
        "y": {"value": 200}
      }
    }
  ],
  "data": {"name": "data-6fe9bf1e4e767c9b7d3ed32c03bb2b6a"},
  "height": 400,
  "title": {
    "text": "LA ASFIXIA DEL ESPACIO MEDIÁTICO",
    "subtitle": ["Mientras algunas especies brillan en su protagonismo, otras son invisibles para los medios."],
    "color": "#91532B",
    "fontSize": 22,
    "subtitleColor": "#1F3D5B"
  },
  "width": 850,
  "$schema": "[https://vega.github.io/schema/vega-lite/v5.20.1.json](https://vega.github.io/schema/vega-lite/v5.20.1.json)",
  "datasets": {
    "data-6fe9bf1e4e767c9b7d3ed32c03bb2b6a": [
      {
        "Etiqueta": 216,
        "Nombre científico": "Spheniscus humboldti",
        "Nombre común": "Pingüino de Humboldt",
        "Clase": "Aves",
        "RCE": "EN",
        "Endémica": "No",
        "Apariciones": 76,
        "Protagonista": 76,
        "% Protagonismo": "100",
        "Foto": 76,
        "Link foto": "[https://live.staticflickr.com/65535/55263020062_f44250f42a.jpg](https://live.staticflickr.com/65535/55263020062_f44250f42a.jpg)",
        "Ficha técnica": "Vive en costas e islas del norte y centro de Chile. En Peligro (EN), nidifica en cavidades de guano y se ve afectado por la sobrepesca y el cambio climático.",
        "prop": 0.5277777777777778,
        "x0": 0.0,
        "x1": 0.5277777777777778,
        "xmid": 0.2638888888888889,
        "etiqueta_grafico": "Pingüino de Humboldt"
      },
      {
        "Etiqueta": 215,
        "Nombre científico": "Rhinoderma darwinii",
        "Nombre común": "Ranita de Darwin",
        "Clase": "Amphibia",
        "RCE": "EN",
        "Endémica": "No",
        "Apariciones": 24,
        "Protagonista": 24,
        "% Protagonismo": "100",
        "Foto": 24,
        "Link foto": "[https://live.staticflickr.com/65535/55264061388_d183652526.jpg](https://live.staticflickr.com/65535/55264061388_d183652526.jpg)",
        "Ficha técnica": "Habita bosques templados del sur. En estado En Peligro (EN), destaca porque el macho incuba los renacuajos en su saco vocal. Sus poblaciones declinan por el hongo quítrido y la deforestación.",
        "prop": 0.16666666666666666,
        "x0": 0.5277777777777778,
        "x1": 0.6944444444444444,
        "xmid": 0.6111111111111112,
        "etiqueta_grafico": "Ranita de Darwin"
      },
      {
        "Etiqueta": 49,
        "Nombre científico": "Rhinoderma rufum",
        "Nombre común": "Ranita de Darwin del Norte",
        "Clase": "Amphibia",
        "RCE": "CR",
        "Endémica": "SÍ",
        "Apariciones": 13,
        "Protagonista": 4,
        "% Protagonismo": "30,76923077",
        "Foto": 13,
        "Link foto": "[https://live.staticflickr.com/65535/55263020057_84a2207950.jpg](https://live.staticflickr.com/65535/55263020057_84a2207950.jpg)",
        "Ficha técnica": "Habitaba la zona central (Maule a Biobío). En Peligro Crítico (CR) y probablemente extinta, su desaparición se vincula a la pérdida de bosque nativo y la propagación de enfermedades fúngicas.",
        "prop": 0.09027777777777778,
        "x0": 0.6944444444444444,
        "x1": 0.7847222222222222,
        "xmid": 0.7395833333333333,
        "etiqueta_grafico": "Ranita de Darwin del Norte"
      },
      {
        "Etiqueta": 45,
        "Nombre científico": "Pristidactylus alvaroi",
        "Nombre común": "Lagarto gruñidor de Álvaro",
        "Clase": "Reptilia",
        "RCE": "CR",
        "Endémica": "SÍ",
        "Apariciones": 9,
        "Protagonista": 7,
        "% Protagonismo": "77,77777778",
        "Foto": 8,
        "Link foto": "[https://live.staticflickr.com/65535/55264324885_5b4d80044b.jpg](https://live.staticflickr.com/65535/55264324885_5b4d80044b.jpg)",
        "Ficha técnica": "Endémico de la Cordillera de la Costa central. En Peligro Crítico (CR), emite sonidos al ser amenazado. Su hábitat en cumbres boscosas como el Cerro El Roble es vulnerable a incendios.",
        "prop": 0.0625,
        "x0": 0.7847222222222222,
        "x1": 0.8472222222222222,
        "xmid": 0.8159722222222222,
        "etiqueta_grafico": "Lagarto gruñidor de Álvaro"
      },
      {
        "Etiqueta": 25,
        "Nombre científico": "Eulidia yarrellii",
        "Nombre común": "Picaflor de Arica",
        "Clase": "Aves",
        "RCE": "CR",
        "Endémica": "SÍ",
        "Apariciones": 8,
        "Protagonista": 8,
        "% Protagonismo": "100",
        "Foto": 8,
        "Link foto": "[https://live.staticflickr.com/65535/55264061478_8273248e77.jpg](https://live.staticflickr.com/65535/55264061478_8273248e77.jpg)",
        "Ficha técnica": "Habita valles de la Región de Arica. En Peligro Crítico (CR), es el ave más pequeña del país. Su extinción es inminente debido al uso de pesticidas y pérdida de vegetación.",
        "prop": 0.05555555555555555,
        "x0": 0.8472222222222222,
        "x1": 0.9027777777777778,
        "xmid": 0.875,
        "etiqueta_grafico": "Picaflor de Arica"
      },
      {
        "Etiqueta": 214,
        "Nombre científico": "Hippocamelus bisulcus",
        "Nombre común": "Huemul",
        "Clase": "Mammalia",
        "RCE": "EN",
        "Endémica": "No",
        "Apariciones": 8,
        "Protagonista": 5,
        "% Protagonismo": "62,5",
        "Foto": 8,
        "Link foto": "[https://live.staticflickr.com/65535/55264157039_b62cefd96c.jpg](https://live.staticflickr.com/65535/55264157039_b62cefd96c.jpg)",
        "Ficha técnica": "Reside en los bosques andino-patagónicos. En estado En Peligro (EN), este ciervo emblemático es Monumento Natural y enfrenta amenazas como ataques de perros, enfermedades ganaderas y fragmentación de hábitat.",
        "prop": 0.05555555555555555,
        "x0": 0.9027777777777778,
        "x1": 0.9583333333333334,
        "xmid": 0.9305555555555556,
        "etiqueta_grafico": "Huemul"
      },
      {
        "Etiqueta": 17,
        "Nombre científico": "Chilina angusta",
        "Nombre común": "Caracol de Paposo",
        "Clase": "Gastropoda",
        "RCE": "CR",
        "Endémica": "SÍ",
        "Apariciones": 4,
        "Protagonista": 1,
        "% Protagonismo": "25",
        "Foto": 3,
        "Link foto": "[https://live.staticflickr.com/65535/55264061428_f0682c5434.jpg](https://live.staticflickr.com/65535/55264061428_f0682c5434.jpg)",
        "Ficha técnica": "Habita exclusivamente en los oasis de niebla de Antofagasta. Clasificado en Peligro Crítico (CR), este molusco depende de la humedad de las nubes y sufre por la sequía extrema.",
        "prop": 0.027777777777777776,
        "x0": 0.9583333333333334,
        "x1": 0.9861111111111112,
        "xmid": 0.9722222222222223,
        "etiqueta_grafico": "Caracol de Paposo"
      },
      {
        "Etiqueta": 50,
        "Nombre científico": "Sclerostomulus nitidus",
        "Nombre común": "Borrachito",
        "Clase": "Insecta",
        "RCE": "CR",
        "Endémica": "SÍ",
        "Apariciones": 1,
        "Protagonista": 0,
        "% Protagonismo": "0",
        "Foto": 1,
        "Link foto": "[https://live.staticflickr.com/65535/55264157119_fa2a0bec27.jpg](https://live.staticflickr.com/65535/55264157119_fa2a0bec27.jpg)",
        "Ficha técnica": "Pequeña ave de valles del norte grande. En Peligro (EN), es un insectívoro esencial para su ecosistema, aunque la degradación de los valles desérticos amenaza su equilibrio local.",
        "prop": 0.006944444444444444,
        "x0": 0.9861111111111112,
        "x1": 0.9930555555555556,
        "xmid": 0.9895833333333334,
        "etiqueta_grafico": ""
      },
      {
        "Etiqueta": 51,
        "Nombre científico": "Sephanoides fernandensis",
        "Nombre común": "Picaflor de Juan Fernández",
        "Clase": "Aves",
        "RCE": "CR",
        "Endémica": "SÍ",
        "Apariciones": 1,
        "Protagonista": 0,
        "% Protagonismo": "0",
        "Foto": 1,
        "Link foto": "[https://live.staticflickr.com/65535/55264061568_47bfe31dc6.jpg](https://live.staticflickr.com/65535/55264061568_47bfe31dc6.jpg)",
        "Ficha técnica": "Exclusivo de la Isla Robinson Crusoe. En Peligro Crítico (CR), destaca por su plumaje rojizo único. Es amenazado severamente por gatos, coatíes y la invasión de plantas exóticas en su hábitat.",
        "prop": 0.006944444444444444,
        "x0": 0.9930555555555556,
        "x1": 1.0,
        "xmid": 0.9965277777777778,
        "etiqueta_grafico": ""
      }
    ]
  }
}
```
