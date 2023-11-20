# FUNDAMENTOS DE C\#

 Universidad de las Fuerzas Armadas ESPE

 Materia: Web Avanzada

 NRC: 14956

 Autor: Alexander David Guacán Rivera

 Fecha: 19 de Noviembre 2023

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
    class YourClass
    {
    }

    struct YourStruct
    {
    }

    interface IYourInterface
    {
    }

    delegate int YourDelegate();

    enum YourEnum
    {
    }

    namespace YourNestedNamespace
    {
        struct YourStruct
        {
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
    class YourClass
    {
    }

    struct YourStruct
    {
    }

    interface IYourInterface
    {
    }

    delegate int YourDelegate();

    enum YourEnum
    {
    }

    namespace YourNestedNamespace
    {
        struct YourStruct
        {
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
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

void DisplayWeatherReport(double tempInCelsius)
{
    if (tempInCelsius < 20.0)
    {
        Console.WriteLine("Cold.");
    }
    else
    {
        Console.WriteLine("Perfect!");
    }
}
````

 Una instrucción if sin una parte else ejecuta el cuerpo solo si una expresión booleana se evalúa como true.

````C#
DisplayMeasurement(45);  // Output: The measurement value is 45
DisplayMeasurement(-3);  // Output: Warning: not acceptable value! The measurement value is -3

void DisplayMeasurement(double value)
{
    if (value < 0 || value > 100)
    {
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

void DisplayMeasurement(double measurement)
{
    switch (measurement)
    {
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
while (n < 5)
{
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
