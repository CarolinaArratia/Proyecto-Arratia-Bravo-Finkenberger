### Gráfico 3: La asfixia mediática 
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
