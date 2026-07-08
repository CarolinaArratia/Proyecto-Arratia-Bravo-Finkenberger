### Gráfico 1: Especies amenazadas por región
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