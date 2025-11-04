# Primer Laboratorio de la Especialización en Análisis de Datos

[Notebook en Colab](https://colab.research.google.com/drive/1fjIo_-eQZl7XEwU0tiRq-rw63OFB4ege?usp=sharing)

## Consideraciones Importantes

1. **Origen del Dataset:**
   El dataset original proviene de una ingesta irregular de datos (scraping) de diferentes sitios web. Como resultado, contiene numerosos valores nulos. A pesar de esto, considero que se deben conservar todos los registros que incluyen *precios*, *días*, *habitaciones*, *baños* y *capacidad*, aunque no estén completamente especificados.

2. **Inconsistencias en los Datos:**
   Existen muchas **inconsistencias** en los datos, por lo que es necesario analizarlos con cautela. Por ejemplo, el README original del dataset menciona que los *precios con dígitos repetidos son, en su mayoría, falsos*. Sin embargo, hay precios como "1,666,666,665" que no cumplen estrictamente con esta regla, pero se puede inferir que son falsos. A la vez, la frase *en su mayoría* deja abierta la posibilidad de que haya precios como "55.555" que sean reales por simple coincidencia.

3. **Precios en Dólares:**
   Los precios inferiores a 7,000 se asumen como valores en dólares. No obstante, dada la baja fiabilidad de los datos y el mensaje del README, existe la **posibilidad** de que algunos precios superiores a 7,000 puedan estar en dólares.

4. **Calidad de los Precios:**
   El dataset contiene precios poco confiables debido a la inclusión de valores falsos. En su mayoría, se han tratado aquellos precios que tienen dígitos repetidos, pero pueden existir otros precios como "12345678" o "2666667" que también son sospechosos (y hay muchas variantes a considerar). Para facilitar el análisis futuro, he incluido una columna denominada `has_price` que indica si el precio es válido o no.

5. **Impacto en las Estadísticas:**
   Debido a las inconsistencias mencionadas, cualquier análisis o estadística realizada sobre este dataset debe considerarse **errónea** en gran medida.

6. **Mezcla de Monedas:**
   Los precios están mezclados entre dólares y pesos. Inicialmente consideré incluir dos columnas separadas (`price_ars` y `price_usd`) para cada moneda. Sin embargo, he optado por incluir una sola columna que indica si el precio está en dólares, utilizando la columna `is_usd`.

7. **Consideraciones en las Preguntas de Negocio:**
   Las preguntas de negocio incluidas como ejemplo han sido formuladas teniendo en cuenta las limitaciones del dataset o, al menos, buscando minimizar el impacto de las inconsistencias en los datos.

