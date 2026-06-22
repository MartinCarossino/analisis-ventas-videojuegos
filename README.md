# Análisis de Ventas Globales de Videojuegos

Análisis exploratorio y de negocio sobre ventas históricas de videojuegos (1980–2016), usando Pandas, Matplotlib y Seaborn. Proyecto enfocado en limpieza de datos, manipulación con `groupby`/`agg`, y visualización estadística — sin modelado predictivo.

## Objetivo

Responder preguntas de negocio sobre la industria de los videojuegos: qué géneros y plataformas dominaron históricamente, cómo varían las ventas según la región, cómo evolucionó el mercado a través de las décadas, y qué estrategias de catálogo distinguen a los publishers más exitosos.

## Dataset

- **Fuente:** [Video Game Sales — Kaggle (gregorut/videogamesales)](https://www.kaggle.com/datasets/gregorut/videogamesales)
- **Tamaño:** 16.598 registros originales (16.327 tras limpieza), 11 columnas
- **Cobertura:** juegos lanzados entre 1980 y 2016, con datos de ventas por región (Norteamérica, Europa, Japón, Otros) y ventas globales

## Proceso

1. **Carga de datos:** lectura del CSV directo desde este repositorio.
2. **Limpieza:** tratamiento diferenciado de valores nulos — eliminación de filas sin año (no existe un valor sustituto razonable) y etiquetado de publishers faltantes como "Desconocido" (para no perder el resto de la información de esas filas). Corrección de tipos de datos y verificación de duplicados.
3. **Análisis exploratorio (EDA):** distribución de juegos por género, análisis de la fuerte asimetría en ventas globales (incluyendo visualización en escala logarítmica), y detección de outliers con boxplot.
4. **Preguntas de negocio:** ventas totales por género, dominancia de plataformas por región, evolución temporal del mercado, y comparación de estrategias de catálogo entre los principales publishers usando `groupby().agg()`.
5. **Interpretación crítica:** contraste entre cantidad de títulos publicados y ventas reales, identificación de limitaciones del dataset (cobertura incompleta en años recientes).

## Principales hallazgos

- Las ventas por juego están extremadamente sesgadas: la mitad de los juegos vende menos de 170.000 copias, mientras que el más exitoso (Wii Sports) vendió 82.74 millones — casi 500 veces más.
- Shooter es un género con relativamente pocos títulos publicados pero un desempeño comercial desproporcionadamente alto, a diferencia de géneros con mucho volumen pero ventas moderadas (como Misc o Adventure).
- Existe un marcado patrón regional: las plataformas de Microsoft prácticamente no tuvieron mercado en Japón, mientras que las plataformas de Nintendo y Sony mantuvieron una presencia japonesa mucho más fuerte.
- Nintendo se distingue del resto de los principales publishers por una estrategia de "menos juegos, mucho más exitosos en promedio" — vende, en promedio, entre 3 y 9 veces más por título que sus competidores directos.
- El pico histórico de ventas de la industria (según este dataset) ocurrió en 2008-2009. La caída observada después de 2016 refleja una limitación de cobertura del dataset, no un colapso real del mercado.

## Cómo reproducirlo

El notebook está pensado para correr de punta a punta en Google Colab sin configuración adicional:

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MartinCarossino/analisis-ventas-videojuegos/blob/main/notebook/analisis_ventas_videojuegos.ipynb)

## Tecnologías

- Python
- Pandas
- Matplotlib
- Seaborn

## Autor

Martín Carossino — [GitHub](https://github.com/MartinCarossino)
