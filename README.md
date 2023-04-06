# TFG notebooks
Notebooks used for my TFG.


**Spanish note**  
Aviso a navegantes, en estos notebooks hay cosas mal, como labels en imagenes, pruebas fallidas o incompletas. También puede ser que se defina una función, que en celdas o notebooks posteriores se vuelve a definir con modificaciones, mejoras etc. Esto es porque son notebooks de desarrollo, no se pensaron para ser presentados o explicados.

En este repositorio se puede ver el proceso/evolución del proyecto. Este proceso de desarrollo no es lineal, pero podríamos ordenar a groso modo la creación de las carpetas para entender la lógica y el razonamiento con el que se fue desarrollando. 
**Cosas que se hicieron:**
- Reproducción del TFG de Rodrigo.
- Exploración de los datos (EDA).
  - Densidades de incidencias (counts)
  - Mapas de calor de las intensidades segun elementos.
  - Mapas de calor según elemento y tramos para la variable analizada.
  - Analisis generales sobre valores de ciertas magnitudes (e.g. energía de los eventos)
- Creacion de modelos:
    - Un telescopio:
      - Modelos sencillos CNN.
    - Multiple telescopios:
      - Modelos CNN para clasificación en clases: se probaron diferentes agrupaciones. Todos los elementos, gamma/electron/hadrones, etc.
      - _Big input model_: Este modelo tiene la particularidad de que pretende meter todos los inputs (imágenes de telescopio) en un solo input mas grande, esto permetiría que el modelo no dependiera de la existencia obligatoria de todas las imagenes de todos los telescopios empletado (si no exist, pues se deja a 0 esa zona).
      - Modelos para regresión de energía: Tienen la misma estructura que los de clasificación, pero terminan en una neurona que predice la energía. Se entrenan y evaluan diferente obviamente, es otro tipo de problema (regresión y no clasificación).
      - Modelos con autoencoder como primer step: Estos modelos tenía una primera etapa de autoencoder(entrenado a priori) que pretendía ayudar a filtrar el ruido para que el resto de la red recibiera datos más limpios. Pero resulta que eso no hace falta, porque la propia red CNN ya es capaz de hacerse su propio filtrado.

**Orden de creación de las carpetas:**  
1. single_input
2. recomp_funs (esto casi que no vale de nada)
3. autoencoders
4. procesado_datos_multi_telescop
5. big_input
6. models_multiinput
7. FINAL_NOTEBOOK


**Nota:** Si alguien quisiera extraer información util de este repositorio, yo recomiendo que:  
1. Revise y vaya apuntando los resultados que le interesaría obtener por su cuenta. 
2. Explore por orden las carpetas y vaya apuntando el notebook y la linea en la que hay información que le podría interesar. 
3. Destilar esto un poco, para obtener unos poco notebooks de los que extraer información. Si se abarcan demasiado, se terminará comprobando la similitud entre funciones que parecen similares y quiza tienen variaciones que en su momento me parecieron buena idea (sorry not sorry).
4. Terminar copiando y adaptando pequeñas partes de codigo, e ir progresivamente probandolo (SI SE HACE UN FRANKESTEIN DEMASIADO RÁPIDO, SERÁ INDEBUGEABLE ESO).
5. Adaptarlo, entenderlo y personalizarse todo el codigo. Usarlo tal como está puede hacer que cometas errores que no encontré.

**Extra:** Te recomiendo que no intentes **calcar** un notebook paso a paso para aprender lo que hago, porque como te comentaba, son notebooks de desarrollo, por lo que igual de defino algo que luego no hace falta, o algo importante esta definido donde no debe. Esto debería planteado más desde el punto de vista de **reutilización de código útil**. Determina tus necesidades y busca lo que las satisfaga en los notebooks, porque estos no te van a guiar en la enseñanza, pues no fueron creados conese proposito, y pueden liar más de los que enseñan, si no se sabe lo que se busca.


