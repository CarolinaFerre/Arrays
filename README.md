# ejercicios-de-arrays

Arrays unidimensionales.

Todos los lenguajes de programación permiten el uso de arrays, veamos como son en Java.
Los arrays permiten almacenar una colección de objetos o datos del mismo tipo. Son muy útiles y su utilización es muy simple:
Declaración del array Declaración del array. La declaración de un array consiste en decir "esto es un array" y sigue la siguiente estructura: "tipo[] nombre;". El
tipo será un tipo de variable o una clase ya existente, de la cual se quieran almacenar varias unidades.
Creación del array Creación del array. La creación de un array consiste en decir el tamaño que tendrá el array, es decir, el número de elementos que
contendrá, y se pone de la siguiente forma: "nombre=new tipo[dimension]", donde dimensión es un número entero positivo que indicará el
tamaño del array. Una vez creado el array este no podrá cambiar de tamaño.

Veamos un ejemplo de su uso:
Una vez hecho esto, ya podemos almacenar valores en cada una de las posiciones del array, usando corchetes e indicando en su interior la
posición en la que queremos leer o escribir, teniendo en cuenta que la primera posición es la cero y la última el tamaño del array menos uno. En
el ejemplo anterior, la primera posición sería la 0 y la última sería la 9.


Autoevaluación
¿Cuáles de las siguientes opciones permitiría almacenar más de 50 números decimales? ¿Cuáles de las siguientes opciones permitiría almacenar más de 50 números decimales?
 int[] numeros; numeros=new int[51]; 
 int[] numeros; numeros=new !oat[52]; 
 double[] numeros; numeros=new double[53]; 
float[] numeros=new float[54]; 

Resolver

int[] n; // Declaración del array.

n = new int[10]; //Creación del array reservando para el un espacio en memoria.

int[] m=new int[10]; // Declaración y creación en un mismo lugar.




Uso de arrays unidimensionales.


Ya sabes declarar y crear de arrays, pero, ¿cómo y cuando se usan? Pues existen tres ámbitos principalmente donde se pueden usar, y los tres
son muy importantes: modi"cación de una posición del array, acceso a una posición del array y paso de parámetros.
La modi"cación de una posición del array se realiza con una simple asignación. Simplemente se especi"ca entre corchetes la posición a
modi"car después del nombre del array. Veamoslo con un simple ejemplo:
El acceso a un valor ya existente dentro de una posición del array se consigue de forma similar, simplemente poniendo el nombre del array y la
posición a la cual se quiere acceder entre corchetes:
Para nuestra comodidad, los arrays, como objetos que son en Java, disponen de una propiedad pública muy útil. La propiedad length nos
permite saber el tamaño de cualquier array, lo cual es especialmente útil en métodos que tienen como argumento un array.
El tercer uso principal de los arrays, como se dijo antes, es en el paso de parámetros. Para pasar como argumento un array a una función o
método, esta debe tener en su de"nición un parámetro declarado como array. Esto es simplemente que uno de los parámetros de la función
sea un array. Veamos un ejemplo:

En el método anterior se pasa como argumento un array numérico, sobre el cual se calcula la suma de todos los números que contiene. Es un
uso típico de los arrays, "jate que especi"car que un argumento es un array es igual que declarar un array, sin la creación del mismo. Para pasar
como argumento un array a una función, simplemente se pone el nombre del array:

En Java las variables se pasan por copia a los métodos, esto quiere decir que cuando se pasa una variable a un método, y se realiza una
modi"cación de su valor en dicho método, el valor de la variable en el método desde el que se ha realizado la invocación no se modi"ca. Pero
cuidado, eso no pasa con los arrays. Cuando dicha modi"cación se realiza en un array, es decir, se cambia el valor de uno de los elementos del
array, si que cambia su valor de forma de"nitiva. Veamos un ejemplo que ilustra ambas cosas:

int[] numeros=new int[3]; // Array de 3 números (posiciones del 0 al 2).

numeros[0]=99; // Primera posición del array.

numeros[1]=120; // Segunda posición del array.

numeros[2]=33; // Tercera y última posición del array.

int suma=numeros[0] + numeros[1] + numeros[2];

System.out.println("Longitud del array: "+numeros.length);

int sumaarray (int[] j) {

 int suma=0;
 
 for (int i=0; i<j.length;i++)
 
 suma=suma+j[i];
 
 return suma;
 
}

int suma=sumaarray (numeros);

public static void main(String[] args) {

 int j=0; int[] i=new int[1]; 
 
 i[0]=0;
 
 modificaArray(j,i);
 
 System.out.println(j+"-"+i[0]); /* Mostrará por pantalla "0–1", puesto que el contenido del array es 
 
 modificado en la función, y aunque la variable j también se modifica, se modifica una copia de la misma,
 
dejando el original intacto */

}

int modificaArray(int j, int[] i) {

 j++;
 
 i[0]++; /* Modificación de los valores de la variable, solo afectará al array, no a j */
 
}

Inicialización.

Rellenar un array, para su primera utilización, es una tarea muy habitual que puede ser rápidamente simpli"cada. Vamos a explorar dos
sistemas que nos van a permitir inicializar un array de forma cómoda y rápida.
En primer lugar, una forma habitual de crear un array y rellenarlo es simplemente a través de un método que lleve a cabo la creación y el
rellenado del array. Esto es sencillo desde que podemos hacer que un método retorne un array simplemente indicando en la declaración que el
valor retornado es tipo[], donde tipo de dato primitivo (int, short, float,...) o una clase existente (String por ejemplo). Veamos un ejemplo:
En el ejemplo anterior se crea un array con una serie de números consecutivos, empezando por el cero, ¿sencillo no? Este uso suele ahorrar
bastantes líneas de código en tareas repetitivas. Otra forma de inicializar los arrays, cuando el número de elementos es "jo y sabido a priori, es
indicando entre llaves el listado de valores que tiene el array. En el siguiente ejemplo puedes ver la inicialización de un array de tres números, y
la inicialización de un array con tres cadenas de texto:

Pero cuidado, la inicialización solo se puede usar en ciertos casos. La inicialización anterior funciona cuando se trata de un tipo de dato primitivo
(int, short, float, double, etc.) o un String, y algunos pocos casos más, pero no funcionará para cualquier objeto.

Cuando se trata de un array de objetos, la inicialización del mismo es un poco más liosa, dado que el valor inicial de los elementos del array de
objetos será null, o lo que es lo mismo, crear un array de objetos no signi"ca que se han creado las instancias de los objetos. Hay que crear,
para cada posición del array, el objeto del tipo correspondiente con el operador new. Veamos un ejemplo con la clase StringBuilder. En el
siguiente ejemplo solo aparecerá null por pantalla:
Para solucionar este problema podemos optar por lo siguiente, crear para cada posición del array una instancia del objeto:

Para acceder a una propiedad o a un método cuando los elementos del array son objetos, puedes usar la notación de punto detrás de los
corchetes, por ejemplo: diassemana[0].length. Fijate bien en el array diassemana anterior y piensa en lo que se mostraría por pantalla con el
siguiente código:


Autoevaluación
¿Cuál es el valor de la posición 3 del siguiente array: ¿Cuál es el valor de la posición 3 del siguiente array: String[] m=new String[10]??
 null. 
 Una cadena vacía. 
 Daría error y no se podría compilar. 
 
static int[] ArrayConNumerosConsecutivos (int totalNumeros) {

 int[] r=new int[totalNumeros];
 
 for (int i=0;i<totalNumeros;i++) r[i]=i;
 
 return r;

}

int[] array = {10, 20, 30};

String[] diassemana= {"Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"};

StringBuilder[] j=new StringBuilderStringBuilder[10];

for (int i=0; i<j.length;i++) System.out.println("Valor" +i + "="+j[i]); // Imprimirá null para los 10 valores.

StringBuilder[] j=new StringBuilder[10];

for (int i=0; i<j.length;i++) j[i]=new StringBuilder("cadena "+i); 

System.out.println(diassemana[0].substring(0,2)); 







. Arrays multidimensionales.


¿Qué estructura de datos utilizarías para almacenar los píxeles de una imagen digital? Normalmente las imágenes son cuadradas o
rectangulares, así que una de las estructuras más adecuadas es la matriz. En la matriz cada valor podría ser el color de cada píxel. Pero, ¿qué es
una matriz a nivel de programación? Pues es un array con dos dimensiones, o lo que es lo mismo, un array cuyos elementos son arrays de
números.

Los arrays multidimensionales están en todos los lenguajes de programación actuales, y obviamente también en Java. La forma de crear un
array de dos dimensiones en Java es la siguiente:

El código anterior creará un array de dos dimensiones, o lo que es lo mismo, creará un array que contendrá 4 arrays de 5 números cada uno.
Veámoslo con un ejemplo grá!co:

Al igual que con los arrays de una sola dimensión, los arrays multidimensionales deben declararse y crearse. Podremos hacer arrays
multidimensionales de todas las dimensiones que queramos y de cualquier tipo. En ellos todos los elementos del array serán del mismo tipo,
como en el caso de los arrays de una sola dimensión. La declaración comenzará especi!cando el tipo o la clase de los elementos que forman el
array, después pondremos tantos corchetes como dimensiones tenga el array y por último el nombre del array, por ejemplo:
La creación es igualmente usando el operador new, seguido del tipo y los corchetes, en los cuales se especi!ca el tamaño de cada dimensión:
Todo esto, como ya has visto en un ejemplo anterior, se puede escribir en una única sentencia.


Autoevaluación
Completa con los números que faltan: Completa con los números que faltan:
El array anterior es de dimensiones, y tiene un total de números enteros.

int[][] a2d=new int[4][5];

int [][][] arrayde3dim;

arrayde3dim=new int[2][3][4];

int[][][] k=new int[10][11][12];



Uso de arrays multidimensionales.


¿Y en que se diferencia el uso de un array multidimensional con respecto a uno de una única dimensión? Pues en muy poco la verdad.
Continuaremos con el ejemplo del apartado anterior:

Para acceder a cada uno de los elementos del array anterior, habrá que indicar su posición en las dos dimensiones, teniendo en cuenta que los
índices de cada una de las dimensiones empieza a numerarse en 0 y que la última posición es el tamaño de la dimensión en cuestión menos 1.
Puedes asignar un valor a una posición concreta dentro del array, indicando la posición en cada una de las dimensiones entre corchetes:
Y como es de imaginar, puedes usar un valor almacenado en una posición del array multidimensional simplemente poniendo el nombre del
array y los índices del elemento al que deseas acceder entre corchetes, para cada una de las dimensiones del array. 

Por ejemplo:
Como imaginarás, los arrays multidimensionales pueden también ser pasados como parámetros a los métodos, simplemente escribiendo la
declaración del array en los argumentos del método, de forma similar a como se realizaba para arrays de una dimensión. 

Por ejemplo:
Del código anterior, !jate especialmente en el uso del atributo length (que nos permite obtener el tamaño de un array). Aplicado directamente
sobre el array nos permite saber el tamaño de la primera dimensión (a2d.length). Como los arrays multidimensionales son arrays que tienen
como elementos arrays (excepto el último nivel que ya será del tipo concreto almacenado), para saber el tamaño de una dimensión superior
tenemos que poner el o los índices entre corchetes seguidos de length (a2d[i1].length).
Para saber al tamaño de una segunda dimensión (dentro de una función por ejemplo) hay que hacerlo así y puede resultar un poco engorroso,
pero gracias a esto podemos tener arrays multidimensionales irregulares.

Una matriz es un ejemplo de array multidimensional regular, ¿por qué? Pues porque es un array que contiene arrays de números todos del
mismo tamaño. Cuando esto no es así, es decir, cuando los arrays de la segunda dimensión son de diferente tamaño entre sí, se puede decir
que es un array multidimensional irregular. En Java se puede crear un array irregular de forma relativamente fácil, veamos un ejemplo para dos
dimensiones.

int[][] a2d=new int[4][5];

a2d[0][0]=3;

int suma=a2d[0][0]+a2d[0][1]+a2d[0][2]+a2d[0][3]+a2d[0][4];

static int sumaarray2d(int[][] a2d) {

 int suma = 0;
 
 for (int i1 = 0; i1 < a2d.length; i1++) 
 
 for (int i2 = 0; i2 < a2d[i1].length; i2++) suma += a2d[i1][i2];
 
 return suma;
 
 }
 
Declaramos y creamos el array Declaramos y creamos el array pero sin especi pero sin especi!car la segunda dimensión. car la segunda dimensión. Lo que estamos haciendo en realidad es crear
simplemente un array que contendrá arrays, sin decir como son de grandes los arrays de la siguiente dimensión: int[][] irregular=new
int[3][];

Después creamos cada uno de los Después creamos cada uno de los arrays unidimensionales arrays unidimensionales (del tamaño que queramos) y lo asignamos a la posición correspondiente
del array anterior: irregular[0]=new int[7]; irregular[1]=new int[15]; irregular[2]=new int[9];


Recomendación

Cuando uses arrays irregulares, por seguridad, es conveniente que veri!ques siempre que el array no sea null en segundas dimensiones, y que
la longitud sea la esperada antes de acceder a los datos:
if (irregular[1]!=null && irregular[1].length>10) {...}


Inicialización de arrays multidimensionales.

¿En qué se diferencia la inicialización de arrays unidimensionales de arrays multidimensionales? En muy poco. La inicialización de los arrays
multidimensionales es igual que la de los arrays unidimensionales.
Para que una función retorne un array multidimensional, se hace igual que en arrays unidimensionales. Simplemente hay que poner el tipo de
dato seguido del número de corchetes correspondiente, según el número de dimensiones del array. Eso claro, hay que ponerlo en la definición
del método:

También se puede inicializar un array multidimensional usando las llaves, poniendo después de la declaración del array un símbolo de igual, y
encerrado entre llaves los diferentes valores del array separados por comas, con la salvedad de que hay que poner unas llaves nuevas cada vez
que haya que poner los datos de una nueva dimensión, lo mejor es verlo con un ejemplo:
El primer array anterior sería un array de 4 por 3 y el siguiente sería un array de 2x2x2. Como puedes observar esta notación a partir de 3
dimensiones ya es muy liosa y normalmente no se usa. Utilizando esta notación también podemos inicializar rápidamente arrays irregulares,
simplemente poniendo separados por comas los elementos que tiene cada dimensión:
Es posible que en algunos libros y en Internet se re!eran a los arrays usando otra terminología. A los arrays unidimensionales es común
llamarlos también arreglos arreglos o vectores vectores, a los arrays de dos dimensiones es común llamarlos directamente matrices matrices, y a los arrays de más de
dos dimensiones es posible que los veas escritos como matrices multidimensionales matrices multidimensionales. Sea como sea, lo más normal en la jerga informática es
llamarlos arrays, término que procede del inglés.


Autoevaluación
Dado el siguiente array: Dado el siguiente array: int[][][] i3d={{{0,1},{0,2}}, {{0,1,3}},{{0,3,4},{0,1,5}}};
¿Cuál es el valor de la posición [1][1][2]? ¿Cuál es el valor de la posición [1][1][2]?
 3 
 4 
 5 
 Ninguno de los anteriores. 
Para saber más Para saber más
Las matrices tienen asociadas un amplio abanico de operaciones (transposición, suma, producto, etc.). En la siguiente página tienes ejemplos de
como realizar algunas de estas operaciones, usando por supuesto arrays:



ARRAYS.BINARYSEARCH()

//Arrays.binarySearch método que se usa para buscar un elemento en un array
            int pos = Arrays.binarySearch(this.tvalores, 0, this.valoresAlmacenados, num);
            if (pos < 0) {
                pos = pos * -1 - 1;
            }

