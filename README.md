# AlaBeam — Predicción ML de vigas 2D a partir de MEF

AlaBeam es una aplicación con interfaz gráfica (GUI) desarrollada en Streamlit para predecir el comportamiento de vigas a partir de los parámetros que introduce el usuario: longitud, tipo de sección, material, cargas y condiciones de contorno (apoyo simple o empotrado). AlaBeam emplea dos modelos de regresión entrenados con datos generados mediante simulaciones FEM/MEF: una Red Neuronal (Keras) y un HistGradientBoostingRegressor (HGBR) de scikit‑learn. La app estima tensión máxima y desplazamiento máximo, aplicando el mismo preprocesado de features usado en el entrenamiento para garantizar coherencia en las predicciones.

## Contenidos

- Script base de interfac gráfica de Alabeam
- Modelos entrenados HGBR y Red Neuronal
- Fichero de configuración
- Requisitos de instalación

## 📁 Estructura del Proyecto

```bash
├── alabeam.py                                  # Script base de toda la app en Streamlit
├── preprocessing.py                            # Rasgos físico-informados, escalas y limpieza
├── models
│   ├── model_max_displacement_logHGB.joblib    # Modelo HGBR para el target de desplazamientos
│   └── model_max_stress_logHGB.joblib          # Modelo HGBR para el target de tensión        
├── models_neural
│   ├── model_max_displacement_neuralnet.keras  # Modelo Red Neuronal para el target de desplazamientos
│   ├── model_max_stress_neuralnet.keras        # Modelo Red Neuronal para el target de tensión
│   ├── scaler_displacement_neuralnet.joblib    # Scaler Red Neuronal para el target de desplazamientos
│   └── scaler_stress_neuralnet.joblib          # Scaler Red Neuronal para el target de desplazamientos
├── config.py                                   # Constantes compartidas (secciones, apoyos, K, etc.)
└── requirements.txt                            # Dependencias de Python
```

Creado por Daniel López López - https://www.linkedin.com/in/daniel-lopez-lopez1313/
