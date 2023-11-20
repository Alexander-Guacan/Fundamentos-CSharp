# FUNDAMENTOS DE C\#

 Universidad de las Fuerzas Armadas ESPE

 Materia: Web Avanzada

 NRC: 14956

 Autor: Alexander David Guacán Rivera

 Fecha: 19 de Noviembre 2023

 Github: <https://github.com/Alexander-Guacan/Fundamentos-CSharp.git>

## Introducción a C\#

### ¿Qué es C#?

 Es un lenguaje de programación multiparadigma desarrollado y estandarizado por la empresa Microsoft como parte de su plataforma .NET, que después fue aprobado como un estándar por la ECMA (ECMA-334) e ISO (ISO/IEC 23270). C# es uno de los lenguajes de programación diseñados para la infraestructura de lenguaje común.

### Historia y evolución

 Andrés Hejlsberg decidió formar un equipo de trabajo en 1999 para crear un nuevo lenguaje de programación, que hoy conocemos como C#. En cambio, en sus inicios el nombre inicial que se barajó fue Cool (C Object Oriented Language), lo que en español traduciríamos con un lenguaje de programación orientado a objetivos.

 C# tiene sus orígenes en la familia de lenguajes C y su primera versión, tal y como explica Microsoft, se parecía mucho a Java. De hecho, se creó con el fin de ser una alternativa viable en este en Windows. Muchas de sus características fueron evolucionando y mejorando hasta llegar a la versión actual.

 Por ejemplo, ahora el lenguaje de C# admite los conceptos de encapsulación, herencia y polimorfismo y facilita el desarrollo de componentes de software mediante varias construcciones de lenguaje innovadoras..

### Plataformas compatibles

 Aunque C# forma parte de la plataforma .NET, esta es una API, mientras que C# es un lenguaje de programación independiente diseñado para generar programas sobre dicha plataforma. Ya existe un compilador implementado que provee el marco Mono - DotGNU, el cual genera programas para distintas plataformas como Microsoft Windows, Unix, Android, iOS, Windows Phone, Mac OS y GNU/Linux.

## Configuración del entorno de desarrollo

### Instalación de Visual Studio

 1. [Descargar](https://visualstudio.microsoft.com/es/free-developer-offers/) Visual Studio.
 2. Abrir instalador de Visual Studio.
 ![instalador-vs](https://learn.microsoft.com/es-es/visualstudio/install/media/vs-2022/privacy-and-license-terms.png?view=vs-2022)
 3. Elegir cargas de trabajo (workloads).
 ![workloads-vs](https://learn.microsoft.com/es-es/visualstudio/install/media/vs-2022/vs-installer-workloads.png?view=vs-2022)
    - .NET desktop development.
    - Universal Windows Platform development.
    - ASP.NET and web development.
    - Azure development.
 4. Elegir componentes adicionales (opcional).
 ![components-vs](https://learn.microsoft.com/es-es/visualstudio/install/media/vs-2022/vs-installer-individual-components.png?view=vs-2022)
 5. Instalar paquetes de idioma (opcional).
 ![idioms-vs](https://learn.microsoft.com/es-es/visualstudio/install/media/vs-2022/vs-installer-language-packs.png?view=vs-2022)
 6. Seleccionar ubicación de instalación (opcional).
 ![folder-installer-vs](https://learn.microsoft.com/es-es/visualstudio/install/media/vs-2022/vs-installer-installation-locations.png?view=vs-2022)

### Configuración del entorno de desarrollo con Azure

 Al depurar aplicaciones a través de Visual Studio, Visual Studio puede usar su cuenta de Azure para autenticarse y acceder a los recursos de Azure. Esta cuenta también se usa cuando se publican aplicaciones directamente desde Visual Studio en Azure.

 Para autenticar su cuenta de Azure desde Visual Studio, seleccione el menú Herramientas>Opciones para iniciar el cuadro de diálogo Opciones. Vaya a las opciones de autenticación del servicio de Azure e inicie sesión con su cuenta de Azure.

 ![azure-service-authentication](https://learn.microsoft.com/es-es/dotnet/azure/media/visual-studio-azure-login-dialog.png)

## Sintaxis básica de C\#

### Estructura de un programa en C\#

 Los programas de C# constan de uno o más archivos. Cada archivo contiene cero o más espacios de nombres. Un espacio de nombres contiene tipos como clases, estructuras, interfaces, enumeraciones y delegados, u otros espacios de nombres. El siguiente ejemplo es el esqueleto de un programa de C# que contiene todos estos elementos.

 ```C#
// A skeleton of a C# program
using System;

// Your program starts here:
Console.WriteLine("Hello world!");

namespace YourNamespace
{
    class YourClass {
    }

    struct YourStruct {
    }

    interface IYourInterface {
    }

    delegate int YourDelegate();

    enum YourEnum {
    }

    namespace YourNestedNamespace {
        struct YourStruct {
        }
    }
}
 ```

 En el ejemplo anterior se usan instrucciones de nivel superior para el punto de entrada del programa. Esta característica se agregó en C# 9. Antes de C# 9, el punto de entrada era un método estático denominado Main, como se muestra en el ejemplo siguiente:

 ```C#
 // A skeleton of a C# program
using System;
namespace YourNamespace
{
    class YourClass {
    }

    struct YourStruct {
    }

    interface IYourInterface {
    }

    delegate int YourDelegate();

    enum YourEnum {
    }

    namespace YourNestedNamespace {
        struct YourStruct {
        }
    }

    class Program {
        static void Main(string[] args) {
            //Your program starts here...
            Console.WriteLine("Hello world!");
        }
    }
}
 ```

### Tipos de datos

#### Tipos por valor

 Los tipos de valor son aquellos que almacenan directamente el valor en la memoria. Al asignar un tipo de valor a otro, se crea una copia independiente del valor.

- Tipos numéricos: enteros, flotantes y decimales.
- Tipo bool: representa valores verdadero o falso.
- Tipos de enumeración: colecciones de constantes con nombres.
- Estructuras: agrupaciones de variables relacionadas.

##### Tipos numéricos

###### Enteros

 Los enteros son números sin parte decimal. En C#, hay varios tipos de enteros según el tamaño y el rango de valores que pueden representar. Estos incluyen:

- byte: 8 bits, sin signo (0 a 255)
- sbyte: 8 bits, con signo (-128 a 127)
- short: 16 bits, con signo (-32,768 a 32,767)
- ushort: 16 bits, sin signo (0 a 65,535)
- int: 32 bits, con signo (-2,147,483,648 a 2,147,483,647)
- uint: 32 bits, sin signo (0 a 4,294,967,295)
- long: 64 bits, con signo (-9,223,372,036,854,775,808 a 9,223,372,036,854,775,807)
- ulong: 64 bits, sin signo (0 a 18,446,744,073,709,551,615)

###### Flotantes y decimales

 Los números flotantes y decimales representan valores con partes enteras y fraccionarias. En C#, hay tres tipos principales:

- float: 32 bits, precisión simple (±1.5 × 10⁻⁴⁵ a ±3.4 × 10³⁸)
- double: 64 bits, precisión doble (±5.0 × 10⁻³²⁴ a ±1.7 × 10³⁰⁸)
- decimal: 128 bits, alta precisión (±1.0 × 10⁻²⁸ a ±7.9 × 10²⁸)

 Los tipos float y double son ideales para cálculos que no requieren alta precisión, como gráficos o simulaciones. El tipo decimal es adecuado para operaciones financieras y matemáticas que requieren máxima precisión.

###### Tipos bool y de enumeración

- Tipo bool: El tipo bool representa valores booleanos true (verdadero) y false (falso). Es comúnmente utilizado en estructuras de control y comparaciones.

 ````C#
bool esVerdadero = true;
bool esFalso = false;
 ````

- Tipos de enumeración: Las enumeraciones son conjuntos de constantes con nombres que representan valores numéricos. Permiten organizar y mejorar la legibilidad del código. Para crear una enumeración, se utiliza la palabra clave **enum**.

 ````C#
enum DiasSemana { Lunes, Martes, Miercoles, Jueves, Viernes, Sabado, Domingo }
 ````

#### Tipos por referencia

 Los tipos de referencia almacenan la dirección de memoria donde se encuentra el valor. Al asignar un tipo de referencia a otro, ambas variables apuntan al mismo objeto en memoria. Los tipos de referencia incluyen:

- Cadenas de caracteres: secuencias de caracteres Unicode.
- Arreglos: colecciones de elementos del mismo tipo.
- Clases: plantillas para crear objetos.
- Delegados: referencias a métodos con una firma específica.
- Interfaces: contratos que definen un conjunto de miembros.

### Variables

 Las variables representan ubicaciones de almacenamiento. Cada variable tiene un tipo que determina qué valores se pueden almacenar en la variable. C# es un lenguaje con seguridad de tipos y el compilador de C# garantiza que los valores almacenados en variables siempre sean del tipo adecuado.

#### Variables estáticas

 Un campo declarado con el static modificador se denomina variable estática. Una variable estática entra en vigor antes de la ejecución del constructor estático(constructores estáticos) para su tipo de contenido y deja de existir cuando el dominio de aplicación asociado deja de existir.

#### Variables de instancia

 Un campo declarado sin el static modificador se denomina variable de instancia.

##### Variables de instancia en clases

 Una variable de instancia de una clase entra en vigor cuando se crea una nueva instancia de esa clase y deja de existir cuando no hay referencias a esa instancia y se ha ejecutado el destructor de la instancia (si existe).
 El valor inicial de una variable de instancia de una clase es el valor predeterminado (valores predeterminados) del tipo de la variable.

##### Variables de instancia en estructuras

 Una variable de instancia de un struct tiene exactamente la misma duración que la variable de estructura a la que pertenece. En otras palabras, cuando una variable de un tipo de estructura entra en existencia o deja de existir, también lo hacen las variables de instancia de la estructura .

 El estado de asignación inicial de una variable de instancia de un struct es el mismo que el de la variable de estructura contenedora. En otras palabras, cuando una variable de estructura se considera asignada inicialmente, también lo son sus variables de instancia y, cuando una variable de estructura se considera inicialmente sin asignar, sus variables de instancia tampoco tienen asignación.

#### Elementos de matriz

 Los elementos de una matriz se crean cuando se crea una instancia de matriz y dejan de existir cuando no hay referencias a esa instancia de matriz.
 El valor inicial de cada uno de los elementos de una matriz es el valor predeterminado (Valores predeterminados) del tipo de los elementos de la matriz.

#### Parámetros de valor

 Un parámetro declarado sin un ref modificador o es un parámetro de out valor.

 Un parámetro de valor entra en vigor tras la invocación del miembro de función (método, constructor de instancia, accessor u operador) o de la función anónima a la que pertenece el parámetro, y se inicializa con el valor del argumento proporcionado en la invocación. Normalmente, un parámetro de valor deja de existir al devolver el miembro de función o la función anónima. Sin embargo, si una función anónima captura el parámetro value (expresiones de funciónanónimas),su duración se extiende al menos hasta que el delegado o el árbol de expresión creado a partir de esa función anónima sea apto para la recolección de elementos no utilizados.

#### Parámetros de referencia

 Un parámetro declarado con un ref modificador es un parámetro de referencia.
 Un parámetro de referencia no crea una nueva ubicación de almacenamiento. En su lugar, un parámetro de referencia representa la misma ubicación de almacenamiento que la variable especificada como argumento en el miembro de función o la invocación de función anónima. Por lo tanto, el valor de un parámetro de referencia siempre es el mismo que la variable subyacente.

 Una variable debe asignarse definitivamente antes de que se pueda pasar como parámetro de referencia en una invocación de delegado o miembro de función.

#### Parámetros de salida

 Un parámetro declarado con un out modificador es un parámetro de salida.
 Un parámetro de salida no crea una nueva ubicación de almacenamiento. En su lugar, un parámetro de salida representa la misma ubicación de almacenamiento que la variable especificada como argumento en la invocación de delegado o miembro de función. Por lo tanto, el valor de un parámetro de salida siempre es el mismo que la variable subyacente.

#### Variables locales

 Una variable local _se declara mediante un_local_variable_declaration, que puede producirse en un bloque , un for_statement , un switch_statement o un using_statement; o por un foreach_statement o un specific_catch_clause para un try_statement.

### Operadores básicos

 C# proporciona una serie de operadores. Muchos de ellos son compatibles con los tipos integrados y permiten realizar operaciones básicas con valores de esos tipos. Entre estos operadores se incluyen los siguientes grupos:

#### Operadores aritméticos

 Que realizan operaciones aritméticas con operandos numéricos.

 | Nombre | Simbolo | Tipo |
 |--------|---------|------|
 | Incremento | ++ | Unario|
 | Decremento | -- | Unario |
 | Más | + | Unario |
 | Menos | - | Unario |
 | Suma | + | Binario |
 | Resta | - | Binario |
 | Multiplicación | * | Binario |
 | División | / | Binario |
 | Modulo | % | Binario |
 | Asignación compuesta | +=, -=, *=, /=, %= | Binario|

#### Operadores de comparación

 Que comparan operandos numéricos, debido a esta característica, todos los operadores son binarios.

 | Nombre | Simbolo |
 |--------|---------|
 | Menor que | < |
 | Mayor que | > |
 | Igual que | == |
 | Menor o igual que | <= |
 | Mayor o igual que | >= |

#### Operadores lógicos booleanos

 Que realizan operaciones lógicas con operandos bool.

 | Nombre | Simbolo | Descripción |
 |--------|---------|-------------|
 | Negación lógico | ! | Calcula la negación lógica de su operando. Es decir, genera true, si el operando se evalúa como false, y false, si el operando se evalúa como true |
 | AND lógico | & | El operador & evalúa ambos operandos, incluso aunque el izquierdo se evalúe como false, para que el resultado de la operación sea false con independencia del valor del operando derecho. |
 | IR exclusivo lógico | ^ | Calcula el operador OR exclusivo lógica, también conocido como el operador XOR lógico, de sus operandos. El resultado de x ^ y es true si x se evalúa como true y y se evalúa como false o x se evalúa como false y y se evalúa como true. |
 | OR lógico | \| | El operador | evalúa ambos operandos, incluso aunque el izquierdo se evalúe como true, para que el resultado de la operación sea true con independencia del valor del operando derecho. |
 | AND lógico condicional | && | Calcula el operador AND lógico de sus operandos. El resultado de x && y es true si x y y se evalúan como true. De lo contrario, el resultado es false. Si x se evalúa como false, y no se evalúa. |
 | OR lógico condicional | \|\| | Calcula el operador OR lógico de sus operandos. El resultado de x || y es true si x o y se evalúan como true. De lo contrario, el resultado es false. Si x se evalúa como true, y no se evalúa. |

#### Operadores bit a bit y de desplazamiento

 Que realizan operaciones bit a bit o de desplazamiento con operandos de tipos enteros.

 | Nombre | Simbolo | Descripción |
 |--------|---------|-------------|
 | Complemento bit a bit | ! | Genera un complemento bit a bit de su operando al invertir cada bit. |
 | Desplazamiento izquierdo | << | desplaza el operando izquierdo a la izquierda el número de bits definido por el operando derecho. |
 | Desplazamiento derecho | >> | desplaza el operando izquierdo a la derecha el número de bits definido por el operando derecho. |
 | Desplazamiento derecho sin signo | >>> | Disponible en C# 11 y posteriores, el >>> operador desplaza el operando izquierdo a la derecha el número de bits definido por su operando derecho. |

### Control de flujo y estructuras de control

#### Instrucciones de selección (Condicionales)

 Permiten crear bifurcaciones a diferentes secciones de código, en función de una o varias condiciones especificadas.

##### Instrucción **If**

 Una instrucción if con una parte else selecciona una de las dos instrucciones que se ejecutarán en función del valor de una expresión booleana.

````C#
DisplayWeatherReport(15.0);  // Output: Cold.
DisplayWeatherReport(24.0);  // Output: Perfect!

void DisplayWeatherReport(double tempInCelsius) {
    if (tempInCelsius < 20.0) {
        Console.WriteLine("Cold.");
    } else {
        Console.WriteLine("Perfect!");
    }
}
````

 Una instrucción if sin una parte else ejecuta el cuerpo solo si una expresión booleana se evalúa como true.

````C#
DisplayMeasurement(45);  // Output: The measurement value is 45
DisplayMeasurement(-3);  // Output: Warning: not acceptable value! The measurement value is -3

void DisplayMeasurement(double value) {
    if (value < 0 || value > 100) {
        Console.Write("Warning: not acceptable value! ");
    }

    Console.WriteLine($"The measurement value is {value}");
}
````

##### Instrucción **switch**

 La instrucción switch selecciona una lista de instrucciones para ejecutarla en función de la coincidencia de un patrón con una expresión de coincidencia.

````C#
DisplayMeasurement(-4);  // Output: Measured value is -4; too low.
DisplayMeasurement(5);  // Output: Measured value is 5.
DisplayMeasurement(30);  // Output: Measured value is 30; too high.
DisplayMeasurement(double.NaN);  // Output: Failed measurement.

void DisplayMeasurement(double measurement) {
    switch (measurement) {
        case < 0.0:
            Console.WriteLine($"Measured value is {measurement}; too low.");
            break;

        case > 15.0:
            Console.WriteLine($"Measured value is {measurement}; too high.");
            break;

        case double.NaN:
            Console.WriteLine("Failed measurement.");
            break;

        default:
            Console.WriteLine($"Measured value is {measurement}.");
            break;
    }
}
````

#### Instrucción de iteración (Bucles)

##### Instrucción **do**

 La instrucción do ejecuta una instrucción o un bloque de instrucciones mientras que una expresión booleana especificada se evalúa como true. Como esa expresión se evalúa después de cada ejecución del bucle, un bucle do se ejecuta una o varias veces.

````C#
int n = 0;

do {
    Console.Write(n);
    n++;
} while (n < 5);

// Output:
// 01234
````

##### Instrucción **while**

 La instrucción while ejecuta una instrucción o un bloque de instrucciones mientras que una expresión booleana especificada se evalúa como true. Como esa expresión se evalúa antes de cada ejecución del bucle, un bucle while se ejecuta cero o varias veces.

````C#
int n = 0;
while (n < 5) {
    Console.Write(n);
    n++;
}
// Output:
// 01234
````

##### Instrucción for

 La instrucción for ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como true. En el ejemplo siguiente se muestra la instrucción for

````C#
for (int i = 0; i < 3; i++) {
    Console.Write(i);
}
// Output:
// 012

````

##### Instrucción **foreach**

 La instrucción foreach ejecuta una instrucción o un bloque de instrucciones para cada elemento de una instancia del tipo que implementa la interfaz System.Collections.IEnumerable o System.Collections.Generic.IEnumerable\<T>

````C#
var fibNumbers = new List<int> { 0, 1, 1, 2, 3, 5, 8, 13 };

foreach (int element in fibNumbers) {
    Console.Write($"{element} ");
}
// Output:
// 0 1 1 2 3 5 8 13

````

## Funciones y métodos

 Un método es un bloque de código que contiene una serie de instrucciones. Un programa hace que se ejecuten las instrucciones al llamar al método y especificando los argumentos de método necesarios. En C#, todas las instrucciones ejecutadas se realizan en el contexto de un método.

### Declaración y llamada de funciones

 Los métodos se declaran en una clase, struct o interfaz especificando el nivel de acceso, como public o private, modificadores opcionales como abstract o sealed, el valor devuelto, el nombre del método y cualquier parámetro de método. Todas estas partes forman la firma del método.

 Los parámetros de método se encierran entre paréntesis y se separan por comas. Los paréntesis vacíos indican que el método no requiere parámetros.

````C#
abstract class Motorcycle {
    // Anyone can call this.
    public void StartEngine() {/* Method statements here */ }

    // Only derived classes can call this.
    protected void AddGas(int gallons) { /* Method statements here */ }

    // Derived classes can override the base class implementation.
    public virtual int Drive(int miles, int speed) { /* Method statements here */ return 1; }

    // Derived classes must implement this.
    public abstract double GetTopSpeed();
}
````

### Parámetros y argumentos

 La definición del método especifica los nombres y tipos de todos los parámetros necesarios. Si el código de llamada llama al métodos, proporciona valores concretos denominados argumentos para cada parámetro. Los argumentos deben ser compatibles con el tipo de parámetro, pero el nombre del argumento (si existe) utilizado en el código de llamada no tiene que ser el mismo que el parámetro con nombre definido en el método.

````C#
public void Caller() {
    int numA = 4;
    // Call with an int variable.
    int productA = Square(numA);

    int numB = 32;
    // Call with another int variable.
    int productB = Square(numB);

    // Call with an integer literal.
    int productC = Square(12);

    // Call with an expression that evaluates to int.
    productC = Square(productA * 3);
}

int Square(int i) {
    // Store input argument in a local variable.
    int input = i;
    return input * input;
}
````

### Pasar por referencia frente a pasar por valor

 Cuando se pasa un objeto de un tipo de referencia a un método, se pasa una referencia al objeto. Es decir, el método no recibe el objeto concreto, recibe un argumento que indica la ubicación del objeto. Si cambia un miembro del objeto mediante esta referencia, el cambio se refleja en el argumento del método de llamada, incluso si pasa el objeto por valor.

### Retorno de valores

 Los métodos pueden devolver un valor al autor de llamada. Si el tipo de valor devuelto (el tipo que aparece antes del nombre de método) no es void, el método puede devolver el valor mediante la instrucción return. Una instrucción con la palabra clave return seguida de un valor que coincide con el tipo de valor devuelto devolverá este valor al autor de llamada del método.

 El valor se puede devolver al autor de la llamada por valor o por referencia. Los valores se devuelven al autor de la llamada mediante referencia si la palabra clave ref se usa en la firma del método y sigue cada palabra clave return. Por ejemplo, la siguiente firma del método y la instrucción return indican que el método devuelve una variable denominada estDistance mediante referencia al autor de la llamada.

````C#
public ref double GetEstimatedDistance() {
    return ref estDistance;
}
````

 La palabra clave return también detiene la ejecución del método. Si el tipo de valor devuelto es void, una instrucción return sin un valor también es útil para detener la ejecución del método. Sin la palabra clave return , el método dejará de ejecutarse cuando alcance el final del bloque de código. Los métodos con un tipo de valor devuelto no nulo son necesarios para usar la palabra clave return para devolver un valor.

## Estructura de datos básica

### Matrices

 Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz. Puede declarar una matriz mediante la especificación del tipo de sus elementos.

````C#
type[] arrayName;
````

#### Propiedades de las matrices

- Una matriz puede ser unidimensional, multidimensional o escalonada.
- El número de dimensiones se establece cuando se declara una variable de la matriz. La longitud de cada dimensión se establece cuando se crea la instancia de la matriz. No se pueden cambiar estos valores durante la vigencia de la instancia.
- Una matriz escalonada es una matriz de matrices y cada matriz miembro tiene el valor predeterminado de **null**.
- Las matrices se indexan con cero: una matriz con **n** elementos se indexa de **0** a **n-1**.
- Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.
- Los tipos de matriz son tipos de referencia que proceden del tipo base abstracto Array. Todas las matrices implementan IList y IEnumerable. Puede usar la instrucción foreach para recorrer en iteración una matriz. Las matrices de dimensión única también implementan IList\<T> y IEnumerable\<T>.

````C#
// Declare a single-dimensional array of 5 integers.
int[] array1 = new int[5];

// Declare and set array element values.
int[] array2 = [1, 2, 3, 4, 5, 6];

// Declare a two dimensional array.
int[,] multiDimensionalArray1 = new int[2, 3];

// Declare and set array element values.
int[,] multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

// Declare a jagged array.
int[][] jaggedArray = new int[6][];

// Set the values of the first array in the jagged array structure.
jaggedArray[0] = [1, 2, 3, 4];
````

### Listas

 Las colecciones proporcionan una manera flexible de trabajar con grupos de objetos. Puede clasificar las distintas colecciones en función de estas características:

- Acceso a elementos: cada colección se puede enumerar para acceder a cada elemento en orden. Algunas colecciones acceden a elementos mediante el índice, la posición del elemento en una colección ordenada. El ejemplo más común es System.Collections.Generic.List\<T>. Otras colecciones acceden a los elementos mediante la clave, donde un valor está asociado a una sola clave. El ejemplo más común es System.Collections.Generic.Dictionary\<TKey,TValue>. Elige entre estos tipos de colección en función de cómo la aplicación accede a los elementos.
- Perfil de rendimiento: cada colección tiene perfiles de rendimiento diferentes para acciones como agregar un elemento, buscar un elemento o quitar un elemento. Puede elegir un tipo de colección en función de las operaciones que se usan más en la aplicación.
- Aumentar y reducir dinámicamente: la mayoría de las colecciones admiten la adición o eliminación de elementos de forma dinámica. En particular, Array, System.Span\<T> y System.Memory\<T> no lo hacen.

````C#
// Create a list of strings by using a
// collection initializer.
List<string> salmons = ["chinook", "coho", "pink", "sockeye"];

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye

// Remove an element from the list by specifying
// the object.
salmons.Remove("coho");


// Iterate using the index:
for (var index = 0; index < salmons.Count; index++)
{
    Console.Write(salmons[index] + " ");
}
// Output: chinook pink sockeye

// Add the removed element
salmons.Add("coho");
// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook pink sockeye coho
````

### Diccionarios

 Una colección de diccionarios permite acceder a los elementos de la colección mediante la clave de cada elemento. Cada adición al diccionario consta de un valor y de su clave asociada. En el ejemplo siguiente se crea una colección Dictionary y se recorre en iteración el diccionario usando una instrucción foreach.

````C#
private static void IterateThruDictionary() {
    Dictionary<string, Element> elements = BuildDictionary();

    foreach (KeyValuePair<string, Element> kvp in elements) {
        Element theElement = kvp.Value;

        Console.WriteLine("key: " + kvp.Key);
        Console.WriteLine("values: " + theElement.Symbol + " " +
            theElement.Name + " " + theElement.AtomicNumber);
    }
}

public class Element {
    public required string Symbol { get; init; }
    public required string Name { get; init; }
    public required int AtomicNumber { get; init; }
}

private static Dictionary<string, Element> BuildDictionary() => new () {
    { "K", new (){ Symbol="K", Name="Potassium", AtomicNumber=19 } },
    { "Ca", new (){ Symbol="Ca", Name="Calcium", AtomicNumber=20 } },
    { "Sc", new (){ Symbol="Sc", Name="Scandium", AtomicNumber=21 } },
    { "Ti", new (){ Symbol="Ti", Name="Titanium", AtomicNumber=22 } }
};
````

## Programación Orientada a Objetos (POO)

### Clases y objetos

#### Declarar clases

 Las clases se declaran mediante la palabra clave class seguida por un identificador único.

````C#
//[access modifier] - [class] - [identifier]
public class Customer {
   // Fields, properties, methods and events go here...
}
````

 Un modificador de acceso opcional precede a la palabra clave class. Como en este caso se usa public, cualquier usuario puede crear instancias de esta clase. El nombre de la clase sigue a la palabra clave class. El nombre de la clase debe ser un nombre de identificador de C# válido. El resto de la definición es el cuerpo de la clase, donde se definen los datos y el comportamiento. Los campos, las propiedades, los métodos y los eventos de una clase se denominan de manera colectiva miembros de clase.

#### Creación de objetos

 Aunque a veces se usan indistintamente, una clase y un objeto son cosas diferentes. Una clase define un tipo de objeto, pero no es un objeto en sí. Un objeto es una entidad concreta basada en una clase y, a veces, se conoce como una instancia de una clase. Se pueden crear objetos usando la palabra clave **new** seguida del nombre de la clase.

````C#
Customer object1 = new Customer();
````

### Herencia

 La herencia, junto con la encapsulación y el polimorfismo, es una de las tres características principales de la programación orientada a objetos. La herencia permite crear clases que reutilizan, extienden y modifican el comportamiento definido en otras clases. La clase cuyos miembros se heredan se denomina clase base y la clase que hereda esos miembros se denomina clase derivada. Una clase derivada solo puede tener una clase base directa, pero la herencia es transitiva. Si ClassC se deriva de ClassB y ClassB se deriva de ClassA, ClassC hereda los miembros declarados en ClassB y ClassA.

 En la ilustración siguiente se muestra una clase WorkItem que representa un elemento de trabajo de un proceso empresarial. Como con todas las clases, se deriva de System.Object y hereda todos sus métodos. WorkItem agrega seis miembros propios. Estos miembros incluyen un constructor, porque los constructores no se heredan. La clase ChangeRequest hereda de WorkItem y representa un tipo concreto de elemento de trabajo. ChangeRequest agrega dos miembros más a los miembros que hereda de WorkItem y de Object. Debe agregar su propio constructor y además agrega originalItemID. La propiedad originalItemID permite que la instancia ChangeRequest se asocie con el WorkItem original al que se aplica la solicitud de cambio.

 ![class-diagram-inherit](https://learn.microsoft.com/es-es/dotnet/csharp/fundamentals/object-oriented/media/inheritance/class-inheritance-diagram.png)

 En el ejemplo siguiente se muestra cómo se expresan en C# las relaciones de clase de la ilustración anterior. En el ejemplo también se muestra cómo WorkItem reemplaza el método virtual Object.ToString y cómo la clase ChangeRequest hereda la implementación WorkItem del método.

````C#
// WorkItem implicitly inherits from the Object class.
public class WorkItem {
    // Static field currentID stores the job ID of the last WorkItem that
    // has been created.
    private static int currentID;

    //Properties.
    protected int ID { get; set; }
    protected string Title { get; set; }
    protected string Description { get; set; }
    protected TimeSpan jobLength { get; set; }

    // Default constructor. If a derived class does not invoke a base-
    // class constructor explicitly, the default constructor is called
    // implicitly.
    public WorkItem() {
        ID = 0;
        Title = "Default title";
        Description = "Default description.";
        jobLength = new TimeSpan();
    }

    // Instance constructor that has three parameters.
    public WorkItem(string title, string desc, TimeSpan joblen) {
        this.ID = GetNextID();
        this.Title = title;
        this.Description = desc;
        this.jobLength = joblen;
    }

    // Static constructor to initialize the static member, currentID. This
    // constructor is called one time, automatically, before any instance
    // of WorkItem or ChangeRequest is created, or currentID is referenced.
    static WorkItem() => currentID = 0;

    // currentID is a static field. It is incremented each time a new
    // instance of WorkItem is created.
    protected int GetNextID() => ++currentID;

    // Method Update enables you to update the title and job length of an
    // existing WorkItem object.
    public void Update(string title, TimeSpan joblen)
    {
        this.Title = title;
        this.jobLength = joblen;
    }

    // Virtual method override of the ToString method that is inherited
    // from System.Object.
    public override string ToString() =>
        $"{this.ID} - {this.Title}";
}

// ChangeRequest derives from WorkItem and adds a property (originalItemID)
// and two constructors.
public class ChangeRequest : WorkItem
{
    protected int originalItemID { get; set; }

    // Constructors. Because neither constructor calls a base-class
    // constructor explicitly, the default constructor in the base class
    // is called implicitly. The base class must contain a default
    // constructor.

    // Default constructor for the derived class.
    public ChangeRequest() { }

    // Instance constructor that has four parameters.
    public ChangeRequest(string title, string desc, TimeSpan jobLen, int originalID) {
        // The following properties and the GetNexID method are inherited
        // from WorkItem.
        this.ID = GetNextID();
        this.Title = title;
        this.Description = desc;
        this.jobLength = jobLen;

        // Property originalItemID is a member of ChangeRequest, but not
        // of WorkItem.
        this.originalItemID = originalID;
    }
}
````

 En el bloque siguiente se muestra cómo usar las clases base y derivadas:

````C#
// Create an instance of WorkItem by using the constructor in the
// base class that takes three arguments.
WorkItem item = new WorkItem("Fix Bugs", "Fix all bugs in my code branch", new TimeSpan(3, 4, 0, 0));

// Create an instance of ChangeRequest by using the constructor in
// the derived class that takes four arguments.
ChangeRequest change = new ChangeRequest("Change Base Class Design", "Add members to the class", new TimeSpan(4, 0, 0), 1);

// Use the ToString method defined in WorkItem.
Console.WriteLine(item.ToString());

// Use the inherited Update method to change the title of the
// ChangeRequest object.
change.Update("Change the Design of the Base Class", new TimeSpan(4, 0, 0));

// ChangeRequest inherits WorkItem's override of ToString.
Console.WriteLine(change.ToString());
/* Output:
    1 - Fix Bugs
    2 - Change the Design of the Base Class
*/
````

### Encapsulamiento

 La encapsulacion esta implementada por modificadores de acceso y estos seran los encargados de definir el rango y la visibilidad de los miembros de la clase.

- public: permitira exponer todos los miembros que definamos de esta manera, estos pueden ser tanto metodos (funciones) como propiedades (variables) dentro de las clases y las mismas podran ser accedidas desde afuera de la misma.
- private: permite a una clase hacer todo lo contrario a la anterior, es decir que permite denegar el acceso a las propiedades y metodos desde otros objetos o clases, y estos elementos solo pueden ser accedidos por miembros dentro de la misma clase, inclusive una instancia de la misma clase no podria acceder.
- protected: es mas utilizado para cuando tenemos clases heredadas, dado que trabaja como public para las clase hijas de la clase base y como private para las clases externas a la misma.
- internal: es el predeterminado cuando no informamos ninguno, este nos permite al igual que public exponer todos los metodos y propiedades de la clase dentro del mismo ensamblado (assembly), es decir que todas las clases podran tener acceso siempre y cuando esten dentro del mismo ensamblado.
- protected internal: es una mezcla entre el internal y el protected, porque ocultara a los miembros a las clases externas de esta pero si le permitira el acceso a las hijas de la clase base.

### Abstraccíón

#### Clases base abstractas

 Puede declarar una clase como abstracta si quiere impedir la creación directa de instancias mediante el operador new. Una clase abstracta solo se puede usar si a partir de ella se deriva una clase nueva. Una clase abstracta puede contener una o más firmas de método que, a su vez, se declaran como abstractas. Estas firmas especifican los parámetros y el valor devuelto, pero no tienen ninguna implementación (cuerpo del método). Una clase abstracta no tiene que contener miembros abstractos, pero si lo hace, la clase se debe declarar como abstracta. Las clases derivadas que no son abstractas deben proporcionar la implementación para todos los métodos abstractos de una clase base abstracta.

 Las clases se pueden declarar como abstractas si se incluye la palabra clave abstract antes de la definición de clase.

````C#
public abstract class A {
    // Class members here.
}
````

Las clases abstractas también pueden definir métodos abstractos. Esto se consigue agregando la palabra clave abstract antes del tipo de valor que devuelve el método.

````C#
public abstract class A {
    public abstract void DoWork(int i);
}
````

#### Interfaces

 Una interfaz es un tipo de referencia que define un conjunto de miembros. Todas las clases y estructuras que implementan esa interfaz deben implementar ese conjunto de miembros. Una interfaz puede definir una implementación predeterminada para todos o ninguno de estos miembros. Una clase puede implementar varias interfaces, aunque solo puede derivar de una única clase base directa.

````C#
interface ISampleInterface {
    void SampleMethod();
}

class ImplementationClass : ISampleInterface {
    // Explicit interface member implementation:
    void ISampleInterface.SampleMethod() {
        // Method implementation.
    }

    static void Main() {
        // Declare an interface instance.
        ISampleInterface obj = new ImplementationClass();

        // Call the member.
        obj.SampleMethod();
    }
}
````

### Polimorfismo

El polimorfismo suele considerarse el tercer pilar de la programación orientada a objetos, después de la encapsulación y la herencia. Polimorfismo es una palabra griega que significa "con muchas formas" y tiene dos aspectos diferentes:

- En tiempo de ejecución, los objetos de una clase derivada pueden ser tratados como objetos de una clase base en lugares como parámetros de métodos y colecciones o matrices. Cuando se produce este polimorfismo, el tipo declarado del objeto ya no es idéntico a su tipo en tiempo de ejecución.
- Las clases base pueden definir e implementar métodosvirtuales, y las clases derivadas pueden invalidarlos, lo que significa que pueden proporcionar su propia definición e implementación. En tiempo de ejecución, cuando el código de cliente llama al método, CLR busca el tipo en tiempo de ejecución del objeto e invoca esa invalidación del método virtual. En el código fuente puede llamar a un método en una clase base y hacer que se ejecute una versión del método de la clase derivada.

Los métodos virtuales permiten trabajar con grupos de objetos relacionados de manera uniforme. Por ejemplo, supongamos que tiene una aplicación de dibujo que permite a un usuario crear varios tipos de formas en una superficie de dibujo. En tiempo de compilación, no sabe qué tipos de formas en concreto creará el usuario. Sin embargo, la aplicación tiene que realizar el seguimiento de los distintos tipos de formas que se crean, y tiene que actualizarlos en respuesta a las acciones del mouse del usuario. Para solucionar este problema en dos pasos básicos, puede usar el polimorfismo:

1. Crear una jerarquía de clases en la que cada clase de forma específica deriva de una clase base común.
2. Usar un método virtual para invocar el método apropiado en una clase derivada mediante una sola llamada al método de la clase base.

Primero, cree una clase base llamada Shape y clases derivadas como Rectangle, Circle y Triangle. Dé a la clase Shape un método virtual llamado Draw e invalídelo en cada clase derivada para dibujar la forma determinada que la clase representa. Cree un objeto List\<Shape> y agréguele una instancia de Circle, Triangle y Rectangle.

````C#
public class Shape {
    // A few example members
    public int X { get; private set; }
    public int Y { get; private set; }
    public int Height { get; set; }
    public int Width { get; set; }

    // Virtual method
    public virtual void Draw() {
        Console.WriteLine("Performing base class drawing tasks");
    }
}

public class Circle : Shape {
    public override void Draw() {
        // Code to draw a circle...
        Console.WriteLine("Drawing a circle");
        base.Draw();
    }
}
public class Rectangle : Shape
{
    public override void Draw() {
        // Code to draw a rectangle...
        Console.WriteLine("Drawing a rectangle");
        base.Draw();
    }
}
public class Triangle : Shape
{
    public override void Draw() {
        // Code to draw a triangle...
        Console.WriteLine("Drawing a triangle");
        base.Draw();
    }
}
````

 Para actualizar la superficie de dibujo, use un bucle foreach para iterar por la lista y llamar al método Draw en cada objeto Shape de la lista. Aunque cada objeto de la lista tenga un tipo declarado de Shape, se invocará el tipo en tiempo de ejecución (la versión invalidada del método en cada clase derivada).

````C#
// Polymorphism at work #1: a Rectangle, Triangle and Circle
// can all be used wherever a Shape is expected. No cast is
// required because an implicit conversion exists from a derived
// class to its base class.
var shapes = new List<Shape> {
    new Rectangle(),
    new Triangle(),
    new Circle()
};

// Polymorphism at work #2: the virtual method Draw is
// invoked on each of the derived classes, not the base class.
foreach (var shape in shapes) {
    shape.Draw();
}

/* Output:
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
*/
````
