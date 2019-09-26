# Lectura y manejo de datos (Python)
Este proyecto consiste en importar tablas y datos de excel en python para uso y manipulación de estos como por ejemplo en gráficos.
 
 # Pre-requisitos
 Como pre requisitos se necesitan los siguientes programas y en este caso se usará el sistema operativo Ubuntu 18.04: 
 
   - Python
  
   - Spyder o Atom
 
   - Terminal de Ubuntu
 
 después de esto se necesitan las siguientes librerías para poder importar los datos de excel.
 
   - libreria pandas.
  
   - libreria matplotlib.
 
 # Instalación
 
Para la instalación abrimos la terminal (Ctrl+Alt+T) y escribimos los siguientes comandos

  `sudo apt-get install python`

lo instalan y ya tendrán python, para descargar e instalar spyder y atom se sigue el mismo proceso

  `sudo apt-get install atom`
  
con ese comando se instalará el editor de atom para python y para el editor spyder es

  `sudo apt-get install spyder`
  
Después de haber instalado python y alguno de los dos editores de python se procede a instalar las librerías de pandas y las demás para la importación de excel.

  `sudo apt-get install python-pandas`
  
  `sudo apt-get install python-matplotlib`
 
 # Ejecutando las pruebas 
 
 Primero entramos al editor de python Spyder, esto puede ser desde la terminal (Ctrl+T) o abriendo el programa.
Después de ya estar en el editor Spyder se procede a importar las librerías de pandas, matplotlib de la siguiente manera 

  `import pandas as pd`
  
  `import matplotlib.pyplot as plt`

Después de haber importado las librerías se crea una variable en la que se va a almacenar el archivo de excel usando la librería pandas (pd)
nombre(puede llamarse de cualquier forma)=pd.ExcelFile(‘nombre del archivo con su extención’)
ejemplo:

  `nombre=pd.ExcelFile(‘grafica2.xls’)`
  
Ojo: EL archivo de excel debe de estar en la misma ruta donde se guarda el código hecho en Atom u Spyder.
Ahora procedemos a imprimir la tabla de excel dando los siguientes comandos
 
 `print(nombre.sheet_names) `
 
el comando anterior sirve para mostrar los nombres de las hojas de calculo (pestañas de excel).
Teniendo ya eso, se transformará en un data frame.
  
  `data=nombre.parse(‘nombre de la pestaña de excel a la que se quiera acceder (Hoja1)’)`
  
Para imprimir los datos de la Hoja1 usamos el comando print
 
 `print(data)`
 
Con eso hasta el momento se tendrá la tabla de la hoja de excel, ahora para graficar usando dichos datos de Excel procedemos a usar los siguientes comandos.
  
  `Data.plot()`
  
Gracias a ese comando graficará la primera columna contra la segunda.


Si se desea que las gŕaficas tengan los ejes para así saber que se está mostrando por consola se necesita usar la libreria matplotlib, entonces se procede con las siguientes instrucciones:
  
  `x=hoja1.ix[:,0]`

Esto se posicionara en la primera columna y primera fila.
  
  `y=hoja1.ix[:,1]`

Ahora con este será la segunda columna y primera fila.

 `plt.ylabel('Rtd (ohms)')`
 
Para colocar el nombre usamos la libreria de matplotlib en el eje de la variable dependiente.
 
 `plt.xlabel('Temperatura (Centigrados)')`

Se hace lo mismo para la variable independiente.
 
 `plt.show`
Para mostrar por consola usamos plt.showw

Si se desean otro tipo de gráficas como la de barras se ejecuta el siguiente còdigo
`datos=pd.ExcelFile('grafica2.xls')`

`hoja2=datos.parse('Hoja2')`

`print(hoja2)`

`hoja2.plot(kind='bar')`

Justo en el .plot por dentro del parentesis se especifica el tipo de gráfica que se quiere.

`x=hoja2.ix[:,0]`

`y=hoja2.ix[:,1]`

`plt.ylabel('likes en Facebook')`

`plt.xlabel('Genero')`

`plt.show`

# Recursos
- Link de la página web en dónde están los tipos de gráfica:
[a link](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.DataFrame.plot.html)



# Construido con

  - Spyder
  
# Código completo!

 `import pandas as pd  `               #Importar las librerias para traer archivos

 `import matplotlib.pyplot as plt`     #Libreria para plotear gráficas

 `nombre=pd.ExcelFile('grafica2.xls') `   #aquí se genera el archivo de excel a python
 
 `print(nombre.sheet_names)  `            #se imprime por consola los nombres
 
` hoja1=nombre.parse('Hoja1')`           #Se crea un data frame  con el nombre de la pestaña en excel
 
  `m=hoja1.ix[:,0]  `                  #Posición de la tabla para gráficar
 
` n=hoja1.ix[:,1]  `                      
 
 `print(m)`
 
` print(n)`
 
 `plt.plot(m,n)  `                       #gráfica de m vs n
 
` plt.ylabel('Rtd (ohms)') `             #Rotulación del eje x (m)
 
 `plt.xlabel('Temperatura (Centigrados)')` #Rotulación del eje y (n)
 
` plt.show    `                          #Muestra por consola la rotulación

 
 ` datos=pd.ExcelFile('grafica2.xls')`     
` hoja2=datos.parse('Hoja2')`             #Se entra en el archivo excel y se abre la pestaña 2 que en este caso es Hoja2
` print(hoja2)`                           #Se implirme la tabla de la hoja2
` hoja2.plot(kind='bar') `                #Con el comando kind se selecciona el tipo de gráfica que se desea
` x=hoja2.ix[:,0]`                        #Se escoge el lugar en dónde se encuentra columna de la variable independiente
` y=hoja2.ix[:,1]`                        #Se escoge el lugar en dónde se encuentra columna de la variable dependiente
` plt.ylabel('likes en Facebook')`        #Rotulación del eje dependiente
` plt.xlabel('Genero')`                   #Rotulación del eje independiente
` plt.show `                              #Muestra por consola la rotulación
 
 

# Autores
Universidad de Ibagué -Ingeniería Electrónica
- **Juan Pablo Siachica**
- **Juan Camilo Buitrago**
-
