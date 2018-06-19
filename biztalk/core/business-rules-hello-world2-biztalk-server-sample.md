---
title: Business Rules Hello World2 (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eed1c0c83432417b53debcf523eeec91f85e5c2b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967306"
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a>Business Rules Hello World2 (ejemplo de BizTalk Server)
El ejemplo Business Rules Hello World2 amplía el ejemplo Business Rules Hello World1 ya que le mostrará cómo a la versión, publicar e implementar la regla XML que se establece en el almacén de reglas SQL compartido y cómo ejecutar la directiva con la **directiva** objeto proporciona el marco de trabajo de reglas de negocios. El ejemplo también muestra las actualizaciones de directivas dinámicas en funcionamiento.  
  
> [!NOTE]
>  Este ejemplo da por supuesto que el usuario ha instalado el Servicio de actualización de motor de reglas y los Componentes de reglas de negocios (situados en el nodo "Software adicional") durante la instalación del producto.  
  
> [!NOTE]
>  Usa **directiva** objetos que se va a integrar el motor de reglas en cualquier aplicación independiente. El **directiva** es la abstracción administrados a través de la regla que varias instancias del motor de objetos, se recuperan y se crea una instancia desde el almacén de SQL compartido conjuntos y las actualizaciones a las directivas se recuperan y se publican en el hospedaje de reglas aplicación.  
  
 Para obtener información básica sobre el conjunto definido y muestras de reglas hechos construidos por este ejemplo, vea [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se crea un ejecutable que realiza la secuencia de pasos siguiente:  
  
1.  Llama al método **CreateRuleset** para generar el conjunto de reglas descrito en la sección Comentarios.  
  
2.  Llama al método **SaveToFile** para mostrar cómo guardar un conjunto de reglas para un archivo.  
  
3.  Llama al método **LoadFromFile** para mostrar cómo cargar un conjunto de reglas de un archivo.  
  
4.  Implementa el conjunto de reglas en un almacén de reglas SQL compartido.  
  
5.  Se ejecuta la regla establecida utilizando un **directiva** objeto y usando el mismo conjunto de hechos de ejemplo que se usan en el Business Rules Hello World1 de ejemplo.  
  
6.  Hace una pausa, lo que le permite modificar la regla establece archivo **SampleRuleStore.xml** de una manera determinada.  
  
7.  Se ejecuta el conjunto de reglas nuevo mediante una **directiva** de objetos, la regla ahora modificada conjunto y nuevo con el mismo conjunto de hechos de ejemplo que se usan en el Business Rules Hello World1 de ejemplo.  
  
8.  Realiza una limpieza mediante la eliminación del archivo de conjunto de reglas y de los registros del conjunto de reglas implementados en preparación de la ejecución posterior del ejemplo.  
  
> [!NOTE]
>  Para obtener información importante acerca de todos los ejemplos de este SDK, vea [ejemplos](../core/samples-in-the-sdk.md).  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>* \Business Rules\Business reglas Hello World2\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld2.csproj, BusinessRulesHelloWorld2.sln|Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que crea, guarda, carga, implementa y ejecuta un conjunto de reglas.|  
|HelloWorld2.cs|Archivo de Visual C# que contiene métodos para mostrar cómo crear una regla de conjunto, guardar un conjunto de reglas para un archivo, cómo cargar un conjunto de reglas de un archivo, al implementar la regla establecida en un almacén de reglas compartido de Microsoft SQL Server y, a continuación, ejecutar el conjunto de reglas mediante un **directiva**objeto.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|SampleDocumentInstance.xml|El archivo de entrada de ejemplo que se ajusta al esquema definido en el archivo SampleSchema.xsd.|  
|SampleSchema.xsd|El archivo de esquema que define un esquema simple con un elemento al que hace referencia el conjunto de reglas creado en el archivo de Visual C# Class1.cs.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta \HelloWorld2Library:<br /><br /> AssemblyInfo.cs, HelloWorld2Library.csproj, HelloWorld2Library.sln|Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que proporciona la clase que define los objetos a los que hace referencia el conjunto de reglas creado.|  
|En la carpeta \HelloWorld2Library:<br /><br /> HelloWorld2LibraryClass.cs|Archivo de Visual C# que contiene la propiedad que se hace referencia en el **IF** parte de la regla creada y el método que se puede llamar en el **, a continuación,** parte de la regla creada.|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a>Para crear e inicializar el ejemplo Business Rules Hello World2  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso\>* \Business Rules\Business reglas Hello World2\  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    > [!NOTE]
    >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
    > [!NOTE]
    >  Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a>Para ejecutar el ejemplo Business Rules Hello World2  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso\>* \Business Rules\Business reglas Hello World2\bin\Debug\  
  
2.  En la ventana de comandos, escriba el nombre del archivo para este ejemplo (**BusinessRulesHelloWorld2.exe**), y, a continuación, presione ENTRAR.  
  
## <a name="hello-world2-output"></a>Resultado de Hello World2  
 En función de la naturaleza del conjunto de reglas creado, se describe en la sección de comentarios [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md), si ejecuta este ejemplo con el archivo de entrada de ejemplo proporcionado SampleDocumentInstance.xml, que se ha definido un valor de uno (1) para su **identificador** elemento, verá el siguiente resultado:  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Deploying the ruleset ...  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...  
Grabbing the policy ...  
Executing the policy...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
The major version of the policy was: 1  
The minor version of the policy was: 0  
Press the ENTER to continue after updating the policy...  
```  
  
> [!NOTE]
>  El resultado se muestra en negrita es el resultado producido por el objeto de negocio de ejemplo, definido por los archivos de la **HelloWorld2Library** carpeta que la regla establecida referencias. En este punto, la aplicación se queda esperando en este estado.  
  
 La siguiente parte de la ejecución de este ejemplo conlleva el uso del Compositor de reglas de negocios para cambiar las reglas de negocios.  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a>Para usar el Compositor de reglas de negocios para cambiar las reglas de negocios  
  
1.  Para abrir el Compositor de reglas de negocio, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocio**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  Si aparece un cuadro de diálogo de SQL Server en el equipo que ejecuta SQL Server, haga clic en **Aceptar** para conectarse al almacén de reglas.  
  
3.  En **Explorador de directivas**, a continuación el **SampleRuleSet** nodo, haga clic en el nodo **versión 1.0 – implementada**y, a continuación, haga clic en **copia**.  
  
4.  Haga clic en **SampleRuleSet**y, a continuación, haga clic en **pegar (versión de la directiva)**.  
  
5.  Puede cambiar la condición de regla y la acción en función de sus necesidades. Para este procedimiento, haga clic en **rule1** en **versión 1.1 (sin guardar)**. En el panel derecho, haga clic en **condiciones**y, a continuación, haga clic en **Agregar operador lógico NOT**. Agregar un **NOT lógico** operación **no es igual a** en el predicado es equivalente a usar un **igual** predicado.  
  
6.  Haga clic en el nodo **versión 1.1 (sin guardar)** y, a continuación, haga clic en **guardar**. Haga clic en nuevo y, a continuación, haga clic en **publicar**. Haga clic en una tercera vez y haga clic en **implementar**.  
  
7.  En la ventana de comandos pausada que le pide que presione cualquier tecla para continuar tras la actualización de la directiva, presione cualquier tecla.  
  
 El resultado (dando por supuesto que ha cambiado la regla mediante la agregación de un operador lógico NOT) del archivo ejecutable BusinessRulesHelloWorld2.exe continúa de la siguiente forma:  
  
```  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...         
Grabbing the policy ...         
Executing the policy...         
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5         
The major version of the policy was: 1         
The minor version of the policy was: 1         
Press ENTER to continue after updating the policy...         
```  
  
 Observe cómo ha cambiado el resultado:  
  
-   La línea de salida en el método **MySampleMethod** sólo imprime una vez ahora, para la instancia de la **MySampleBusinessObject** clase para la que el **MyValue** propiedad es igual a 1 , en lugar de la regla anterior de impresión cuando la **MyValue** propiedad no es igual a 1.  
  
-   El número de la versión secundaria de la directiva es ahora 1.  
  
## <a name="see-also"></a>Vea también  
 [Reglas de negocio (carpeta de ejemplos de BizTalk Server)](../core/business-rules-biztalk-server-samples-folder.md)