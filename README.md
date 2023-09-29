# Clasificación de vinos

### Comprensión del negocio

El objetivo es simular una situación donde se requiera trabajar con la base de datos Wine Quality, con el objetivo de obtener un modelo que prediga la calificación que tiene un vino en función de sus caracteristicas.

- [ ] Hacer analisis exploratorio de los datos
- [ ] Escoger un modelo para llegar a la variable objetivo a partir de las caracteristicas.
- [ ] Separar los datos en datos de entrenamiento, datos de prueba y datos de validación. La relación entre estos sera de 80/10/10.
- [ ] Analizar la validez del modelo usando k-fold.
- [ ] Repetir para un segundo modelos.
- [ ] Comparar resultados.

#### Determinar el objetivo del Data Mining (DM).

### Objetivos:
En éste proyecto usaremos las herramientas programáticas y metodologías de análisis de Data Mining para obtener información pública acerca de la clasificación de varios aspectos cualitativos de vinos de diferentes marcas, países, uvas, y regiones; limpiar y entender la información disponible; para después, buscar aplicar un algoritmo de Machine Learning (ML) que basado en la información descriptiva disponible, nos diga la calidad esperada del vino en cuestión. 

### Criterios de éxito:
El proyecto se considera un éxito cuando logremos ejecutar todas los objetivos descritos, programacionalmente; y que el resultado de nuestro set de test para nuestro algoritmo de predicción sea de >85%. 

### Plan del proyecto
El proyecto sigue los siguientes pasos.

- [ ] Comprensión del negocio
- [ ] Comprensión de los datos
- [ ] Preparación de los datos
- [ ] Modelado
- [ ] Evaluación

### Comprensión de los datos

Con la base de datos, hay que describir los tipos de variable que existe para los registros, que tipo de datos tiene. Finalizando con una exploración simple del cual sacar conclusiones sobre la conclusión de los datos.

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

### Preparación de los datos

Se decide que datos son relevantes para el modelado, se obtienen variables nuevas de ser necesario. 
