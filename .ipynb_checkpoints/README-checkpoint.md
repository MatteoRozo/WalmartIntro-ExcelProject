# Walmart Consumer Behavior Dashboard

## Introduction
This Walmart Consumer Behavior Excel dashboard was developed to find how loyalty systems, discounts and payment methods affect the overall expenditure. 

This

## Main objectives
Este dashboard hace uso de diversas habilidades en Excel, tales como:
- Uso de **fórmulas** como `XLOOKUP`, `SUMPRODUCT`, `IF`, `MEDIAN` and `UNIQUE`.
- **Gráficos dinámicos** y visualización de datos utilizando barras, mapas y gráficos.
- **Dynamic arrays** para análisis interactivos.

## Walmart Dataset Description
El conjunto de datos utilizado incluye información sobre los trabajos en el campo de la ciencia de datos, incluyendo:
- Títulos de trabajo (por ejemplo, Analista de Datos, Científico de Datos, Ingeniero de Datos).
- Salarios medianos por país.
- Tipo de jornada laboral (tiempo completo, medio tiempo, etc.).

## Dashboard Build
La construcción del dashboard se llevó a cabo de la siguiente manera:
1. **Preparación de los datos**: Limpieza y organización de la información.
2. **Creación de gráficos**: Selección de los gráficos más adecuados para visualizar los datos.
3. **Fórmulas y funciones**: Aplicación de cálculos y métricas relevantes.
4. **Interactividad**: Inclusión de filtros y validaciones para facilitar la interacción del usuario.

## 📉 Charts

### 📊 Data Science Job Salaries - Bar Chart
Uno de los principales gráficos en el dashboard es el gráfico de barras que muestra los salarios de los diferentes títulos de trabajo en la ciencia de datos.


### 🗺️ Country Median Salaries - Map Chart
Un mapa interactivo visualiza los salarios medianos por país, permitiendo ver rápidamente las diferencias regionales.


## 🧮 Formulas and Functions
Este dashboard utiliza varias fórmulas y funciones para calcular y analizar los datos:
- **Promedio de salario por trabajo**: `=AVERAGE(rango)`
- **Filtro de datos por país o tipo de trabajo**: Usando `VLOOKUP` y otras funciones de búsqueda.
- **Condiciones de salario**: Fórmulas como `IF` para determinar el rango salarial.

## 💰 Median Salary by Job Titles
En esta sección, se presenta el salario mediano para cada título de trabajo, lo que permite hacer comparaciones rápidas entre las posiciones.



## ⏰ Count of Job Schedule Type
Este gráfico muestra la distribución de los tipos de jornada laboral (tiempo completo, medio tiempo, etc.) de los trabajos en el conjunto de datos.


## ❎ Data Validation
La validación de datos se utiliza para asegurarse de que las entradas sean correctas. Esto incluye:
- Validación de tipo de datos para asegurarse de que los salarios sean numéricos.
- Restricciones para evitar que se introduzcan países o títulos de trabajo inválidos.

## 🔍 Filtered List
Esta funcionalidad permite a los usuarios filtrar la lista de trabajos y salarios según diferentes criterios, como país o tipo de trabajo.


## Conclusion
Este dashboard en Excel proporciona una forma sencilla y efectiva de visualizar y analizar los salarios en la industria de la ciencia de datos. A través de gráficos interactivos, validación de datos y un análisis detallado, ofrece una visión completa y precisa de las tendencias salariales en diferentes países y tipos de trabajo.


=MEDIAN(
  IF(
    (Walmart[customer_loyalty_level]=A2)*
    (LEFT(Walmart[store_location];FIND(",";Walmart[store_location])-1)=location)*
    (Walmart[payment_method]=method)*
    (Walmart[promotion_type]=promo);
    Walmart[total_expenditure])
)

=XLOOKUP(loyalty;A2:A5;B2:B5)

=SUMPRODUCT(--(Walmart[customer_loyalty_level] = loyalty); --(LEFT(Walmart[store_location]; FIND(","; Walmart[store_location])-1) = location); --(Walmart[payment_method] = method); --(Walmart[promotion_type] = promo))

=SORTBY(LEFT(A10:A14; FIND(","; A10:A14)-1); B10:B14; -1)

=UNIQUE(Walmart[customer_loyalty_level])

https://www.kaggle.com/datasets/ankitrajmishra/walmart