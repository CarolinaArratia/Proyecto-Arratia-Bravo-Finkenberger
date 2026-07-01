### Gráfico 2: Base Wikipedia 
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
