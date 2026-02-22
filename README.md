# Optimizacion-Cartera
## Entorno y paquetes necesarios

Este proyecto utiliza librerías de Python para descargar, procesar, analizar y visualizar datos financieros históricos:

- **yfinance**: descarga de datos históricos de mercado.
- **pandas** y **numpy**: manejo de datos tabulares y cálculos numéricos.
- **scipy** y **scikit-learn**: optimización y técnicas de machine learning.
- **matplotlib** y **seaborn**: visualización de resultados.
- **statsmodels** y **arch**: modelado de series temporales y volatilidad condicional (GARCH).
- **joblib**: almacenamiento y recuperación de objetos pesados (modelos, matrices, resultados).

**Nota:** Se recomienda ejecutar la instalación antes de iniciar el proyecto para asegurar que todas las dependencias estén presentes.

## Estructura de Carpetas del Proyecto

El proyecto sigue una estructura organizada para asegurar reproducibilidad y claridad:

ProyectoCartera/
│
├── data/
│ ├── raw/ <- Datos crudos descargados de yfinance
│ └── processed/ <- Datos limpios, transformados y listas para análisis
│
├── outputs/ <- Gráficos, reportes y resultados finales
└── notebooks/ <- Notebooks de análisis y backtesting

## Universo de Activos y Periodo de Estudio

Para este proyecto se seleccionaron 17 activos representativos de diferentes clases:

- **ETFs de acciones**: SPY, QQQ, IWM, EEM  
- **ETFs de bonos**: TLT, IEF, AGG  
- **Oro**: GLD  
- **Acciones mega-cap**: AAPL, MSFT, GOOG, AMZN, NVDA  

**Periodo de estudio:** del 1 de enero de 2015 al 21 de septiembre de 2025.

Los datos crudos se guardan en la carpeta `data/raw` para asegurar reproducibilidad.
