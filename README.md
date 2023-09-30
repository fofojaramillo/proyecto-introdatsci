
# Proyecto de Introducción a la Ciencia de Datos

## MODELOS PARA CLASIFICACIÓN DE VINOS (METODOLOGÍA CRISP-DM)

<div style="background-color: #f0f0f0; padding: 5px;">
  <h2>Objetivos de la linea de investigación</h2>
</div>

> Proyecto para la materia de Introducción a la ciencia de datos y sus metodologías, se enfoca en la clasificación de la calidad de vinos tintos.

Autores:

Luis Ernesto Ortiz Villalón

Rodolfo Armando Jaramillo Ruiz

Mario Estrada Ferreira

Luis Andrés Burruel Durán

El proyecto seguirá la metodología CRISP-DM, abordando las siguientes etapas: 

- Comprensión del negocio (definición de objetivos de investigación, evaluación de la situación actual y definición de objetivos de minería de datos, planificación del proyecto)
- Comprensión de los datos (recolección inicial de datos, descripción de datos, exploración de datos y verificación de la calidad de los datos)
- Preparación de datos
- Modelado
- Evaluación.

En la fase de evaluación, se empleará la técnica de validación cruzada K-Fold para estimar el rendimiento predictivo del modelo. Además, se compararán y evaluarán algoritmos de clasificación, como las Máquinas de Soporte Vectorial (SVM) y el análisis discriminante, con el fin de determinar el modelo óptimo. La clasificación de los datos en conjuntos de entrenamiento, prueba y validación será considerada para garantizar la robustez del modelo.

### Comprensión del negocio

Con foco en la industria vitivinícola y su interés en mejorar la calidad de sus productos. La base de datos proporciona una rica colección de datos numéricos relacionados con diversas propiedades químicas y físicas de los vinos, incluyendo características como acidez fija, acidez volátil, contenido de azúcar residual, concentración de cloruros, y otros parámetros. El objetivo fundamental es utilizar estos datos para desarrollar un modelo predictivo que pueda evaluar y predecir la calidad del vino, representada por la variable objetivo "quality", que se expresa en valores enteros.

Este modelo de predicción es de gran valor para la industria vinícola, ya que permitirá a las bodegas y productores evaluar la calidad de sus vinos de manera más eficiente y precisa. Al comprender cómo las diferentes propiedades químicas y físicas influyen en la calidad percibida del vino, las empresas pueden tomar decisiones más informadas sobre cómo ajustar sus procesos de producción para mejorar sus productos y satisfacer las preferencias de los consumidores. Además, este modelo también puede ser útil para identificar tendencias y patrones en la producción de vinos con el tiempo, lo que podría conducir a innovaciones en la elaboración de vinos y estrategias de comercialización más efectivas. En resumen, la comprensión del negocio se enfoca en el objetivo de mejorar la calidad del vino a través de un análisis integral de los datos disponibles y la creación de un modelo predictivo sólido.

#### Valoración de la situación actual

El vino es una de las bebidas alcoholicas más consumidas alrededor del mundo. Debido a su popularidad, anualmente se producen más de 230 millones de hectalitros alrededor del mundo. El mercado global de esta bebida en 2021 estuvo evaluado en aproximadamente 340.23 mil millones de dolares, y se espera que este valor ascienda a 456.76 millones de dólares con una tasa de crecimiento anual compuesta del 4.3%.

Esta bebida además resulta ser bastante compleja, y por ende ha sido clasificada de distintas formas por sus diversas cualidades. Algunas de las características que influyen en la calidad del vino son el cuerpo, esto es, la intensidad de color y la densidad, su dulzor, su acidez, y los grados de alcohol. Ante esto, son muchos los factores que necesitan ser controlados para obtener ciertas características en esta bebida, por ejemplo, la especie de uva a utilizar, la selección de las mismas uvas, posibles plagas de la vid, factores ambientales y orgánicos en el proceso de fermentación, entre otros.
 
A nivel industrial, la producción del vino involucra muchos gastos. Podemos mencionar, por ejemplo, máquinas como desgranadoras, prensas, molinos e incluso embotelladoras, las cuales además de tener cierto costo, necesitan otro tipo de recursos para funcionar y mantenimiento. Otros gastos incluyen personal, control sobre distintos factores en la producción del vino e incluso el transporte.


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
### Descripción de los datos

El dataframe consta de 11 variables numéricas continuas que describen propiedades químicas del vino, y una variable target "wine_quality", la cual es una variable categórica ordinal con 7 valores disponibles (los números del 3 al 9). Procedemos a describir algunas de las variables involucradas en esta base de datos.

#### 'fixed_acids'

Estos también son llamados ácidos no volátiles, y son aquellos que no pueden ser respirados por los pulmones.

#### 'Volatile acidity'

Es una medida de cantidad de ácidos grasos de bajo peso en el vino, y por lo general es percibido como el olor del vinagre.

#### 'citric_acid'

Es añadido al vino de forma artificial para incrementar la acidez, complementar algún sabor y prevenir la creación de suspensiones ferricas.

#### 'residual_sugar'

Azucar que proviene de restos de la uva natural después del proceso de fermentación.

#### 'chlorides'

Influido por el suelo, clima, la varidad de la uva, y otros factores, es de gran importancia tener en cuenta los cloruros, ya que le da al vino un sabor salado indeseado.

#### 'free_sulfur_dioxide'

El dióxido de azufre es utilizado como conservador primario del vino. Actúa como antioxidante y antimicrobiano.

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

### Criterios para la Elección de Técnicas de Modelado:

La elección de las técnicas se basó en criterios clave:

* **Apropiación al Problema:** Los algoritmos seleccionados son adecuados para problemas de clasificación.
* **Datos Adecuados:** Se verificó que los datos fueran suficientes y adecuados para la construcción de modelos.
* **Cumplimiento de Requisitos:** Los modelos seleccionados cumplen con los requisitos específicos del problema.
* **Tiempo Adecuado:** Se consideró el tiempo necesario para obtener un modelo efectivo.
* **Conocimiento de la Técnica:** Se optó por algoritmos bien comprendidos y utilizados en problemas similares que se investigaron de los cuales hicieron uso de ellos con buenos resultados, además de evaluar si realmente este se adaptaba al resultado del objetivo.
* **Resultados y Visualización:**
Los resultados fueron visualizados mediante gráficos de barras que muestran la asertividad promedio de cada modelo en la clasificación de vinos buenos y malos utilizando el metodo K-Fold.

### Evaluación del Modelo:

La evaluación del modelo se basó en métricas como la precisión (accuracy). Las métricas fueron promediadas sobre las repeticiones y los pliegues de la validación cruzada para obtener estimaciones más confiables.

### Conclusión de la fase de Modelación:

La elección de técnicas y modelos se basó en una cuidadosa consideración de los requisitos y características específicas del problema, así como en la utilización de prácticas de validación cruzada para obtener estimaciones confiables del rendimiento del modelo.

### Implantación

La validación de los modelos se hizo utilizando un set de datos de validación que no fueron utilizados en el proceso de aprendizaje. Se usaron datos completos (de los que se conoce el valor 'quality' real), el modelo genera una predicción para la variable calidad, y se compara con el valor real. 
La calificación resultante es el 'acurracy score', que expresa de manera porcentual el número de predicciones correctas. 

El modelo que mejor desempeño tuvo es el 'Análisis discriminante', el cuál hizo una predicción correcta el 81% de las veces. 

Cualquier interesado en conocer la calidad específica de un vino del cuál conoce todas sus carácterísticas necesarias para el modelo, puede, con cierta certeza, saber si el vino es bueno o malo: Un consumidor puede descubrir lo propio de una marca desconocida, un productor que sabe cómo afecta un cambio en la cadena de producción a cierta carácterística específica puede predecir la calidad antes de hacer dichos cambios etc. 

La implementación del modelo con fines de desarrollo comercial van más allá del alcance de éste proyecto. Vale la pena agregar que 'Calidad' puede ser una variable bastante subjetiva, que no necesariamente representa sabor, o valor comercial. Es por eso que resulta clara la necesidad de un experto en la materia para extraer el mayor valor de los modelos. 
