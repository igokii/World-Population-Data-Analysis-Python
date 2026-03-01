# Fundamentals of Programming - 1st Year Engineering
# Lab Exercise: World Population
### Author: Toñi Reina
---

In  this  project,  we  will  work  with  data  on  world  population  trends  by  country, 
represented by lists. We will implement a series of functions that will allow us to display 
graphs of population trends and compare the populations of different countries. 
 
The data we are starting with in the project is in the population.csv file in the 
data folder of the project. If you open the file, you will see that it is in CSV format (the data is 
separated by commas). You can see an excerpt from it here: 

<img src="./img/figura1.png" alt="drawing" width="300"/>

As you can see, each line of the file has the name of a country, the code for that country, the year 
in which the population data was collected, and the population of the country in that year. For example, from 
the first line of the excerpt we can see that Spain had 30,455,000 inhabitants in 1960. 
 
In the project, we will have to find out, on the one hand, how many different countries and which countries 
we have data for, and on the other hand, we will have to display two types of graphs, one that allows us to 
see the evolution of a country's population over time, and another that allows us to 
compare the populations of several countries in a specific year.

<img src="./img/figura2.png" alt="drawing" width="800"/>

Create two modules, one called **poblacion.py**, where we will implement the functions, and another called **poblacion_test.py**, where we will implement the tests for the previous functions. 
We will use named tuples to store the data from the file. Include the following definition in the **poblacion.py** module:

```
RegistroPoblacion = namedtuple('RegistroPoblacion', 'pais, codigo, año, censo')
```
Implement the following functions in the module **poblacion.py** and write the corresponding tests in the module **poblacion_test.py**:

* **lee_poblaciones(ruta_fichero)**:  
  Reads the input file and returns a list of tuples of type `RegistroPoblacion`.

* **calcula_paises(poblaciones)**:  
  Takes a list of tuples of type `RegistroPoblacion` and returns an **alphabetically sorted** list with the names of the countries for which there is data.

* **filtra_por_pais(poblaciones, nombre_o_codigo)**:  
  Takes a list of tuples of type `RegistroPoblacion`, and the name or code of a country, and returns a list of tuples with the data of the country passed as a parameter (year and census). **Important!** The country may be provided in the *nombre_o_codigo* parameter either by its full name or by its code.

* **filtra_por_paises_y_anyo(poblaciones, anyo, paises)**:  
  Takes a list of tuples of type `RegistroPoblacion`, a year, and a set of country names, and returns a list of tuples `(nombre_pais, num_habitantes)` with the data for the year passed as a parameter for the countries included in the *paises* parameter.

* **muestra_evolucion_poblacion(poblaciones, nombre_o_codigo)**:  
  Takes a list of tuples of type `RegistroPoblacion` and the name or code of a country, and generates a plot with the population trend curve of the country given as a parameter. **Important!** The country may be provided in the *nombre_o_codigo* parameter either by its full name or by its code. Use the following code to generate the plot:

    ```
    plt.title(titulo)
    plt.plot(lista_años, lista_habitantes)
    plt.show()
    ```
    where ```titulo``` is a string that will be displayed as the title of the plot, ```lista_años``` is a list of integers with the years for which there is population data for the country in question, and ```lista_habitantes``` is a list of integers with the number of inhabitants for each year in the previous list.

* **muestra_comparativa_paises_anyo(poblaciones, anyo, paises)**:  
Takes a list of tuples of type `RegistroPoblacion`, a year, and a set of country names, and generates a bar chart with the population of those countries in the year given as a parameter. The countries will be shown on the X axis in alphabetical order. Use the following code to generate the plot:

    ```
    plt.title(titulo)
    plt.bar(lista_paises, lista_habitantes)
    plt.show()
    ```

where ```titlo``` is a string that will be displayed as the title of the plot, ```lista_paises``` is a list of strings with the labels of the bars to be shown on the X axis, and ```lista_habitantes``` is a list of integers with the number of inhabitants to represent in each bar of the chart.

---
## Fundamentos de Programación
# Ejercicio de laboratorio: Población Mundial
### Autora: Toñi Reina
---

En  este  proyecto  trabajaremos  con  datos  de  la  evolución  de  la  población  mundial  por  países, 
representados mediante listas. Implementaremos una serie de funciones que nos permitirán mostrar 
tanto gráficas de evolución de la población, como comparar la población en distintos países. 
 
Los datos de los que partimos en el proyecto están en el fichero population.csv de la carpeta 
data del proyecto. Si abre el fichero, comprobará que es un fichero en formato CSV (los datos están 
separados por comas). Un extracto del mismo lo puede ver aquí: 

<img src="./img/figura1.png" alt="drawing" width="300"/>

Como puede observar cada línea del fichero tiene el nombre de un país, el código de ese país, el año 
en el que fueron tomados los datos de población, y la población del país en ese año. Por ejemplo, de 
la primera línea del extracto podemos ver que España tenía 30.455.000 habitantes en 1960. 
 
En el proyecto tendremos que averiguar, por una parte, de cuántos países distintos y de qué países 
disponemos datos, y por otra parte tendremos que mostrar dos tipos de gráficos, uno que nos permita 
ver la evolución de la población de un país a lo largo de tiempo, y otro que nos permita 
comparar las poblaciones de varios países en un año concreto.

<img src="./img/figura2.png" alt="drawing" width="800"/>


Cree dos módulos, uno llamado **poblacion.py**, donde implementaremos las funciones, y otro llamado **poblacion_test.py**, donde implementaremos los tests de las funciones anteriores. 

Utilizaremos tuplas con nombre para guardar los datos del fichero. Incluya la siguiente definición en el módulo **poblacion.py**:

```
RegistroPoblacion = namedtuple('RegistroPoblacion', 'pais, codigo, año, censo')
```

Implemente las siguientes funciones en el módulo **poblacion.py** y realice los tests correspondientes en el módulo **poblacion_test.py**:

* **lee_poblaciones(ruta_fichero)**:
    lee el fichero de entrada y devuelve una lista de tuplas de tipo RegistroPoblacion.
* **calcula_paises(poblaciones)**:
    toma una lista de tuplas de tipo RegistroPoblacion y devuelve una lista **ordenada alfabéticamente** con los nombres de los países para los que hay datos.
* **filtra_por_pais(poblaciones, nombre_o_codigo)**:
    toma una lista de tuplas de tipo RegistroPoblacion, y el nombre o código de un país, y devuelve una lista de tuplas con los datos del país que se pasa como parámetro (año y censo). **¡Importante!**: el país puede venir expresado en el parámetro *nombre_o_codigo* con su nombre completo o con su código.
* **filtra_por_paises_y_anyo(poblaciones, anyo, paises)**:
    toma una lista de tuplas de tipo RegistroPoblacion, un año y un conjunto de nombres de países, y devuelve una lista de tuplas (nombre_pais, num_habitantes) con los datos del año pasado como parámetro para los países incluidos en el parámetro *paises*. 
* **muestra_evolucion_poblacion(poblaciones, nombre_o_codigo)**:
    toma una lista de tuplas de tipo RegistroPoblacion y el nombre o código de un país, y genera una gráfica con la curva de evolución de la población del país dado como parámetro. **¡Importante!**: el país puede venir expresado en el parámetro *nombre_o_codigo* con su nombre completo o con su código. Utilice el siguiente código para generar la gráfica:
    ```
    plt.title(titulo)
    plt.plot(lista_años, lista_habitantes)
    plt.show()
    ```
    donde ```titulo``` es una cadena de texto que se mostrará como título de la gráfica, ```lista_años``` es una lista de enteros con los años para los que hay datos de población del país en cuestión, y ```lista_habitantes``` es una lista de enteros con el número de habitantes en cada año de la lista anterior.

* **muestra_comparativa_paises_anyo(poblaciones, anyo, paises)**:
    toma una lista de tuplas de tipo RegistroPoblacion, un año y un conjunto de nombres de países y genera una gráfica de barras con la población de esos países en el año dado como parámetro. Los países se mostrarán en el eje X en orden alfabético. Utilice el siguiente código para generar la gráfica:
    ```
    plt.title(titulo)
    plt.bar(lista_paises, lista_habitantes)
    plt.show()
    ```
    donde ```titulo``` es una cadena de texto que se mostrará como título de la gráfica, ```lista_paises``` es una lista de cadenas con las etiquetas de las barras a mostrar en el eje x, y ```lista_habitantes``` es una lista de enteros con el número de habitantes a representar en cada barra del gráfico.



