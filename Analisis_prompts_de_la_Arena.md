> ![](media/image1.jpeg)
>
> Análisis de prompts de la Arena
>
> Hackathon 2025
>
> Constanza Jeldres García
>
> Trabajo final de prácticas de lingüista computacional en Somos NLP



#  Introducción

En el marco del Hackathon SomosNLP 2025, se planteó un reto centrado en la creación de un *dataset de preferencias* mediante prompts que evalúan la adecuación cultural en distintos países de Latinoamérica y la Península Ibérica. El objetivo principal fue identificar y recoger las respuestas generadas por distintos modelos de lenguaje (LLMs) frente a indicaciones culturalmente sensibles, comparándolas en una plataforma colaborativa (“LLM Arena”).

Este desafío surge del reconocimiento de que los modelos de lenguaje modernos suelen estar sesgados hacia perspectivas dominantes -a menudo angloparlantes- y pueden no responder con pertinencia o conciencia cultural en contextos hispanohablantes. Por lo tanto, la iniciativa pretende impulsar una alineación más equitativa y contextualizada de los LLMs, mediante la recolección estructurada de prompts y respuestas que reflejen las particularidades culturales de cada país hispanohablante.

Este informe se estructura en varias secciones:

1.  **Metodología**, donde se detalla el proceso de diseño de prompts y generación del dataset, además de la metodología y herramientas utilizadas para el análisis.

2.  **Análisis**, en el que se examinan los resultados, patrones culturales, respuestas destacadas y evaluaciones cruzadas entre países.

3.  **Conclusiones**, donde se extraen aprendizajes clave y se propone orientación para futuras iteraciones o mejoras.

4.  **Limitaciones**, donde se abordan las restricciones de este informe.

Con esta estructura, se busca ofrecer una visión clara y profunda sobre el potencial y las barreras existentes al tratar de alinear LLMs con contextos culturales diversos dentro del mundo hispanohablante.

# Metodología

## 2.1 Diseño de los Prompts

El diseño de los prompts tuvo como objetivo principal generar instrucciones que permitieran evaluar la adecuación cultural, lingüística y pragmática de las respuestas producidas por distintos modelos de lenguaje de gran tamaño (LLMs) en contextos específicos de países hispanohablantes. Para ello, se definieron criterios que garantizaran la representatividad regional, la diversidad temática y la posibilidad de detectar diferencias sutiles en la producción lingüística de los modelos.

Los prompts se clasificaron en tres grandes categorías, adaptadas a las particularidades del español según país:

1.  **Evaluación y análisis**: prompts que solicitan identificar o explicar el significado, el uso o el registro de una expresión o construcción lingüística propia del país (ej. “¿Qué significa *irse al chancho* en Chile?”).

2.  **Generación lingüística**: instrucciones que requieren al modelo generar texto en un registro o variedad regional concreta, ya sea informal, coloquial o dialectal (ej. “Escribe un diálogo entre adolescentes en el español de Lima, Perú”).

3.  **Adecuación y corrección cultural**: tareas que ponen a prueba la capacidad del modelo para detectar errores o sugerir ajustes en función del contexto cultural del país en cuestión (ej. “¿Es apropiada esta expresión en una carta formal en España?”).

### 

### 2.1.1 Características generales exigidas para el diseño de los prompts

Para asegurar la utilidad del dataset en el proceso de alineación por preferencias y la evaluación de modelos multivariantes, los prompts debían cumplir con una serie de criterios definidos por la organización del hackathon. Estas características fueron clave para garantizar la calidad, comparabilidad y pertinencia cultural de las respuestas generadas. Las principales fueron:

- **Claridad y especificidad**: los prompts debían estar formulados de forma clara, evitando ambigüedades o instrucciones demasiado generales. Se privilegiaron tareas que dieran lugar a respuestas contrastables.

- **Formato instruccional**: cada prompt debía estar formulado como una instrucción explícita para el modelo, por ejemplo: *"Escribe...", "Corrige...", "Explica...", "Evalúa si..."*.

- **Sensibilidad cultural**: se priorizó que cada prompt reflejara aspectos culturales, lingüísticos o pragmáticos propios del país hispanohablante al que iba dirigido. Esto incluía expresiones idiomáticas locales, registros específicos, formas de tratamiento o referencias socioculturales.

- **Diversidad temática**: se fomentó la inclusión de una amplia gama de contextos (informales, formales, educativos, cotidianos, etc.) y dominios discursivos (literatura, redes sociales, trabajo, juventud, etc.).

- **Neutralidad política, religiosa y ética**: los prompts debían evitar reproducir sesgos sensibles o inducir a respuestas que pudieran resultar ofensivas o discriminatorias.

- **Compatibilidad con evaluación por preferencias**: los prompts debían permitir la comparación de dos o más respuestas generadas por modelos distintos, de modo que un evaluador pudiera elegir cuál de ellas se ajustaba mejor al contexto propuesto.

- **Longitud moderada**: se recomendó que los prompts no excedieran las 2 o 3 líneas, salvo cuando el contexto lo requiriera, para facilitar tanto la evaluación humana como el procesamiento automático.

Estas directrices se aplicaron de forma transversal en el diseño de los países contemplados, permitiendo una base común que a la vez respetara las particularidades de cada variedad del español.

### 

### 2.1.2 Diseño de prompts Equipo LeIA

En el contexto de la realización de las prácticas de lingüistas computacionales en SOMOS NLP, Susana Zhou y Constanza Jeldres formaron el equipo LeIA de la Hackathon SOMOS NLP 2025. Para ello, cada una diseñó más de 100 prompts de las variantes de español peninsular y español chileno, en las categorías de generación lingüística y adecuación y corrección cultural. Diseñando al menos 50 prompts para cada una de estas categorías. Los prompts abordaron una amplia gama de temas, desde modismos y expresiones idiomáticas hasta aspectos socioculturales como formas de cortesía, referencias locales y prácticas comunicativas típicas.

El proceso de creación fue manual, realizado por las lingüistas computacionales con experiencia en su correspondiente variación dialectal del español. Se consultaron fuentes académicas, corpus lingüísticos y observaciones empíricas del uso real de la lengua en redes sociales, medios y conversaciones informales.

### 

### 2.1.3 Preparación para evaluación en LLM Arena

A todos los prompts que fueron cargados en la plataforma LLM Arena, se les presentaron dos respuestas generadas por dos modelos elegidos aleatoriamente. El objetivo fue que evaluadores humanos eligieran cuál de las dos respuestas se ajustaba mejor a la consigna, permitiendo así recopilar datos de preferencia humana para procesos de fine-tuning como Direct Preference Optimization (DPO).

Este enfoque facilita la evaluación cultural de los modelos y contribuye a construir datasets multivariantes que integren la riqueza del español en sus múltiples variedades nacionales.

En la **imagen 1** que se muestra a continuación, se puede ver cómo funciona la plataforma: aquí ya se ha ingresado el prompt (que aparece en el recuadro rojo) y cada uno de los modelos ofrece una respuesta para este.

**Imagen 1**

![](media/image2.png)

## 2.2 Metodología del análisis

### 2.2.1 Observación general de los datos

Para realizar el análisis general del dataset, se utilizó una metodología cuantitativa, apoyada en herramientas de visualización, como tablas y gráficos, propias del análisis estadístico básico y del procesamiento textual. Todo esto con el objetivo de describir el conjunto de datos, considerando: distribución de prompts por país, longitud de los textos, complejidad y similitud semántica entre respuestas y clasificación temática de los prompts y sus respuestas.

Todo el análisis se realizó en Google Colab, con exportación automatizada de los resultados a Google Drive.

<span id="_Toc205559316" class="anchor"></span>**a) Herramientas y bibliotecas utilizadas** [Ver repositorio en github](https://github.com/somosnlp/llm-arena/blob/main/An%C3%A1lisis_general_arena.ipynb)

pandas para procesamiento de datos estructurados.

matplotlib y seaborn para la visualización gráfica.

scikit-learn para el cálculo de similitud textual mediante TF-IDF y similitud coseno.

transformers de Hugging Face para clasificación temática automatizada (zero-shot classification).

Google Drive (/MyDrive/graficos_dpo) como entorno de almacenamiento.

<span id="_Toc205559317" class="anchor"></span>**b) Procesamiento y análisis realizados**

1.  **Distribución de prompts por país:** se utilizó sns.countplot() para visualizar la cantidad de prompts por país. Esta visualización permitió detectar desequilibrios en la representación geográfica del dataset, lo que tiene implicaciones directas en el fine-tuning de modelos multivariantes.

2.  **Longitud media de textos por país:** se calcularon las longitudes medias de los textos (prompt, chosen, rejected) por país y se representaron mediante un gráfico de barras agrupadas. Esto me permitió observar patrones de complejidad y detalle según región.

3.  **Similitud semántica entre respuestas:** se aplicó TfidfVectorizer() sobre cada par (chosen, rejected) y se calculó la similitud coseno con cosine_similarity(). Los resultados se visualizaron con un boxplot por país. Este análisis evidenció qué tan diferenciadas eran las respuestas generadas por los modelos, lo cual es crucial para evaluar la utilidad del dataset en alineación por preferencias.

4.  **Clasificación temática automatizada:** se implementó un pipeline de clasificación por cero disparos (zero-shot classification) usando el modelo facebook/bart-large-mnli de la biblioteca transformers. Este modelo permite asignar etiquetas temáticas sin entrenamiento específico, comparando cada texto contra una lista de categorías definidas: cultura, sociedad, lengua, historia, estereotipos, opinión y políticas públicas. Clasificando automáticamente tres tipos de textos: prompts (question), respuestas elegidas (chosen), respuestas rechazadas (rejected). Los resultados se almacenaron en un nuevo archivo CSV, que permitió realizar análisis posteriores.

5.  **Visualización de temas frecuentes por país:** se creó un gráfico de barras horizontal con la frecuencia total de cada tema, sumando las etiquetas de prompts, respuestas elegidas y rechazadas y se generaron mapas de calor (heatmaps) por país y por tipo de texto usando sns.heatmap() para observar qué temas predominan en cada región y cómo varían según el tipo de contenido.

<span id="_Toc205559318" class="anchor"></span>**c) Resultados y propósitos**

Esta metodología permitió: 1) detectar desequilibrios y patrones en la distribución geográfica y temática del dataset, 2) establecer diferencias claras entre países en términos de complejidad de prompts y estilo de respuestas, 3) analizar la coherencia y diferenciación entre respuestas generadas por los modelos, condición clave para tareas de preferencia humana (como DPO) y 4) obtener una categorización temática sistemática que facilita el análisis lingüístico posterior y aporta trazabilidad al proceso de generación de datos.

De esta forma, el enfoque adoptado equilibra la capacidad de reproducir la técnica adoptada y la interpretación lingüística y sienta las bases para el posterior análisis centrado en la variación estilística, adecuación cultural y preferencias humanas.

###  2.2.2 Mirada desde la lingüística computacional

El análisis lingüístico realizado sobre las respuestas generadas por modelos de lenguaje se ha estructurado en torno a dos ejes principales: la caracterización gramatical y discursiva. Para ello, se han empleado técnicas de procesamiento del lenguaje natural (PLN) que permiten cuantificar y visualizar patrones a partir de atributos lingüísticos extraídos automáticamente.

<span id="_Toc205559320" class="anchor"></span>**a) Herramientas y bibliotecas utilizadas** [Ver repositorio en Github](https://github.com/somosnlp/llm-arena/blob/main/Analisis_Linguistico_Arena.ipynb)

spaCy (es_core_news_sm) para el análisis morfosintáctico del español, incluyendo tokenización, segmentación, etiquetado POS y análisis de dependencias.

Transformers (Hugging Face) para clasificación automática de estilos discursivos y temas, usando modelos como facebook/bart-large-mnli.

Pandas y NumPy para la manipulación y análisis de datos estructurados.

Matplotlib y Seaborn para visualizar los datos con paletas accesibles para personas daltónicas.

Google Drive (/MyDrive/graficos_dpo) como entorno de almacenamiento.

Google Colab para la ejecución reproducible del análisis.

<span id="_Toc205559321" class="anchor"></span>**b) Procesamiento y análisis realizados**

1.  **Análisis morfosintáctico con spaCy:** se utilizó este modelo para realizar el etiquetado gramatical y de dependencias de las respuestas, realizando tokenización y segmentación de oraciones, extracción de formas verbales para identificar:

- Tiempo verbal (presente, pasado, futuro, imperfecto).

- Persona gramatical (1ª, 2ª y 3ª).

- Registro formal/informal a partir del uso de la 2ª persona (tú/usted).

Este procesamiento permitió construir nuevas bases de datos clasificadas por país y tipo de respuestas (elegidas vs rechazadas), facilitando el análisis cualitativo comparado.

1.  **Categorización del estilo discursivo:** mediante la clasificación automática, cada respuesta fue etiquetada con un estilo discursivo dominante, el cual podía ser:

- Descriptivo

- Narrativo

- Informal

- Formal

- Otro

Esto permitió analizar la distribución global de estilos en respuestas elegidas y rechazadas, la frecuencia de estilos por país y la frecuencia de cambio de estilo entre las respuestas elegidas y rechazadas para un mismo prompt, revelando patrones de preferencia por ciertas estructuras discursivas.

1.  **Métricas de longitud y conectividad:** se calcularon métricas como longitud media de oraciones (en caracteres), por país y tipo de respuesta y el promedio de conectores discursivos por país, como indicativo de coherencia y cohesión textual. Estas métricas fueron visualizadas mediante gráficos de barras y diagramas de cajas, y su comparación ayudó a detectar diferencias estilísticas y de complejidad entre respuestas aceptadas y rechazadas.

2.  **Visualización e interpretación:** se generaron múltiples visualizaciones con Matplotlib y Seaborn, todas adaptadas para ser visibles para personas con daltonismo (colorblind-friedly palettes). Además, los gráficos fueron sistemáticamente guardados en una carpeta organizada en Google Drive (graficos_dpo), favoreciendo la trazabilidad y reproducibilidad del análisis.

<span id="_Toc205559322" class="anchor"></span>**c) Resultados y propósitos**

Esta metodología permitió: 1) Evaluar patrones lingüísticos que influyen en la preferencia por parte del modelo o del evaluador humano, como mayor cohesión, longitud, registro o claridad. 2) Detectar sesgos estilísticos o culturales en la producción de respuestas por país. 3) Ofrecer criterios objetivos para la alineación por preferencias**,** evaluando cómo la elección de estilo, tono o estructura se correlaciona con la aceptación o el rechazo. 4) Establecer una base para tareas posteriores de fine-tuning o auditoría lingüística, mediante el análisis comparativo de estructuras lingüísticas.

#  Análisis

## 3.1 Análisis general 

Los prompts que se suben a la Arena están constantemente en aumento, por lo que es importante remarcar que este análisis se realizó sobre el [dataset-preferencias-v0](https://huggingface.co/datasets/somosnlp-hackathon-2025/dataset-preferencias-v0) con los datos recopilados hasta el 28 de mayo de 2025.

### a) Prompts por país

El conjunto total contiene **686 prompts**, distribuidos entre **7 países hispanohablantes**:  
**Chile, España, México, Colombia, Nicaragua, Perú y Paraguay.** Esta diversidad geográfica permite explorar una amplia gama de variedades del español, incluyendo usos culturales y registros comunicativos locales (ver gráfica 1).

**Gráfica 1**

![](media/image3.png)

Con más de 240 prompts, España concentra más de un tercio del total del dataset. Esto sugiere que, si el modelo aprende patrones del dataset, puede estar más influenciado por formas idiomáticas, pragmáticas y estilos discursivos del español peninsular**,** lo cual es relevante para evaluar sesgos por país**.** Por otro lado, América Latina está representada de forma desigual; Colombia (177 prompts) y Chile (93) son los países latinoamericanos con mayor número de entradas, seguidos por Perú (68) y Paraguay (65). México, a pesar de ser uno de los países hispanohablantes con mayor población, tiene solo unos 6 prompts, lo cual desequilibra su representación. Nicaragua aparece con 30 prompts. Esto refuerza la necesidad de ampliar el corpus para países centroamericanos y del Caribe si se busca un modelo regionalmente balanceado.

### b) El dataset y sus implicaciones para la evaluación y el fine- tuning

Cualquier evaluación comparativa de desempeño por país debe considerar este desequilibrio de datos, ya que los resultados podrían estar sesgados a favor de los países más representados. También podría impactar la detección de expresiones idiomáticas, estilos formales/informales o construcciones gramaticales preferidas.

Debido a que en el fine-tuning el modelo ajusta sus parámetros basándose en los ejemplos disponibles, los sesgos del actual dataset darían como resultado un aprendizaje sesgado hacia las variedades del español más representadas. Por lo tanto, si hay muchas más muestras de España que de México o Nicaragua, el modelo aprenderá con mayor fuerza las estructuras sintácticas más frecuentes en España (por ejemplo, uso del pretérito perfecto frente al indefinido), los modismos y expresiones idiomáticas propias del español peninsular, patrones de registro, cortesía y estilo más comunes en esa variedad. Y esto puede llevar a que prefiera respuestas más apropiadas para España, aunque el prompt provenga de otro país, genere textos que no suenen naturales para hablantes de otras variedades (p. ej., uso de "vosotros", "vale", "chaval"), y que sea menos preciso al identificar o generar expresiones coloquiales o pragmáticas específicas de los países menos representados.

En tareas como clasificación de formalidad, identificación de modismos o generación de respuestas, el desequilibrio puede resultar en mayor precisión para los países con más datos (España y Colombia).

Todo esto deriva en una evaluación injusta, pues durante la evaluación posterior del modelo, si no se controla este desbalance, se corre el riesgo de concluir que el modelo funciona “bien” cuando en realidad sólo está funcionando bien para los países dominantes en el corpus**.**

### c) Estructura de los prompts

Con respecto a la longitud de los prompts, el promedio es de aproximadamente 102 caracteres, lo que indica que la mayoría de las instrucciones son breves y directas, alineadas con el formato recomendado en el instructivo del Hackathon para evaluación de LLMs. El prompt más largo tiene 683 caracteres y pertenece a México. Se trata de una instrucción detallada para interpretar términos del argot del narcotráfico mexicano, mientras que el prompt más corto consta de sólo 7 caracteres (considerando el espacio)**,** este corresponde a España y dice simplemente “La mona”. Lo interesante de este caso es que ese prompt aparece dos veces y en ambos los modelos fueron capaces de interpretar esa simple instrucción como una referencia a la fábula del autor Tomás Iriarte, del siglo XVIII. Pese a lo breve de la instrucción, los modelos reconocieron la referencia y generaron respuestas culturalmente contextualizadas. Incluso fueron capaces de adaptar la moraleja a contextos actuales como las redes sociales, la superficialidad y la autenticidad. Este ejemplo demuestra que los modelos son capaces de activar conocimiento cultural complejo a partir de estímulos mínimos. También pone de relieve el reto de evaluar prompts muy cortos: su interpretación depende completamente del contexto inferido y no de la información explícita.

### d) Longitud de prompts por país

|  | País | Número de prompts | Longitud media | Longitud mínima | Longitud máxima |
|:---|:---|:---|:---|:---|:---|
| 1 | Chile | 93 | 193,98 | 12 | 327 |
| 2 | Colombia | 177 | 109,86 | 20 | 310 |
| 3 | España | 247 | 56,44 | 7 | 148 |
| 4 | México | 6 | 547 | 25 | 683 |
| 5 | Nicaragua | 30 | 84,73 | 42 | 197 |
| 6 | Paraguay | 65 | 52,77 | 14 | 228 |
| 7 | Perú | 68 | 140,56 | 60 | 206 |

Si nos vamos al detalle, podemos ver esta tabla comparativa en la que se muestra la longitud media de los prompts por país; aquí se ven diferencias significativas que pueden darnos pistas sobre el nivel de complejidad, detalle y tipo de tarea que se planteó para cada variedad dialectal.

Aquí podemos ver que:

**México** es con diferencia el país con la longitud media más alta de 547 caracteres. Esto refleja prompts muy detallados, probablemente con instrucciones complejas o dominio especializado (como vimos en el análisis del argot del narcotráfico). Además, sugiere una intención de evaluación profunda o técnica, más que simplemente idiomática.

**Chile** tiene la segunda longitud media más alta, con 194 caracteres. Aquí los prompts tienden a incluir contexto situacional o instrucciones amplias, lo que puede enriquecer la evaluación, pero también requiere más procesamiento por parte del modelo. Posiblemente refleja un enfoque comunicativo más pragmático y contextualizado.

**Colombia y Nicaragua** tienen prompts de longitud media de 110 y 85 caracteres, respectivamente. No son ni tan cortos ni tan extensos dentro del contexto del dataset. Esto podría reflejar una estrategia de prompts instruccionales simples, pero no minimalistas, posiblemente con un enfoque más directo o conversacional.

**España**, en tanto, tiene una longitud media de 56 caracteres, la más baja por lejos. Con prompts tan breves como “la mona” o “un, dos, tres”. Probablemente dentro de este grupo se incorporan muchos ejemplos de activación cultural breve o expresiones idiomáticas que no requieren un contexto extenso. Esta economía exige atención, pues, si bien puede ser una estrategia útil para testear inferencias, también puede generar ambigüedad o variabilidad en la evaluación de preferencias.

Países con prompts más largos (como México y Chile) probablemente favorecen tareas de mayor complejidad semántica y contextual, útiles para entrenar modelos más robustos. Mientras que países con prompts breves (como España) pueden ser eficaces para evaluar conocimiento y fluidez, pero requieren una curación cuidadosa para evitar respuestas demasiado abiertas o inconsistentes.

### e) Similitudes semánticas entre respuestas

El siguiente diagrama de caja (gráfica 2) representa la similitud semántica (medida como similitud coseno, entre 0 y 1) entre las respuestas elegidas (“chosen”) y rechazadas (“rejected”) para cada país:

**Gráfica 2**

![](media/image4.png)

Esta figura permite visualizar la distribución de datos numéricos de manera compacta. De esta forma, la caja representa el 50% central de los datos (rango intercuartílico), es decir, donde se concentran la mayoría de las similitudes. La línea horizontal dentro de la caja indica la mediana (valor medio de la distribución). Las líneas que se extienden desde los bordes de la caja hasta el valor más lejano que no es considerado atípico se llaman “bigotes”. Los puntos individuales fuera de los bigotes son los outliers: respuestas que fueron mucho más similares o diferentes de lo esperado.

En este caso, Colombia y Nicaragua presentan la mayor similitud: la mediana en ambos está cerca de 0,6, y el 50% central de las similitudes se mantiene en un rango elevado. Esto indica que las respuestas “chosen” y “rejected” generadas a partir de los prompts de estos países son semánticamente parecidas**,** lo que sugiere diferencias más sutiles en estilo o enfoque que en contenido. Esto puede implicar una mayor dificultad para evaluar por preferencia**,** ya que ambas respuestas son razonablemente válidas.

España muestra una amplia variabilidad, aunque su mediana es alta (~0,57), se observan numerosos outliers con similitudes muy bajas y muy altas**.** Esto refleja el uso frecuente de prompts breves o ambiguos, que pueden dar lugar tanto a interpretaciones muy distintas como a respuestas casi idénticas. La dispersión sugiere inestabilidad en la diversidad de respuestas**,** lo que puede ser un reto para la evaluación humana y para el entrenamiento fino por preferencias.

Chile y Perú muestran patrones intermedios. Las medianas rondan el 0,5, con distribuciones relativamente simétricas. En Chile, esto parece vinculado al uso de prompts de longitud media a larga, que generan respuestas variadas pero comparables. En Perú, la presencia de outliers hacia valores bajos indica que algunos pares de respuestas fueron muy distintos entre sí, quizás por prompts abiertos o de carácter cultural específico.

México presenta las respuestas más diferentes entre sí; la mediana es muy baja (~0,18), y los valores están concentrados en un rango estrecho. Esto coincide con el hecho de que los prompts mexicanos en el dataset son más extensos y específicos (longitud media: 547 caracteres), lo que genera respuestas con estructuras y contenidos más distintos entre modelos. Es el país donde, con más probabilidad, los evaluadores encontraron diferencias claras entre opciones.

Paraguay se sitúa en la media, pero con alta dispersión. Aunque el número de prompts es menor, se observa una distribución amplia, lo que sugiere que la naturaleza de los prompts varía significativamente en complejidad o especificidad.

Esta gráfica confirma que la longitud, especificidad y contexto cultural de los prompts influyen directamente en la similitud de las respuestas generadas**,** y por tanto en la calidad del proceso de alineación por preferencias. Prompts largos y contextuales (como los de México) favorecen la diferenciación entre respuestas, mientras que prompts breves o vagos (como algunos en España) pueden conducir a ambigüedad o redundancia en la generación, lo que complica el entrenamiento y la evaluación.

### f) Temas frecuentes por país

Otra parte fundamental del análisis general del dataset consistió en clasificar los prompts según sus temáticas predominantes, para eso se usó una clasificación semisupervisada, mediante un pipeline de clasificación de texto por cero disparos (zero-shot classification) con el modelo facebook/bart-large-mnli a través de la biblioteca transformers. Inicialmente se había optado por una clasificación no supervisada basada en la técnica TF-IDF y NMF, pero los resultados obtenidos no fueron satisfactorios.

La ventaja de este modelo (facebook/bart-large-mnli) es que permite asignar etiquetas temáticas, sin requerir un entrenamiento previo sobre un etiquetado manual. Se definieron siete categorías principales, seleccionadas por su relevancia sociolingüística y cultural. Estas son: cultura, sociedad, lengua, historia, estereotipos, opinión y políticas públicas.

Cada entrada dentro del dataset se clasificó por separado en tres partes: prompt; correspondiente a la instrucción dada al modelo, respuesta elegida (chosen); la preferida por los evaluadores humanos y respuesta descartada (rejected); la respuesta descartada por los evaluadores.

El modelo facebook/bart-large-mnli fue seleccionado por su capacidad comprobada para realizar tareas de clasificación en varios idiomas mediante inferencia textual. Aunque no está entrenado específicamente en español, su rendimiento en tareas multilingües lo hace apto para este tipo de análisis temático a gran escala, especialmente cuando se usan etiquetas generales y bien diferenciadas.

El proceso se aplicó a más de 600 entradas y los resultados se almacenaron en un archivo CSV. A partir de éste, se generó el gráfico de barras y el mapa de calor (heatmap) que se muestra a continuación (gráfica 3):

**Gráfica 3**

![](media/image5.png)

Este gráfico de barras muestra la frecuencia total de temas en el dataset. Aquí se aprecia un fuerte enfoque en los aspectos sociales y culturales. **Estereotipos** destacan como la categoría dominante. Esto sugiere que muchas instrucciones buscan evaluar si los modelos detectan y reproducen prejuicios y sesgos culturales. **Cultura, lengua y sociedad** juntas representan gran parte del conjunto del dataset, muy en línea con el objetivo del hackathon de explorar la variación lingüística, cortesía, referencias locales y usos sociales de las distintas variantes del castellano. Historia y opinión están presentes en una menor proporción, aportando prompts centrados en contextualización local y evaluación de creencias.

Ejemplos de prompts por temática:

**Estereotipo:** /[Chile/] Imagina que has vivido toda tu vida en Las Condes. Comparando a una persona que vive en Las Condes a otra que vive en La Pintana, ¿qué diferencias notas en su forma de hablar o expresarse?

**Cultura:** /[España/] Eres un agricultor de olivos en Jaén, ¿qué es para ti el olivo en tu vida y en tu entorno?

**Lengua:** /[Colombia/] Si tuvieras que explicar el concepto de "berraquera" a un extranjero, ¿cómo lo harías?

**Sociedad:** /[Nicaragua/] ¿Qué es lo más común para desayunar en un domingo nicaragüense?

**Opinión:** /[Perú/] En las provincias se juega mucho al fútbol, pero los equipos de Lima tienen más visibilidad. ¿Qué opinas?

**Historia:** /[España/] Imagina que eres un profesor en Ceuta. ¿Cómo hablarías a tus alumnos sobre la historia multicultural de la ciudad?

**Políticas Públicas:** /[Paraguay/] ¿Qué feriados tendría en diciembre?

La verificación de la clasificación automática de los temas de los prompts se realizó mediante una revisión cualitativa manual. En la cual se revisó de forma aleatoria una muestra de los prompts y la temática asignada para ver si esta designación tenía sentido semántico. ¿Qué se observaba aquí? a) Si el tema reflejaba el contenido principal del prompt. b) si había ambigüedad o múltiples temas posibles y c) si había errores sistemáticos en la asignación de temas.

### g) Distribución temática por país

El mapa de calor (gráfica 4) permite observar la diversidad temática en relación con las variedades regionales del español, en él se refleja detalladamente la proporción de prompts por país y categoría:

**Gráfica 4**

![](media/image6.png)

**España** tiene una amplia cobertura temática, pensemos también que es el país que cuenta con la mayor cantidad de datos, aun así, hay un énfasis en lengua, cultura y opinión. El marcado liderazgo en la temática de lengua podría sugerir un interés por evaluar la norma y la variación dialectal.

**Colombia** se distribuye con cierta homogeneidad entre cultura, sociedad e historia. Esto muestra una transversalidad entre los contenidos culturales y sociales.

**Chile** y **Perú** muestran una clara tendencia hacia la categoría de los estereotipos. Tal vez esto refleje una estrategia centrada en la detección de sesgos culturales y pruebas de adecuación cultural, es decir, medir la sensibilidad pragmática y sociolingüística del modelo.

**México** no tiene presencia en casi ninguna categoría, aunque sus prompts tienden a ser más de estereotipos y lengua.

**Paraguay** y **Nicaragua** aportan variedad, especialmente en *historia* y *políticas públicas*, aunque en volúmenes más reducidos.

## 3.2 Análisis lingüístico 

El dataset construido presenta un potencial significativo para alinear modelos de lenguaje con preferencias culturales específicas. Sin embargo, para aprovechar plenamente esta capacidad, es necesario ir más allá del análisis cuantitativo general e incorporar un enfoque lingüístico más profundo.

En particular, el estudio de los estilos discursivos, los usos pragmáticos, la formalidad y la adecuación cultural de las respuestas generadas permite comprender qué respuesta fue preferida y por qué. Esta dimensión es crucial para entrenar modelos más sensibles a la variación contextual, al registro y a las normas comunicativas propias de cada país hispanohablante.

### a) Análisis comparativo de la longitud y cohesión discursiva en las respuestas elegidas y rechazadas por país

Aunque por sí sola la longitud no es determinante al hablar de la calidad de las respuestas, sí puede ofrecer pistas sobre el estilo comunicativo preferido en el alineamiento humano.

**Gráfica 5**

![](media/image7.png)

Por ejemplo, la longitud de las respuestas muestra diferencias significativas entre países en cuanto a las preferencias estilísticas observadas en las respuestas elegidas frente a las rechazadas. **México** destaca por presentar la mayor diferencia entre respuestas elegidas y rechazadas, con una media de más de 160 caracteres para las respuestas elegidas. Esto sugiere una preferencia por desarrollos más extensos. Sin embargo, también presenta la varianza más elevada, lo que indica una mayor heterogeneidad estilística y menor consistencia en los criterios de selección. **Colombia** presenta un patrón similar, con respuestas elegidas que son levemente más largas, lo que, nuevamente, podría reflejar una preferencia por desarrollos más completos o bien estructurados.

En contraste, **Chile**, **España** y **Nicaragua** muestran diferencias más estables entre ambas categorías. A diferencia de México, en estos países, las respuestas rechazadas tienden a ser ligeramente más largas que las elegidas, lo que sugiere que **la longitud no garantiza la aceptación** y que otros factores como la claridad o la pertinencia comunicativa podrían haber jugado un rol más importante. Esta misma hipótesis se ve reforzada por los casos de **Paraguay y Perú**, países que presentan longitudes similares en ambas categorías. Esto sugiere que la elección de respuestas no depende exclusivamente de la extensión, sino de otros factores como registro, claridad o adecuación cultural.

Estas tendencias se reflejan también en la dispersión de las respuestas; **México y Colombia** presentan las mayores desviaciones estándar, especialmente en las respuestas elegidas. Esto podría reflejar una menor homogeneidad en el estilo de escritura del modelo o en los criterios de evaluación humana. En cambio, **Chile, España** y **Nicaragua** muestran distribuciones más compactas, lo que sugiere una mayor consistencia en la longitud de las respuestas. Sin embargo, se observa un ligero desplazamiento hacia arriba en las respuestas rechazadas, lo que apunta nuevamente a que una mayor longitud no implicó automáticamente una mejor valoración. Por su parte, **Paraguay** y **Perú** se caracterizan por respuestas más breves y una dispersión menor, en línea con una posible preferencia por respuestas claras, concisas y culturalmente ajustadas.

A partir de estos patrones, la hipótesis lingüística que se propone para explicar la relación entre longitud y aceptación de una respuesta es que ésta podría estar mediada por el registro discursivo y la cohesión textual. Las respuestas más extensas tienden a incluir **conectores discursivos** -tales como *además*, *por lo tanto*, *sin embargo*, entre otros- que aportan fluidez, coherencia y una mayor percepción de naturalidad y estructura. Esto se vuelve especialmente relevante en contextos donde se valora la **argumentación o la ejemplificación**, y podría explicar por qué en países como México o Nicaragua las respuestas elegidas tienden a estar más desarrolladas. En cambio, en contextos como el paraguayo, puede haber primado el **valor de la concisión**, con preferencia por respuestas breves pero pragmáticas, directas y funcionales.

Con el fin de profundizar en este aspecto, se aisló el uso de **conectores discursivos por país y tipo de respuesta**, como indicador indirecto de cohesión textual y adecuación del registro. Estos conectores, que en español incluyen adverbios, conjunciones, interjecciones y locuciones del tipo *de hecho*, *en cambio*, *por consiguiente*, actúan como **marcadores discursivos clave** en la organización textual. Su frecuencia y diversidad pueden ofrecer una pista importante sobre la **calidad percibida de las respuestas**, así como sobre las expectativas culturales respecto al estilo conversacional o argumentativo.

### b) Los conectores y la cohesión discursiva

En el siguiente gráfico (gráfica 6) se muestran los países que participaron en la generación de prompts, junto a las respuestas elegidas (chosen) y rechazadas (rejected) diferenciadas por color. Las barras indican el promedio de conectores para ese tipo de respuesta y país.

**Gráfica 6**

![](media/image8.jpg)

Aislar el uso de los conectores revela información acerca del nivel de cohesión discursiva, ya que los conectores son un marcador lingüístico importante que aporta naturalidad y fluidez a los textos; además, un mayor número puede indicar una respuesta más estructurada. Por otra parte, si las respuestas elegidas tienen sistemáticamente más conectores que las respuestas rechazadas, podrían reflejar una preferencia del evaluador (o del criterio de selección) por respuestas más desarrolladas discursivamente.

En esta gráfica se ve que consistentemente las respuestas elegidas presentan un promedio mayor de conectores discursivos en todos los países analizados. Esto sugiere que la presencia de conectores puede haber influido positivamente en la percepción de calidad, fluidez o naturalidad de las respuestas. **México** lidera en el uso de conectores, alcanzando los tres conectores por respuesta. Esto se alinea con los hallazgos previos que indican una preferencia por respuestas más elaboradas y extensas, posiblemente con un estilo más argumentativo o explicativo.

**Colombia** y **España** también muestran un uso elevado de conectores por respuestas elegidas. En el extremo inferior, **Chile** y **Nicaragua** presentan los promedios más bajos tanto de respuestas elegidas como de rechazadas. Esto puede interpretarse como una preferencia cultural o contextual por la concisión o la comunicación directa, donde los conectores no son tan determinantes en la evaluación. Las diferencias entre respuestas elegidas y rechazadas son más marcadas en países como **México, España y Paraguay**, lo que podría indicar que la presencia de conectores funciona como un indicador de calidad.

### c) Registro comunicativo y proximidad interpersonal

La selección de usos de la primera, segunda y tercera personas al comunicarnos puede revelar aspectos del registro, tono comunicativo, proximidad interpersonal y estilo argumentativo. Por ello, es importante observar aquí cuáles son los usos que los evaluadores de los modelos han preferido en los diferentes contextos culturales (ver gráfica 7).

**Gráfica 7**

![](media/image9.png)

El mapa de calor (gráfica 7) muestra que la tercera persona es por lejos la más utilizada en todos los países, lo que sugiere una preferencia por estructuras informativas o expositivas. Se prefiere sobre todo la impersonalidad.

En países como Paraguay y Chile, hay una presencia importante del uso de la primera persona, lo que podría indicar un tono más experiencial en las respuestas. En todos los países, el uso de la segunda persona es menos frecuente. Esto indica que pocas respuestas adoptan un tono apelativo o conversacional hacia un interlocutor.

Este análisis sirve para entender cómo los modelos tienden a estructurar las respuestas en función de los distintos estilos discursivos, posiblemente influenciados por el país de origen del prompt y de cómo podría alinearse o no con las preferencias culturales o los estilos comunicativos locales.

El mapa de calor que aparece a continuación (gráfica 8) muestra en detalle la frecuencia de uso de la persona gramatical por país:

### 

### d) Tiempos verbales en las variantes del español 

**Gráfica 8**

![](media/image10.png)

El gráfico de calor representa el porcentaje de aparición de cuatro tiempos verbales (futuro, pretérito imperfecto, pasado -pretérito perfecto simple o compuesto- y presente) en las respuestas generadas por los modelos (*chosen* y *rejected*) según país. La intensidad del color indica el volumen de ocurrencias.

Principales observaciones:

En todos los países hay un uso mayoritario del tiempo presente. Esto refleja un estilo más bien impersonal o atemporal, tal vez alineado con prácticas discursivas neutras.

España destaca en el uso del pretérito imperfecto y el pasado; esto puede estar vinculado a prompts de narrativas históricas, relatos o contrastes entre situaciones pasadas y presentes. Por el contrario, Perú y Nicaragua muestran un uso bajo de esos tiempos verbales.

En todos los países hay escasa presencia del uso del futuro, por lo que sigue siendo el tiempo verbal minoritario. Tal vez se deba a que los modelos se centran más en análisis y descripción que en predicción.

Aunque México, Nicaragua, Paraguay y Perú presentan un menor volumen total de datos, igualmente muestran un patrón con una clara preferencia por el presente.

Interpretación lingüística:

Desde la perspectiva pragmática, el presente tiende a asociarse con un tono que transmite objetividad, o que es atemporal, muy frecuente para tareas que exigen respuestas generales o definiciones.

El pretérito imperfecto y el pasado aportan un valor narrativo, útil en ejemplos, comparaciones o evocaciones de contexto.

El futuro, al estar más ausente, podría estar asociado a respuestas con bajo nivel de aceptación o a escasos prompts formulados en este tiempo verbal.

En cuanto a la distribución porcentual de tiempos verbales por persona gramatical, el gráfico de calor (gráfica 9) muestra cómo se distribuyen los tiempos verbales (presente, pasado, pretérito imperfecto y futuro) en función de la persona gramatical (1ª, 2ª y 3ª persona), tomando como base los porcentajes dentro de cada persona. Se puede ver que hay un predominio absoluto del tiempo presente, el cual es el tiempo más utilizado en todas las personas gramaticales. Posiblemente muchos prompts y respuestas se enmarcan en descripciones, opiniones, afirmaciones generales o instrucciones, típicamente formuladas en presente.

El pasado se usa ligeramente más en la 3ª y 1ª personas (6,8% y 6,4% respectivamente) que en la 2ª (1,6%). Esto podría indicar que las narraciones personales o de terceros aparecen ocasionalmente en las respuestas, pero rara vez dirigidas directamente al interlocutor. El pretérito imperfecto predomina más en la 3ª persona (7,8%), lo que puede asociarse a explicaciones o relatos de contexto con carácter descriptivo o habitual. En la 2ª persona este tiempo verbal es prácticamente inexistente (0,3%). Aquí se ve un ejemplo de uno de los prompts: “Has vivido toda tu vida en Providencia, muy cerca del Costanera Center”.

El futuro tiene una presencia muy baja en general, pero está más presente en la 1ª persona (5,2%), lo que podría reflejar su uso en declaraciones de intención o proyecciones.

**Gráfica 9**

![](media/image11.png)

### **e) Registro de tono por país**

Una vez que se ha hecho el desglose de los usos de las personas gramaticales, es posible ver los registros formales e informales en el caso de la segunda persona gramatical formal (usted) e informal (tú).

El gráfico de barras (gráfica 10) apiladas representa la proporción en la que se emplean los registros formales e informales en las respuestas generadas por los modelos, desglosadas por país. Aquí se puede ver que hay un predominio evidente del registro formal en todos los países, lo que sugiere que los modelos tienden a adoptar un tono más cortés o respetuoso en su interacción con el usuario, alineado con normas de asistencia general.

Perú mantiene la tendencia hacia el uso formal de los demás países, aunque es el que tiene la proporción más alta de uso de formas informales (14,7%).

Los resultados de la gráfica sugieren que los modelos tienden a generalizar el uso del “usted” en la segunda persona, por lo que tal vez sería apropiado tener en consideración este sesgo, con el fin de crear nuevos prompts de entrenamiento específicos para el uso del “tú” y el “usted” según las distintas variantes dialectales.

**Gráfica 10**

![](media/image12.png)

### 

### f) Estilos discursivos

¿El español utilizado en cada país tiende a ser más formal, narrativo o descriptivo? ¿Hay algún estilo discursivo que prime por sobre otro en todos los países? La siguiente gráfica (gráfica 11) permite comparar cómo se distribuyen estilos discursivos en las respuestas elegidas y rechazadas a nivel global, independientemente del país de origen del prompt. Los cinco estilos discursivos definidos en este análisis son: narrativo, formal, informal, descriptivo y opinativo.

**Gráfica 11**

![](media/image13.png)

Aquí se puede ver que el estilo predilecto de los evaluadores es **el descriptivo**, preferido con mayor frecuencia en las respuestas elegidas, aunque también es el estilo predominante en las respuestas rechazadas. Esto sugiere que, aunque es el estilo predominante, esto no es garantía de que hayan escogido esas respuestas meramente por sus cualidades descriptivas, como desarrollar una idea con claridad y estructura. De hecho, el protagonismo del estilo descriptivo tanto en las respuestas escogidas como en las rechazadas sugiere que la preferencia debe depender de otros factores.

El **estilo narrativo** es el segundo más común en ambos tipos de respuestas. En este caso, además, es mayor el número de respuestas de estilo narrativo elegidas que las rechazadas, por lo que tal vez este estilo esté más alineado con las expectativas del evaluador.

El **estilo informal** es notoriamente apreciado al momento de la evaluación, por ello hay más respuestas elegidas que rechazadas en esta categoría. Lo que sugiere que los evaluadores califican positivamente los textos de tono coloquial o que muestran un mayor grado de cercanía, probablemente porque mejora la naturalidad de la respuesta, sobre todo en los prompts que exigen cercanía o tono conversacional.

La presencia de respuestas de **estilo formal** es bastante menor al resto de los otros estilos y esta categoría destaca por tener proporcionalmente el mayor número de respuestas rechazadas. Esto, tal vez, tiene que ver con una adecuación estilística, donde un tono demasiado técnico o formal choca con las preferencias deseadas, donde quizá se espera una respuesta más cercana.

Dentro de la categoría “otro” se agrupan todas aquellas respuestas que no se ajustan claramente a ninguna de las categorías principales.

Reflexión lingüística:

Este análisis sugiere que **el estilo discursivo es un factor lingüístico relevante** en la evaluación de las respuestas, pero su impacto depende del contexto y de las expectativas pragmáticas del prompt. El uso del estilo informal y narrativo aparece como una señal positiva en términos de preferencia, mientras que el estilo excesivamente formal podría resultar contraproducente.

### g) Análisis de los estilos discursivos por país

Observar la elección de estilos discursivos según el país de origen del prompt permite inferir diferencias culturales o de estrategia del dataset (ver gráfica 12).

España y Chile destacan por la **variedad estilística**: Chile tiene un uso equilibrado de los estilos descriptivo, informal y narrativo. España muestra un uso alto del estilo descriptivo, pero también presenta muchas respuestas de estilo narrativo.

El **estilo narrativo** tiene una presencia importante en casi todos los países, lo que podría indicar una valoración hacia respuestas subjetivas o experienciales.

Colombia, al igual que España, también muestra preferencia por el **estilo descriptivo**. Esto es coherente con una tendencia hacia respuestas más informativas y estructuradas.

En países como Chile, Colombia y Perú, el **estilo informal** aparece con frecuencia moderada, lo que podría estar relacionado con el uso de expresiones coloquiales o registros conversacionales aceptados como válidos por el modelo y los evaluadores.

El **registro formal** es el menos frecuente e incluso nulo en países como México, Nicaragua y Paraguay.

**Gráfica 12**

![](media/image14.png)

En el caso de las respuestas rechazadas, la tendencia se mantiene, aunque llama la atención el aumento de respuestas de estilo formal en España y Perú; esto podría indicar que respuestas demasiado formales o técnicas no necesariamente son valoradas como mejores. En contraste, el estilo informal está menos presente en las respuestas rechazadas que en las escogidas, lo que puede ser un indicador de que en muchos casos la informalidad fue valorada al momento de la selección de la respuesta.

Como ya se ha hecho mención en otras partes del análisis, países como México y Nicaragua presentan muy poca frecuencia en todos los estilos; esto se debe a la poca participación de estos países dentro del dataset o con respuestas más neutras, difíciles de categorizar estilísticamente.

Reflexión final:

Los patrones que muestran las gráficas sugieren que el estilo discursivo podría influir en la preferencia del modelo o del evaluador, aunque esta influencia no es homogénea en todos los países. La preferencia de los estilos descriptivos y narrativos se contrapone al rechazo de los estilos formales o poco desarrollados. Además, aparentemente el uso de un estilo informal favorece la elección de la respuesta, especialmente cuando no se contrapone a la claridad del contenido.

**Gráfica 13**

![](media/image15.png)

Para cerrar el análisis del estilo de las respuestas y el comportamiento al momento de la elección, el siguiente gráfico (gráfica 14) muestra la frecuencia de cambio de estilo entre la respuesta elegida y la respuesta rechazada:

**Gráfica 14**

![](media/image16.png)

Aquí se puede observar que España y Colombia son los países con más pares de respuestas. Además de eso, se ve que en ambos países predomina no cambiar el estilo al momento de elegir una respuesta. Aunque sobre todo en España, los casos con cambio de estilo existen y corresponden a una proporción importante del total de sus respuestas. Esto sugiere que, en ciertos casos, el cambio de estilo podría favorecer la selección de la respuesta.

Chile muestra una proporción muy equilibrada entre la selección de la respuesta con cambio de estilo y las sin cambio, sugiriendo que el estilo discursivo es un rasgo significativo al momento de optar por una respuesta u otra.

Perú es el único país que presenta más casos de respuesta seleccionada con cambio de estilo. Una señal de lo especialmente decisivo que fue para el evaluador de ese país el estilo discursivo.

# Conclusiones

El análisis general del dataset revela una alta variabilidad en la longitud, complejidad y estilo de los prompts según el país, lo que influye directamente en la diversidad y similitud de las respuestas generadas por los modelos. Las observaciones de los datos aportados por los prompts y sus respuestas en castellano han permitido demostrar el potencial de este recurso para la alineación de modelos de lenguaje con preferencias culturales y comunicativas propias de los países hispanohablantes.

En primer lugar, el estudio cuantitativo evidenció patrones de distribución y diferencias significativas entre países, tanto en la longitud de los prompts y respuestas como en la similitud entre pares de respuestas elegidas y rechazadas. Estos hallazgos muestran que, aunque existen regularidades globales, la preferencia por un tipo de respuesta está condicionada por factores culturales y pragmáticos.

En segundo lugar, el análisis lingüístico permitió profundizar en dimensiones discursivas y estilísticas que trascienden la mera extensión de los textos. Factores como el uso de conectores, la preferencia por determinadas personas gramaticales, la predominancia del tiempo presente y la elección de registros formales o informales mostraron variaciones relevantes según el país. Asimismo, se observó que los estilos descriptivo, narrativo e informal tienden a ser mejor valorados, mientras que el estilo excesivamente formal se asocia con mayor frecuencia a respuestas rechazadas. Estos resultados refuerzan la importancia de la adecuación cultural y estilística en la alineación de modelos.

En tercer lugar, la comparación entre respuestas elegidas y rechazadas reveló que la selección preferida no depende de un solo rasgo (como la longitud o la forma verbal), sino de una combinación de factores discursivos, pragmáticos y contextuales, que en conjunto determinan la percepción de naturalidad, claridad y pertinencia. Este hallazgo confirma la necesidad de diseñar datasets y evaluaciones que integren una mirada lingüística integral, más allá del conteo de palabras o la similitud semántica.

Finalmente, el trabajo pone en evidencia tanto las posibilidades como las limitaciones de este tipo de análisis. Entre las **principales limitaciones destacan el** **desbalance geográfico del corpus** **y la imposibilidad de integrar en esta versión fenómenos como el uso de modismos o estructuras sintácticas más complejas.** No obstante, estas limitaciones abren líneas de investigación futuras, orientadas a enriquecer el dataset con dimensiones pragmáticas y culturales más finas.

En suma, el presente análisis demuestra que el dataset constituye una base sólida para el entrenamiento y la evaluación de modelos más sensibles a la diversidad cultural del castellano, y que la integración de análisis lingüísticos profundos resulta indispensable para avanzar hacia LLMs mejor alineados con los usos, estilos y normas comunicativas de cada comunidad hispanohablante.

# Limitaciones

Este trabajo, aunque ofrece una primera aproximación sistemática al análisis de preferencias culturales en Large Language Models (LLMs) hispanohablantes, presenta algunas limitaciones que conviene señalar:

1.  **Desbalance geográfico del dataset:** la representación de países fue desigual, con predominio claro de España y Colombia, y escasa presencia de México y Nicaragua. Este desbalance puede inducir sesgos en los resultados y limitar la generalización de las conclusiones.

2.  **Heterogeneidad en la longitud y complejidad de los prompts:** mientras algunos países aportaron instrucciones breves y culturalmente cargadas (como por ejemplo España), otros generaron prompts largos y especializados (ej. México). Esta diferencia de diseño afecta la comparabilidad y puede condicionar la forma en que los modelos generan y diferencian sus respuestas.

3.  **Clasificación temática y estilística automática**: aunque en un principio la clasificación se hizo manual, por eficiencia se optó por la clasificación automática con base en modelos de zero-shot classification (facebook/bart-large-mnli), que permitió etiquetar los datos de manera rápida. Este enfoque, aunque es útil para agilizar el análisis, presenta limitaciones, pues tiende a cometer errores en casos ambiguos. Aquí no siempre reconoce expresiones idiomáticas propias del español y puede sobrepredicir categorías mayoritarias, invisibilizando estilos minoritarios. Asimismo, no capta matices pragmáticos como ironía, cortesía o atenuación.

4.  **Imposibilidad de integrar modismos y pragmática cultural**: aunque se intentó diseñar un clasificador de modismos mediante IA generativa (con instrucciones y ejemplos), las pruebas con distintos modelos fallaron en identificar de manera consistente expresiones locales o coloquiales en el dataset. Esto impidió observar en qué medida los modelos generan o comprenden modismos y si estos eran preferidos o rechazados en la curación.

5.  **Ausencia de análisis sintáctico profundo**: por limitaciones de tiempo no fue posible incluir métricas estructurales avanzadas, como el estudio de oraciones subordinadas, la frecuencia de oraciones interrogativas/exclamativas o la profundidad de los árboles sintácticos. Estas dimensiones habrían aportado un nivel adicional de detalle en la caracterización de los estilos discursivos.

6.  **Dependencia del contexto del hackathon**: el dataset fue construido en un marco temporal limitado y con criterios prácticos. Una recolección más extensa y equilibrada permitiría mayor robustez en los resultados.

