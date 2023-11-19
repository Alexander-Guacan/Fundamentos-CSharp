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
