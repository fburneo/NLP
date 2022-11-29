# *Gendered Pronoun Resolution* [PNL]

En el análisis de texto natural, existen oraciones complejas de entender incluso para las personas. Uno de los casos más conflictivos son los pronombres ambiguos. En 2018, se publicó un dataset junto con el paper [A Balanced Corpus of Gendered Ambiguous Pronouns](https://arxiv.org/pdf/1810.05201.pdf), donde se proponen un conjunto de textos con pronombres ambiguos con género.

El objetivo de este dataset es encontrar el nombre en el texto al que el pronombre ambiguo hace referencia.

Para ello se nos da un dataset con los siguientes campos:

* `ID`: Identificador de la frase.
* `Text`: Texto en fromato string.
* `Pronoun`: string con el pronombre ambiguo.
* `Pronoun-offset`: índice del carácter donde empieza el pronombre dentro del texto.
* `A`: string con el primer nombre candidato a hacer referencia por el pronombre.
* `A-offset`: índice del carácter donde empieza el nombre A dentro del texto.
* `A-coref`: boleano indicando si el pronombre hace referencia al nombre A.
* `B`: string con el segundo nombre candidato a hacer referencia por el pronombre.
* `B-offset`: índice del carácter donde empieza el nombre B dentro del texto.
* `B-coref`: boleano indicando si el pronombre hace referencia al nombre B.
* `URL`: web de donde se ha sacado el fragmento de texto.

El código tiene como objetivo la predicción de a cuál de los dos nombres marcados en cada frase hace referencia el pronombre seleccionado usando **dos modelos distintos** de PNL:

* **MODELO 1**: Puede ser **cualquier modelo visto en los seminarios de PLN o en otras asignaturas**, como: Count vectorizer, HMM, Structured Perceptron, RNN, Logistic Regressor, XGBoost, etc...

* **MODELO 2**: Debe ser un modelo **basado en Transformers** que incorpore el concepto de ***attention***.
