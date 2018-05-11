# psu-data

Este repositorio contiene scripts para importar y ordenar los datasets originales de la prueba PSU y llevarlos a SQL.

Para ordenar los datos las referencias fueron las siguientes:

* Reunir toda la documentación posible en pdf (incluída en este repositorio)
* Reunir los suplementos de la prueba PSU de El Mercurio (en papel) donde aparecen puntajes de corte, información de las carreras, etc

Dado que la prueba PSU entrega un puntaje calculado de acuerdo a una distribución normal con media 500, la referencia para saber si la limpieza de los datos originales era adecuada fue reemplazar los valores tales como 0, 000, 999, etc por `NA` y verificar que el promedio nacional es efectivamente en torno a 500 puntos. Este proceso lo hice de forma iterativa y mediante ensayo y error a partir del calculo directo del promedio PSU a nivel nacional (que dista mucho de 500 puntos si no se limpian los datos).

Hice una verificación manual de los datos a partir de los puntajes de corte de distintas carreras (datos versus reportado en suplemento del diario) y también verifiqué los códigos de las carreras y sus nombres (e.g. "Construcción Civil" versus "CONST CIV"). De acuerdo a este proceso hice una limpieza adicional de los datos usando expresiones regulares y buscando outliers mediante las funciones del paquete `tidyverse` y sobretodo haciendo análisis exploratorio de los datos con `ggplot2`.

Puedes revisar la estadística resumen que preparé para los años 2012-2016 en https://github.com/pachamaltese/psu-data/raw/master/0_descriptive_statistics_of_psu_results.xlsx

También dejé disponible el diagrama de la base de datos que preparé en https://github.com/pachamaltese/psu-data/blob/master/0_psu_database_diagram.svg

Todos los scripts están bajo licencia MIT.

