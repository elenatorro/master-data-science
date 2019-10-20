# Introducción al Procesamiento del Lenguaje Natural

## Minería de Textos

Proceso de analizar colecciones de textos para descubrir información y patrones que no aparecen de forma explícita en los textos.

### Qué hace

* Extracción y recuperación de información
* Categorización y agrupamiento de documentos

### Cómo lo hace

* Se utilizan técnicas de **procesamiento del lenguaje natural** y de **aprendizaje automático**.
* Se aplica a **colecciones de documentos** con **información textual no estructurada** y escrita en **lenguaje natural**

## Información Textual

Documentos que pueden agruparse en colecciones o **corpus**. Pueden contener **anotaciones** y **metadatos**.

## Extracción de Información

Extraer automáticamente información estructurada a partir de textos.

Abarca procesos como:

* NER: Named Entity Recognition, o **reconocimiento** de nombre de entidades. 
* **Extracción** de terminología y de relaciones.
* Information Retrieval: **recuperación** de información.
  * Buscar documentos
  * Buscar información dentro de los documentos
  * Buscar información en los metadatos que describan los documentos
  * Buscar en distintas fuentes de datos

## Categorización de Documentos

**Asignar** a un documento una o más categorías definidas previamente en función de su contenido.

## Agrupamiento de Documentos
_Document Clustering_

Forma de organización de documentos en grupos en la que ni la naturaleza de los grupos, ni en ocasiones su número están definidos de antemano.

## Procesamiento del Lenguaje Natural
_(PLN ó NLP, Natural Languaje Processing)_

Rama de la informática cuyo objetivo es el desarrollo de sistemas que permitan a los ordenadores comunicarse con personas utilizando el lenguaje humano.

Se utiliza para adquirir conocimientos a partir de cantidades masivas de datos textuales

### Retos NLP

* Alta ambigüedad a todos los niveles: Léxico, Sintáctico, Semántico, de discursos
* Conocimiento del mundo (contexto, situación, jerga...)
* Interpretar correctamente:
    * **Negación:** al extraer la información es importante saber si un dato, concepto, relación etc. está siendo negado.
    * **Especulación:** Muchas veces se dice que “puede” darse un hecho.
    * **Correferencia:** es necesario identificar expresiones que hacen referencia a la misma entidad _(Aunque todos vieron al **Presidente**, ninguno reconoció al **ganador de las últimas elecciones**_)

### Evaluación de Tareas

* Es necesario **obtener** datos de evaluación de los modelos y sistemas para el avance del área.
* Es necesario **comparar** modelos y sistemas de formas justa:
    * Sobre los mismos datos: corpus o colecciones comunes
    * Usando las mismas medidas

### Corpus

Un corpus es una compilación de textos en formato electrónico.

Son un recurso fundamental en el desarrollo de aplicaciones basadas en PLN:
* Permiten **evaluar** los sistemas
* Proporcionan un **marco común** para comparar técnicas alternativas
* Permiten **entrenar** los sistemas de aprendizaje automático supervisados: ajustan sus parámetros a partir de una parte del corpus usada para entrenamiento.
* Proporcionan una muestra amplia y natural del lenguaje.
* Son una fuente de datos estadísticos sobre las palabras, sus relaciones y sus construcciones.

#### Aplicaciones

* Asignación automática de categorías léxicas
* Desambiguación sintáctica
* Extracción de gramáticas
* Traducción automática
* Extracción de entidades (nombres, medicamentos, etc.)
* Extracción de relaciones

#### Tipos generales

* **Sin anotar:** Texto puro
* **Anotados:** marcados con distintos tipos de información
lingüística (se les denomina Gold standard y se usan de referencia)
* **Monolingüe:** textos pertenecientes a una única lengua
* **Multilingüe:** textos en diversas lenguas. Proporcionan anotaciones similares en distintas lenguas
* **Paralelo:** contiene los mismos textos en más de una lengua
* **Comparable:** Contiene un número equilibrado de textos en distintas lenguas. También están equilibrados respecto al tema y tipo de textos

#### Ejemplos

---

* Corpus de Brown
    * [http://www.nltk.org/nltk_data](http://www.nltk.org/nltk_data)
    * Palabras anotadas (+1M)
    * Categorías léxicas
    * 87 Etiquetas

---

* Corpus de Susanne
    * [http://www.nltk.org/nltk_data](http://www.grsampson.net/Resources.html)
    * Palabras (+130K)
    * Subconjunto de 64 archivos del corpus de Brown
    * Anotado con categorías léxicas y análisis sintáctico
        * Por cada palabra de texto hay una línea de anotaciones (análisis sintáctico)

---

* Corpus ADE
    * [https://github.com/trunghlt/AdverseDrugReaction](https://github.com/trunghlt/AdverseDrugReaction)
    * Relaciones entre efectos adversos y medicamentos

---

* Corpus Bioscope:
    * [http://rgai.inf.u-szeged.hu/index.php?lang=en&page=bioscope](http://rgai.inf.u-szeged.hu/index.php?lang=en&page=bioscope)
    * Textos biomédicos anotados con negación y especulación

---

* Corpus DDI:
    * [https://omictools.com/ddi-corpus-tool](https://omictools.com/ddi-corpus-tool)
    * Anotación de medicamentos e interacciones entre ellos: _The DDI corpus: an annotated corpus with pharmacological substances and drug-drug interactions._

---

* Corpus Europarl:
    * [http://www.statmt.org/europarl/](http://www.statmt.org/europarl/)
    * Actas del parlamento europeo en 21 lenguas de Europa: Español, Inglés, Francés, Griego, ..., con alineamiento o correspondencia a nivel de oración)

---

* Corpus DIANN
    * [https://github.com/gildofabregat/DIANN-IBEREVAL-2018/tree/master/DIANN_CORPUS](https://github.com/gildofabregat/
DIANN-IBEREVAL- 2018/tree/master/DIANN_CORPUS)
    * Discapacidades anotadas

### Evaluación de Tareas

#### Campañas de evaluación

Proponen retos a los participantes, proporcionando datos y un marco de evaluación común y bien definido.
    * TREC: Text Retrieval conference
    * CLEF: Conference and Labs of the evaluation Forum
    * Semeval: Semantic Evaluation Ibereval: Lenguas Ibéricas

#### Medidas de Evaluación

**Precisión**: fracción de predicciones del modelo propuesto acertadas (coinciden con los datos de referencia)

```
precission = true positive / (true positive + false positive)
```

**Recall**: Cobertura o exhaustividad. Fracción de los datos de referencia que han sido propuestas por el modelo evaluado:

```
recall =
    true positive /
    (true positive + false negative)
```

**Medida-F:** media armónica de precisión y cobertura:

```
meassure_f =
    2 * precission * recall /
    (precission + recall)
```

**Medida-Fβ:** forma general de la media armónica que permite dar más importancia a la precisión o a la cobertura en función del parámetro β:

```
meassure_f_beta =
    ((1 + β^2) * precission * recall) /
    (β^2 * (precission + recall))
```

---

### Ejemplo

Tenemos:

* Número de datos totales: 16
* Número de datos del modelo: 13
* Número de datos que usa el modelo: 8  (true positive)
* Número de datos aportados: 11
* Falsos negativos: 11 - 8 = 3
* Falsos positivos: 13 - 8 = 5

Medidas:

* Precisión

```
 8 / 8 + 5 = 8 / 13
```

* Medida_F

```
8 / 8 + 3 = 8 / 11
```

### Herramientas

* Nltk: Natural Language Toolkit
    * Librería para desarrollar programas en python para procesar datos de lenguaje natural
    * [https://www.nltk.org/](https://www.nltk.org/)
    * Ejemplos de como iniciarlo, y algunas de las utilidades más básicas: [https://www.nltk.org/book/ch01.html](https://www.nltk.org/book/ch01.html)

* Spacy:
  * Librería para desarrollar programas en python para procesar datos de lenguaje natural
  * [https://spacy.io/](https://spacy.io/)
  * Tiene modelos preentrenados en Inglés y Español

### Procesos

* Normalización:
    * Unificar palabras que se refieren de distinta forma a la misma entidad

---

* Expresiones regulares:
    * Especificar patrones de texto

---

* Distancia de edición:
    * Número/coste de las operaciones de edición: Inserción, Borrado,  Sustitución
    * Necesarias para transformar una cadena en la otra.
    * Explorar todas las combinaciones de operación para seleccionar la de menor coste
    * Importante para medir la similitud entre dos cadenas
    * Se usan para corrección de errores ortográficos, extracción de información...

---

* Identificar palabras vacías:
    * Palabras sin significado propio: artículos, preposiciones, etc.
    * Suelen ser las más frecuentes en un idioma
    * En muchos procesos de PLN se eliminan para centrar el análisis en las palabras con contenido semántico

---

* Segmentación de cadenas:
    * Romper una cadena de caracteres (grafemas) en una secuencia de palabras.

---

* POS tagging
    * Part-Of-Speech Tagging: Etiquetar las palabras de una oración con su categoría léxica según su definición y el contexto de la oración
    * Cada palabra de una oración se puede clasificar en clases: verbos, adjetivos, nombres, etc
    * Útil para: Identificación de entidades, desambiguación del sentido de las palabras, análisis sintáctico...
    * Técnicas: Basados en reglas, modelo de probabilidades de las secuencias de palabras y sus etiquetas en función de los datos de un corpus anotado, aprendizaje automático.
    * Evaluación: 
        * Accuracy: número de etiquetas acertadas sobre el número total de palabras etiquetadas
        * Precisión, cobertura y medida-F para cada tipo de etiqueta del conjunto de etiquetas considerado

---

* Stemming
    * Análisis morfológico
    * El proceso de stemming se refiere al proceso de eliminar la parte final de las palabras, que en muchas ocasiones es una aproximación a la lematización.
    * Permite reconocer todas las palabras correspondiente a una misma raíz

---

* Chunking
    * Parte en trozos (chunks) y etiqueta secuencias multipalabra
    * NP-chunks suelen ser menores que las frases nominales: NP-chunks no contienen otros NP-chunks
    * Los sintagmas preposicionales o las cláusulas subordinadas que modifican un nominal no se suelen incluir.
    * Se puede construir una gramatica de detección de chunks usando expresiones regulares sobre las etiquetas POS. (pag. 265 libro nltk)
    * También puede construirse con clasificadores entrenados.

---

* Análisis Sintáctico: 
    * Identificar la estructura sintáctica de una oración.
    * La estructura asignada depende del tipo de gramática considerada.
    * Dificultad: ambigüedad estructural → una oración puede tener múltiples árboles de análisis respecto a una misma gramática

---

* Desambiguación del sentido de las palabras
    * Muchas palabras tiene más de un significado o sentido dependiendo del contexto en que se usan
    * Muchas aplicaciones requieren seleccionar el sentido correcto: Word Sense Disambiguation (WSD).

    * Relaciones entre sentidos:
        * Sinónimos: distintas palabras con el mismo (o muy similar) significado
        * Hipónimo: un sentido es hipónimo de otro si el primero es más específico (una subclase).
        * Hiperónimo: un sentido es hiperónimo de otro si el primero es más general (superclase)
    
    * Wordnet: una base de datos de relaciones léxicas

### Análisis morfolológico

* La morfología es el campo de la lingüística que estudia la estructura de las palabras
* Un morfema es la unidad lingüística más pequeña que tiene significado semántico
* El análisis morfológico es la tarea de segmentar una palabra en sus morfemas