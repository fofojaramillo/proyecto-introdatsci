# proyecto-introdatsci
> Repositorio del proyecto final del primer módulo de Introducción a la Ciencia de Datos.

## MODELOS PARA CLASIFICACIÓN DE VINOS (METODOLOGÍA CRISP-DM)

<div style="background-color: #f0f0f0; padding: 5px;">
  <h2>Objetivos de la linea de investigación</h2>
</div>

> Proyecto para la materia de Introducción a la ciencia de datos y sus metodologías, se enfoca en la clasificación de la calidad de vinos tintos.

Estos vinos exhiben una serie de características distintivas como:

* acidez fija
* acidez volátil 
* ácido cítrico 
* azúcar residual 
* cloruros, 
* dióxido de azufre libre
* dióxido de azufre total, 
* densidad
* pH
* sulfatos
* grados de alcohol
* calidad, que se utilizará como variable clasificatoria.

El proyecto seguirá la metodología CRISP-DM, abordando las siguientes etapas: 

- Comprensión del negocio (definición de objetivos de investigación, evaluación de la situación actual y definición de objetivos de minería de datos, planificación del proyecto)
- Comprensión de los datos (recolección inicial de datos, descripción de datos, exploración de datos y verificación de la calidad de los datos)
- Preparación de datos
- Modelado
- Evaluación.

En la fase de evaluación, se empleará la técnica de validación cruzada K-Fold para estimar el rendimiento predictivo del modelo. Además, se compararán y evaluarán algoritmos de clasificación, como las Máquinas de Soporte Vectorial (SVM) y el análisis discriminante, con el fin de determinar el modelo óptimo. La clasificación de los datos en conjuntos de entrenamiento, prueba y validación será considerada para garantizar la robustez del modelo.


<div style="background-color: #f0f0f0; padding: 5px;">
  <h2>Preparación de los datos</h2>
</div>

> Dentro del contexto de nuestro proyecto de clasificación de vinos tintos, la preparación de datos es una fase fundamental que abarca diversas tareas esenciales.

> La preparación de datos desempeña un papel crítico en el éxito de nuestro proyecto de clasificación de vinos tintos, ya que garantiza que nuestros datos estén listos y en las mejores condiciones para ser utilizados en la construcción y entrenamiento de modelos de clasificación de calidad.

### Selección de datos

Hemos optado por trabajar con una base de datos de vinos tintos que cuenta con diversas características, como se mencionó previamente. De esta muestra, seleccionaremos las siguientes variables como atributos:

* fixed_acidity 
* volatile_acidity
* citric_acid
* residual_sugar
* chlorides
* free_sulfur_dioxide
* total_sulfur_dioxide
* density
* pH
* sulphates
* alcohol

Estas características se denominarán colectivamente como nuestra variable independiente "X" en todo el modelo. Asimismo, de la muestra, utilizaremos la siguiente variable como etiqueta de clase:

* quality

Esta etiqueta se referirá como nuestra variable dependiente "Y" en todo el modelo.

### Limpieza de datos

Los datos que emplearemos ya han sido sometidos a un proceso de limpieza desde su descarga. Se realizó una revisión exhaustiva para asegurar que no contuvieran datos corruptos y que todos los valores fueran adecuados para su uso en el modelo de clasificación.

### Contrucción de los datos

A partir de esta base de datos, hemos procedido a dividirla en tres grupos:

- Conjunto de Entrenamiento (80%): Este conjunto de datos se utilizará para entrenar el modelo.
- Conjunto de Prueba (10%): Una vez entrenado el modelo, utilizaremos este conjunto de datos para realizar pruebas.
- Conjunto de Validación (10%): Este conjunto se empleará como si fueran nuevos datos para evaluar nuestro modelo y verificar si produce los resultados deseados.

Es importante señalar que los porcentajes mencionados corresponden al número total de observaciones en la base de datos original.

Además, hemos tenido en cuenta que la columna "Quality" se utiliza como variable de clasificación, la cual abarca valores del 3 al 9. Esto asegura que respetamos las proporciones adecuadas para evitar sesgos en los resultados del modelo y lograr un entrenamiento correcto tanto del modelo como de los datos resultantes.


<div style="background-color: #f0f0f0; padding: 5px;">
  <h2>Modelado</h2>
</div>

### Contexto General:

En la fase de Modelado del proceso CRISP-DM, se busca construir modelos de aprendizaje automático que puedan predecir la variable objetivo (en este caso, la calidad del vino y su correcta clasificación con base a ciertas propiedades o caracteristicas).

### Preprocesamiento de Datos:

Previo a la construcción de los modelos, se realizó un preprocesamiento de datos. Se transformó la variable de clase quality en una variable binaria, donde se clasificó el vino como "malo" si su calidad estaba en el rango 3-6 y como "bueno" si estaba en el rango 6-9. Luego, se mapearon estas etiquetas a valores numéricos (0 para malo y 1 para bueno) para que los modelos pudieran procesarlos.

### Elección del Método k-fold:

Se optó por utilizar la validación cruzada k-fold para evaluar los modelos de manera robusta. Este método divide el conjunto de datos en k particiones, utiliza k-1 para entrenar y la restante para validar. Este proceso se repite k veces, y se calcula el promedio de las métricas de evaluación. El método k-fold ayuda a obtener estimaciones más confiables del rendimiento del modelo y a evitar sesgos.

### Selección de Modelos:

Se eligieron varios algoritmos de aprendizaje supervisado para el análisis de clasificación de vinos:

1. **Análisis Discriminante:** Seleccionado por su capacidad para encontrar combinaciones lineales de características que maximizan la separación entre clases.
2. **Naive Bayes:** Elegido por su simplicidad y eficacia, asumiendo independencia condicional entre las características.
3. **Support Vector Machine (SVM) con Kernel Polinomial:** Utilizado por su capacidad para manejar relaciones no lineales entre características.

### Justificación de la Elección de Modelos:

- **Análisis Discriminante (AD):** Apropiado para problemas de clasificación lineal, cumple con los requisitos del problema y es conocido por su rendimiento en problemas similares.

- **Naive Bayes (NB):** Efectivo en situaciones donde las características son independientes, y su simplicidad facilita la interpretación y el entrenamiento rápido.

- **SVM con Kernel Polinomial:** Capaz de manejar relaciones no lineales, lo cual puede ser crucial en problemas más complejos de clasificación.

### Plan de Prueba (Validación Cruzada k-fold):

Se implementó la validación cruzada k-fold con 10 particiones y 5 repeticiones para evaluar los modelos. Esto garantiza que cada modelo sea evaluado en múltiples conjuntos de datos y proporciona una estimación robusta de su rendimiento.

### Construcción del Modelo:

Se utilizó código en Python, aprovechando las bibliotecas como scikit-learn para implementar los modelos y la validación cruzada, y seaborn y matplotlib para visualizar los resultados.

### Evaluación del Modelo:

La evaluación del modelo se basó en métricas como la precisión (accuracy). Las métricas fueron promediadas sobre las repeticiones y los pliegues de la validación cruzada para obtener estimaciones más confiables.

### Criterios para la Elección de Técnicas de Modelado:

La elección de las técnicas se basó en criterios clave:

* **Apropiación al Problema:** Los algoritmos seleccionados son adecuados para problemas de clasificación.
* **Datos Adecuados:** Se verificó que los datos fueran suficientes y adecuados para la construcción de modelos.
* **Cumplimiento de Requisitos:** Los modelos seleccionados cumplen con los requisitos específicos del problema.
* **Tiempo Adecuado:** Se consideró el tiempo necesario para obtener un modelo efectivo.
* **Conocimiento de la Técnica:** Se optó por algoritmos bien comprendidos y utilizados en problemas similares que se investigaron de los cuales hicieron uso de ellos con buenos resultados, además de evaluar si realmente este se adaptaba al resultado del objetivo.
* **Resultados y Visualización:**
Los resultados fueron visualizados mediante gráficos de barras que muestran la asertividad promedio de cada modelo en la clasificación de vinos buenos y malos utilizando el metodo K-Fold.

### Conclusión de la fase de Modelación:

La elección de técnicas y modelos se basó en una cuidadosa consideración de los requisitos y características específicas del problema, así como en la utilización de prácticas de validación cruzada para obtener estimaciones confiables del rendimiento del modelo.
