# MAVEN TOYS SALES DASHBOARD | POWER BI

# Descripción del Proyecto
Con este proyecto he tratado de mejorar el mismo análisis realizado previamente con SQL y Excel, dando una mejor legibilidad a los resultados obtenidos mediante Power BI y el uso de medidas DAX.
El proyecto consiste en la creación de dashboards analíticos sobre una empresa juguetera distribuida por México. Los datos analizados son históricos y ficticios. A partir de ellos se han desarrollado diferentes medidas DAX para obtener información relevante y construir los principales KPIs del negocio.
La metodología seguida analiza la empresa desde tres perspectivas: Ventas, Productos y Tiendas. Cada página está diseñada para responder diferentes preguntas de negocio que se plantean a continuación.

# Objetivos del estudio
Los objetivos estudiados van de la mano del proyecto realizado previamente en SQL y Excel, ya que se trata del mismo caso práctico desarrollado con una herramienta diferente.
Las principales preguntas de negocio son:

¿Cómo evolucionan los ingresos a lo largo del tiempo?
¿Qué categorías generan más ingresos?
¿Qué productos son los más rentables?
¿Qué ciudades generan mayor facturación?
¿Qué productos presentan mayor riesgo de rotura de stock?
¿Cuál es el margen de beneficio del negocio?
Estas son las principales cuestiones que se pretenden resolver, aunque durante el desarrollo del proyecto surgieron otras preguntas que también fueron analizadas.

# Metodología
1. Importación y validación de archivos CSV.
2. Modelado de datos.
3. Creación de medidas DAX.
4. Creación del dashboard.
5. Elaboración de conclusiones y recomendaciones.

## 1. Importación y validación de datos
En este caso los datos podrían haberse importado directamente desde SQL, ya que el proceso de limpieza y validación ya había sido realizado previamente. Sin embargo, preferí hacerlo desde archivos CSV para seguir practicando el proceso de limpieza y transformación de datos mediante Power Query.

## 2. Modelado de datos
Una vez importados y validados los datos, procedí a plantear el modelo de datos creando dos tablas de hechos que estarán relacionadas con tres tablas de dimensiones. De esta manera se crea un modelo en estrella. En la siguiente imagen podréis ver como estructure las relaciones y la dirección de las mismas.
Posteriormente creé una tabla de fechas que sirve como dimensión temporal para poder relacionar correctamente las diferentes tablas y realizar análisis temporales mediante DAX.

## 3. Creación de medidas DAX
Una vez ya con el modelo creado y las relaciones bien planteadas lo que hice fue plantear el negocio y los objetivos para empezar a realizar medidas DAX creando asi las primeras medidas que posteriormente sirvieron para construir medidas más complejas y los diferentes KPIs del dashboard.
Entre las principales medidas desarrolladas destacan:
Revenue
Profit
Revenue Último Mes
Revenue Mes Anterior
Profit Último Mes
Número de Ventas
Número de Ventas Último Mes
Índice de Presión sobre el Stock
Todas las medidas fueron desarrolladas manualmente mediante DAX, sin utilizar cálculos automáticos.

## 4. Creación del Dashboard

El análisis realizado se divide en tres dashboards diferentes: Ventas, Productos y Tiendas, donde cada uno responde a diferentes preguntas de negocio según el ámbito analizado.

Dashboard de Ventas
## Dashboard de Ventas
Se trata de un dashboard ejecutivo enfocado al análisis de las ventas de la empresa. Es un dashboard ejecutivo puesto que el usuario no puede interactuar con los gráficos ni los datos. Se hizo así con el objetivo de ofrecer una visión estable y comparable del negocio.
Este Dashboard abarca preguntas de negocio que afectan a tres grupos, estos grupos son: la facturación, el margen de beneficio y el numero de ventas.
La estructura es la misma para los tres grupos, trabajando siempre a mes vencido. De esta forma se evitan meses incompletos que puedan dar lugar a interpretaciones erróneas.
Los resultados obtenidos pueden compararse con el mes anterior y con el mismo mes del año anterior, permitiendo calcular indicadores como la evolución mensual (MoM), la evolución interanual (YoY) y observar la tendencia de los últimos doce meses.
Con este dashboard se responde principalmente a preguntas relacionadas con la evolución de los ingresos, la rentabilidad del negocio y su comportamiento a lo largo del tiempo.

## Dashboard de Productos
El segundo dashboard analiza la empresa desde la perspectiva de los productos que comercializa.
Los principales objetivos de esta página son mostrar los productos con mayor facturación, analizar la distribución de los ingresos por categorías y detectar aquellos productos con mayor presión sobre el inventario.
Este dashboard pasa a ser analítico, permitiendo al usuario interactuar mediante los slicers de Categoría y Fecha para analizar diferentes periodos o segmentos del catálogo.
Uno de los indicadores más interesantes desarrollados es el Índice de Presión sobre el Stock. Este indicador se creó debido a que el dataset no dispone de información sobre las reposiciones de inventario. Para ello se relacionan las unidades vendidas con el stock disponible, obteniendo un ratio que permite identificar aquellos productos que presentan una mayor presión sobre su inventario y, por tanto, una mayor prioridad de reposición.
Un ejemplo es el producto Colorbuds, que presenta un índice de 90,05, lo que significa que durante todo el periodo analizado se han vendido aproximadamente 90 veces las unidades que actualmente permanecen en stock. Esto indica una elevada presión sobre el inventario y la necesidad de revisar su reposición.

## Dashboard de Tiendas
El último dashboard analiza la empresa desde la perspectiva de sus tiendas, mostrando cómo se distribuyen geográficamente, qué zonas abarcan y cuál es el rendimiento de cada una de ellas.
Al igual que el dashboard de Productos, se trata de un dashboard analítico donde el usuario puede interactuar mediante filtros de Fecha y Zona Geográfica.
Entre las principales visualizaciones destacan un mapa con la distribución de las tiendas, un análisis de las ciudades con mayor facturación y un gráfico comparativo entre las mejores tiendas según sus ingresos y beneficios.
Con este dashboard se responde a preguntas relacionadas con la distribución geográfica de la empresa, la facturación por ciudad, las tiendas con mejor rendimiento y aquellas ubicaciones que generan un mayor beneficio.

## 5. Elaboración de conclusiones y recomendaciones

### Principales conclusiones

- El negocio mantiene un rendimiento estable durante la mayor parte del periodo, mostrando una evolución relativamente constante tanto en facturación como en número de ventas, sin cambios bruscos durante el año. Sin embargo, se aprecia una ligera tendencia descendente en el margen de beneficio, el cual comienza a recuperarse en los últimos meses, aunque todavía no alcanza los niveles iniciales.

- La comparación interanual (YoY) muestra un incremento tanto en la facturación como en el número de ventas respecto al mismo periodo del año anterior. Sin embargo, el margen de beneficio es ligeramente inferior, lo que indica que, aunque el negocio genera más ingresos, obtiene una menor rentabilidad sobre las ventas. Este comportamiento debería analizarse con mayor detalle para identificar sus posibles causas.

- En cuanto a los productos, observamos que la categoría **Toys** es la que mayor facturación genera, representando el **35,26 %** del total. También se muestran los diez productos con mayor facturación junto con el beneficio generado por cada uno de ellos. Sin embargo, el análisis más relevante de esta página es el **Índice de Presión sobre el Stock**, donde destacan especialmente **Action Figure** y **Colorbuds**, dos productos que presentan una elevada presión sobre el inventario y que deberían tener prioridad en la reposición de stock para reducir el riesgo de rotura.

- Si pasamos a la página de tiendas, observamos que las tiendas con mayor facturación se concentran en las grandes ciudades. Además, la zona **Downtown** representa aproximadamente el **56,9 %** de la facturación total, lo que indica una elevada concentración de los ingresos en este tipo de ubicación y una fuerte dependencia de estas zonas para el rendimiento del negocio.

### Principales recomendaciones

- Estudiar la disminución del margen de beneficio observada en la comparación interanual (YoY), identificando las posibles causas y analizando qué medidas podrían adoptarse para incrementar la rentabilidad del negocio.

- Priorizar la reposición de stock de los productos **Action Figure** y **Colorbuds** para reducir el riesgo de rotura de stock y evitar el posible impacto sobre las ventas.

- Tratar de mejorar el resto de categoría de productos con el objetivo de evitar que gran parte de la facturación del negocio (más de 1/3) dependa de la categoria **Toys**.






