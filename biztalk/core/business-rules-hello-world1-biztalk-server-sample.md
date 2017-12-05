---
title: Business Rules Hello World1 (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe9f04fc8dac06676d7f29bf5dd2ecd01e7a06c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a>Business Rules Hello World1 (ejemplo de BizTalk Server)
El ejemplo Business Rules Hello World1 muestra cómo crear un conjunto de reglas BizTalk, guardarlo en un archivo (SampleRuleSet.xml), cargarlo y ejecutarlo basado en un conjunto de ejemplos de hechos. El conjunto de reglas de ejemplos consta de una regla sencilla que implica a un elemento XML y objetos basados en .NET (propiedades y miembros) como términos de la definición de reglas.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se crea un ejecutable que realiza la secuencia de pasos siguiente:  
  
1.  Llama al método **CreateRuleset** para generar el conjunto de reglas descrito en la sección Comentarios.  
  
2.  Llama al método **SaveToFile** para mostrar cómo guardar un conjunto de reglas para un archivo.  
  
3.  Llama al método **LoadFromFile** para mostrar cómo cargar un conjunto de reglas de un archivo.  
  
4.  Construye hechos de prueba en los que se puede ejecutar el conjunto de reglas.  
  
5.  Ejecuta el conjunto de reglas en los hechos de prueba, que produce una presentación en la pantalla.  
  
6.  Pausa, le permite examinar el archivo de conjunto de reglas SampleRuleStore.xml.  
  
7.  Realiza una limpieza mediante la eliminación del archivo de conjunto de reglas en preparación de las ejecuciones posteriores del ejemplo.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*\>\Business Rules\Business reglas Hello World1\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln|Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que crea, guarda, carga y ejecuta un conjunto de reglas.|  
|HelloWorld1.cs|El archivo de Visual C# que contiene métodos para mostrar cómo se crea un conjunto de reglas, se guarda un conjunto de reglas en un archivo y se carga un conjunto de reglas desde un archivo. También contiene código adyacente que llama a estos métodos y, a continuación, ejecuta el conjunto de reglas creado.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|SampleDocumentInstance.xml|El archivo de entrada de ejemplo que se ajusta al esquema definido en el archivo SampleSchema.xsd.|  
|SampleSchema.xsd|El archivo de esquemas que define un esquema simple con un elemento al que hace referencia el conjunto de reglas creado en el archivo HelloWorld1.cs. de Visual C#.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta \MySampleLibrary:<br /><br /> AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln|Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que proporciona la clase que define los objetos a los que hace referencia el conjunto de reglas creado.|  
|En la carpeta \MySampleLibrary:<br /><br /> MySampleLibraryClass.cs|Archivo de Visual C# que contiene la propiedad que se hace referencia en el **IF** parte de la regla creada y el método que se puede llamar en el **, a continuación,** parte de la regla creada.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Use el siguiente procedimiento para generar e inicializar el ejemplo Business Rules Hello World1.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Business Rules\Business reglas Hello World1\  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] de Microsoft para este ejemplo.  
  
    > [!NOTE]
    >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
    > [!NOTE]
    >  Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Use el siguiente procedimiento para ejecutar el ejemplo Business Rules Hello World1.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Business Rules\Business reglas Hello World1\bin\Debug\  
  
2.  En la ventana de comandos, escriba el nombre del archivo ejecutable para este ejemplo (BusinessRulesHelloWorld1.exe) y, a continuación, presione ENTRAR.  
  
    > [!NOTE]
    >  Mientras se ejecuta, este ejemplo produce el conjunto de reglas de archivo SampleRuleStore.xml en la **bin\Debug** carpeta. Cuando se pausa el ejecutable y se espera a que presione ENTRAR para finalizar, puede examinar los contenidos de este archivo. Recuerde cerrarlo antes de presionar cualquier tecla para finalizar. En caso contrario, puede que el ejecutable no pueda quitarlo en preparación de las ejecuciones posteriores del ejemplo.  
  
 Según la naturaleza del conjunto de reglas creado, si ejecuta este ejemplo con el archivo de entrada de ejemplo proporcionado SampleDocumentInstance.xml, que tiene un valor de uno (1) definido para su **identificador** elemento, verá el siguiente resultado:  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
> [!NOTE]
>  El resultado que aparece en negrita, en el código anterior y en el código siguiente, el resultado generado por el objeto de negocio de ejemplo, definido por los archivos de la **MySampleLibrary** carpeta, que hace referencia el conjunto de reglas.  
  
 Si cambia el valor asociado a la **identificador** elemento en el archivo de entrada de ejemplo **SampleDocumentInstance.xml** de uno (1) a dos (2), el resultado cambiará como sigue:  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
 No obtendrá una línea de salida para los objetos de la **MySampleBusinessObject** clase que tienen sus **MyValue** propiedad establecida en un valor (durante la construcción) que coincide con el valor asociado a la  **Id. de** elemento en el archivo de entrada de ejemplo SampleDocumentInstance.xml.  
  
## <a name="comments"></a>Comentarios  
 La regla creada mediante programación dentro del **CreateRuleset()** método muestra:  
  
 **IF**  
  
 **MySampleBusinessObject.MyValue** no es igual al valor de la **identificador** elemento en el documento XML.  
  
 **A CONTINUACIÓN**  
  
 **Mysamplebusinessobject.mysamplemethod (int)** con un parámetro de número entero, disco duro codificado en la constante cinco (5) en este caso. Este método produce las líneas de salida que comienzan **MySampleBusinessObject Class –-**.  
  
 Esta regla depende de lo siguiente:  
  
-   A **MySampleBusinessObject** clase con una propiedad pública denominada **MyValue** y llama a un método público **MySampleMethod** (que toma un parámetro de número entero).  
  
-   Un esquema XML schema definition language (XSD) que define un documento XML que contiene un **identificador** elemento.  
  
 Puede definir las reglas en términos de clases y esquemas pero, durante la ejecución, se necesitan las instancias de objetos de las clases relevantes y las instancias de documentos de los esquemas relevantes. Evalúe las reglas en estas instancias de tiempo de ejecución (conocidas como hechos). En este ejemplo, los hechos son varias instancias de la **MySampleBusinessObject** objeto, construido con valores diferentes para sus **MyValue** propiedad y una única instancia XML del esquema definido que contiene un valor para el **identificador** elemento.  
  
## <a name="see-also"></a>Vea también  
 [Reglas de negocio (carpeta de ejemplos de BizTalk Server)](../core/business-rules-biztalk-server-samples-folder.md)