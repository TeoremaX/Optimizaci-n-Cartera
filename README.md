# Optimización de Cartera: Análisis Cuantitativo y Simulación

Este proyecto implementa un flujo completo de optimización de carteras basado en la teoría de Markowitz, incluyendo restricciones realistas, backtesting y simulaciones de Monte Carlo. Está diseñado para ser reproducible, modular y transparente, con foco en análisis financiero cuantitativo avanzado.

---

## 🛠 Entorno y Paquetes Necesarios

El proyecto utiliza librerías de Python para procesamiento, análisis y visualización de datos financieros históricos:

- **yfinance**: descarga de datos históricos de mercado.
- **pandas**, **numpy**: manipulación de datos tabulares y cálculos numéricos.
- **scipy**, **scikit-learn**: optimización y técnicas de machine learning.
- **matplotlib**, **seaborn**: visualización de resultados.
- **statsmodels**, **arch**: modelado de series temporales y volatilidad condicional (GARCH).
- **joblib**: almacenamiento y recuperación de objetos pesados (modelos, matrices, resultados).

> Se recomienda instalar todas las dependencias antes de ejecutar el proyecto para asegurar reproducibilidad:

```bash
pip install -r requirements.txt
