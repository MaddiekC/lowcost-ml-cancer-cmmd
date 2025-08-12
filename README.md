# lowcost-ml-cancer-cmmd

**Proyecto:** EVALUACIÓN COMPARATIVA DE MODELOS DE APRENDIZAJE AUTOMÁTICO DE BAJO COSTO PARA DIAGNÓSTICO DE CÉLULAS CANCEROSAS  
**Dataset:**  Dataset CMMD | The chinnese Mamografy database 

Otros Repositorios 
- https://github.com/MaddiekC/lowcost-ml-cancer-nsclc.git
- https://github.com/DilanT123/lowcost-ml-cancer-padufes20.git
- https://github.com/DilanT123/lowcost-ml-cancer-cnn-extratrees.git
  
## ✨ Características Principales

*   **Análisis Exploratorio de Datos (EDA):** Visualizaciones y resúmenes estadísticos para entender la distribución y las relaciones en los datos.
*   **Pipeline de Preprocesamiento Robusto:** Manejo avanzado de valores faltantes, codificación de variables categóricas y escalado de características.
*   **Extracción de Características de Imágenes:** Implementación de descriptores de textura (GLCM, LBP), forma y estadísticos para cuantificar la información de las mamografías.
*   **Selección de Características:** Múltiples técnicas (ANOVA, RFE, Basada en Importancia) para identificar los predictores más relevantes y reducir la dimensionalidad.
*   **Entrenamiento y Optimización de Modelos:** Búsqueda de hiperparámetros para 7 modelos de clasificación diferentes, incluyendo XGBoost, SVM y Extra Trees.
*   **Ensemble Learning:** Creación de modelos de ensamble (Voting, Stacking) para mejorar la precisión y la generalidad del modelo final.
*   **Evaluación Exhaustiva:** Métricas detalladas, matrices de confusión y análisis de generalización para seleccionar el mejor modelo.

## 📂 Estructura del Repositorio

```
lowcost-ml-cancer-cmmd/
│
├── data/                  # Carpeta para los datos (no incluida en el repo)
│   ├── CMMD_clinicaldata_revision.xlsx
│   └── metadata.csv
│
├── graficos/              # Gráficos generados durante el análisis
├── modelos/               # Modelos entrenados y guardados
├── resultados/            # Resultados intermedios y finales (archivos .pkl y .json)
│
├── 01_lowcost_ml_cancer_cmmd.ipynb  # Notebook principal con todo el pipeline
├── config.yaml            # Archivo de configuración centralizado
└── README.md              # Este archivo
```

## 🚀 Cómo Empezar

### Prerrequisitos

Asegúrate de tener Python 3.8+ instalado. Puedes instalar todas las dependencias necesarias ejecutando:

```bash
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn plotly pydicom pyyaml xgboost
```

### Configuración

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/MaddiekC/lowcost-ml-cancer-cmmd.git
    cd lowcost-ml-cancer-cmmd
    ```

2.  **Descarga los datos:**
    Descarga el dataset CMMD y colócalo en la carpeta `data/` siguiendo la estructura mencionada arriba.

3.  **Configura el pipeline:**
    Abre el archivo `config.yaml` para ajustar las rutas de los ficheros, los parámetros del modelo y las etapas del pipeline que deseas ejecutar.

### Ejecución

Puedes ejecutar el pipeline completo abriendo y corriendo el notebook `01_lowcost_ml_cancer_cmmd.ipynb` en un entorno como Jupyter Lab o Google Colab.

## 📈 Resultados

El modelo final seleccionado fue un **Ensemble (Voting Classifier )**, que demostró un rendimiento robusto y una excelente capacidad de generalización en el conjunto de prueba.

| Métrica             | Valor         |
| ------------------- | ------------- |
| **Mejor Modelo**    | `voting_soft` |
| **F1-Score (Test)** | 0.8131        |
| **Accuracy (Test)** | 0.8293        |
| **AUC-ROC (Test)**  | 0.6981        |

El análisis demostró que la combinación de múltiples modelos a través de un ensamble mejora la estabilidad y el rendimiento predictivo en comparación con los modelos individuales.

## 🛠️ Pasos Futuros

*   **Validación Externa:** Probar el modelo final en un dataset de mamografías completamente diferente para verificar su robustez.
*   **Optimización de Inferencia:** Convertir el modelo a un formato más eficiente como ONNX para acelerar las predicciones en un entorno de producción.
*   **Reentrenamiento Periódico:** Implementar un flujo de trabajo para reentrenar el modelo a medida que se disponga de nuevos datos.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si tienes alguna idea para mejorar el proyecto, por favor abre un "issue" para discutirlo o envía directamente un "pull request".

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
