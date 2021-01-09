# analisisDeDatos

Informe estadístico del impacto del Covid-19 sobre la industria aérea europea, segmentado por año (2019 vs 2020) y por país

El dataset infoVuelos_.csv disponible en este repositorio está basado en el reporte "Airport traffic data by reporting airport and airlines" (https://data.europa.eu/euodp/es/data/dataset/43C6uGqWp92dX7vlgNzJA) publicado por Eurostat, la oficina estadística de la Unión Europea 

"Airport traffic data by reporting airport and airlines" cuenta con el total de pasajeros transportados por desde 1997 hasta octubre 2010 inclusive, segmentados por aeropuerto de partida (campo del dataset “rep_airp”) codificado en el formato estipulado por la OACI.

En una exploración inicial de la fuente de datos se observa que por el formato de la tabla (aeropuerto en el eje y, períodos en el x) hay una gran cantidad de registros en cero, por lo cual para evitar errores en los cálculos de las medidas se realizó una transformación del dataset, tomando únicamente las columnas con “totalVuelos” >=1.  
A fin de poder posterieromente analizar los datos con RStudio, se realizó una transformación y limpieza del dataset, transponiendo la base para que cada registro (fila) contenga la información [“rep_airp”, “totalVuelos”, “periodo”] y extrayéndose del mismo únicamente la información correspondiente a los tres primeros trimestres de 2019 y 2020. Por último, a partir del código del aeropuerto, se agregó una campo con la descripción del país correspondiente.

Se realiza una nueva exploración sobre el dataset limpio y se detectan seis países que no presentaban ningún dato en 2020: Bélgica, Irlanda, Polonia, Portugal, Serbia y Turquía, por lo cual serán excluídos del análisis en cuestión
