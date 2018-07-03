---
title: OperationsSamples (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a871afd76d6dd46cb4aa5d72d1c23b332ad90e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969501"
---
# <a name="operationssamples-biztalk-server-sample"></a>OperationsSamples (ejemplo de BizTalk Server)
El ejemplo OperationsSamples muestra cómo se realizan actividades operativas mediante el modelo de objetos Operaciones.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra lo siguiente:  
  
- Uso de un perfil de seguimiento para comentar una orquestación con actividades.  
  
- Uso de la base de datos de seguimiento de BAM para buscar un identificador de actividad y usarlo para encontrar una instancia de orquestación relacionada.  
  
- Cómo buscar y trabajar con flujos de mensajes mediante el **MessageFlow** clase y otras clases de modelo de objetos de operaciones y las API.  
  
- Cómo obtener acceso a puertos, mensajes y otras instancias mediante las clases derivadas de la **instancia** clase.  
  
  El ejemplo contiene muchas clases y métodos auxiliares que resultan útiles para las operaciones anteriores. Estos aspectos destacados y otros sobre el código se explican en la sección siguiente.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Diseño del ejemplo y justificación  
 Este ejemplo está diseñado para mostrar varios métodos y clases clave del modelo de objetos Operaciones, así como la forma de consultar la base de datos de seguimiento de BAM que está disponible públicamente.  
  
 El modelo de objetos Operaciones contiene clases que permiten manipular mensajes y otras instancias en BizTalk Server.  
  
### <a name="using-a-bam-activity-id"></a>Uso de un identificador de actividad de BAM  
 Este ejemplo muestra la interacción con BAM y el uso de las vistas disponibles públicamente en la base de datos de seguimiento para localizar un mensaje activo en el cuadro de mensajes a partir de datos económicos. Para ello, el ejemplo recupera un identificador de orquestación correspondiente a un número de pedido. Para que esta tarea funcione correctamente, debe hacer lo siguiente:  
  
1. Utilizar datos económicos (un número de pedido) para encontrar un Id. de actividad. En este paso se asignan los datos económicos a un Id. interno que se puede utilizar para encontrar información adicional.  
  
2. Recuperar las referencias de BAM relacionadas con el identificador de actividad.  
  
3. Encontrar una referencia que tenga un tipo de "BizTalkService" y haga referencia a una orquestación. Si se encuentra una, devolver su identificador de instancia.  
  
   Esta funcionalidad se proporciona mediante el **BAMWebService.GetOrchestrationID** método estático y los métodos auxiliares asociados incluidas las clases y métodos en el archivo de origen BamManagementService.cs.  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a>Suspensión, finalización y reanudación de instancias  
 El programa de ejemplo incluye un **Samples.OperateOnInstance** método que toma un identificador de operación y la instancia y realiza la operación especificada en la instancia. Las operaciones válidas se definen mediante la **InstanceOperation** enumeración e incluyen suspender, finalizar y reanudar. Estas operaciones se asignan directamente a los métodos de la clase BizTalkOperations:**SuspendInstance**, **TerminateInstance**, y **ResumeInstance**.  
  
 Tenga en cuenta que el método controla las excepciones ArgumentException y SqlException. Debe tener cuidado en la anticipación de excepciones, incluida SqlException, al trabajar con las clases y los métodos del modelo de objetos Operaciones.  
  
> [!NOTE]
>  Muchos métodos de Operaciones requieren acceso a la base de datos. Debería anticipar las excepciones que estos métodos inician y controlarlas de forma adecuada.  
  
### <a name="retrieving-all-live-messages"></a>Recuperación de todos los mensajes activos  
 El modelo de objetos Operaciones facilita la repetición sobre todos los mensajes activos disponibles, tal y como se muestra en el siguiente fragmento de código:  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 El programa OperationsSamples lleva más lejos este paso al demostrar cómo se obtiene acceso a la información acerca de cada mensaje, incluido el identificador y el tipo de mensaje junto con el número y los tipos de partes del mensaje. Puede modificar este código y usarlo en escenarios donde tenga que repetir en muchos o todos los mensajes activos disponibles en BizTalk Server.  
  
> [!NOTE]
>  Puede haber cientos o miles de mensajes disponibles. La exploración de toda la lista puede afectar negativamente al rendimiento.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de la ruta de acceso*\>\Admin\OperationsOM\OperationsSamples\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|BamManagementService.cs|Clase de proxy web para el servicio web de BAM.|  
|Cleanup.bat|Quita la orquestación de ejemplo y restaura el estado original del ejemplo HelloWorld.|  
|HelloOrchestration.btt|Perfil de seguimiento usado para asignar orígenes de eventos de BizTalk a actividades de destino de BAM.|  
|HelloOrchestration.xls|Hoja de estilos de definición de BAM.|  
|OperationsSamples.cs|Archivo de origen de C# que contiene código que demuestra varios aspectos del modelo de objetos Operaciones.|  
|OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs|Archivos de información de proyectos, soluciones y ensamblados para este ejemplo.|  
|Setup.bat|Usado para crear e inicializar este ejemplo mediante la modificación del ejemplo de orquestación HelloWorld. Instala una orquestación de ejemplo, implementa una definición de actividad de BAM y un archivo de editor de perfiles de seguimiento, configura puertos y coloca un archivo de ejemplo en la ubicación de recepción.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use este ejemplo para explorar la funcionalidad disponible en el modelo de objetos Operaciones. Modifique las rutinas que existen para buscar y trabajar con mensajes de un modo diferente o para agregar código nuevo que replique partes del concentrador de grupo en la consola de administración de BizTalk Server.  
  
 Considere también la opción de llevar a cabo algunas de las tareas siguientes:  
  
-   Escribir una aplicación que replique el subconjunto más usado del concentrador de grupo en una aplicación personalizada.  
  
-   Escribir una aplicación de suministro personalizada que cree puertos y envíe un mensaje de prueba a través de socios comerciales nuevos.  
  
-   Modificar el programa de ejemplo en una utilidad de línea de comandos que proporcione información acerca de un único pedido o de un intervalo de pedidos en la pantalla, en un archivo XML o en un informe de texto.  
  
## <a name="installing-sample-support-files"></a>Instalación de archivos adicionales del ejemplo  
 En esta sección se le guiará por los procedimientos necesarios para instalar y ejecutar el ejemplo.  
  
> [!NOTE]
>  Antes de instalar y ejecutar este ejemplo, debe comprobar que BAM está instalado y que funciona. Si BAM no está instalado, el ejemplo no funcionará.  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a>Procedimiento para compilar e instalar los archivos adicionales de este ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  Ejecute el archivo Setup.bat, que realiza las acciones siguientes:  
  
    -   Crea directorios de envío y recepción  
  
    -   Crea e inicia puertos de envío y recepción  
  
    -   Compila e implementa la orquestación HelloWorld en la carpeta `<Samples Path>`\Orchestrations\HelloWorld.  
  
    -   Modifica el token de clave pública para la orquestación HelloWorld  
  
    -   Implementa la definición de actividad de BAM y el archivo del editor de perfiles de seguimiento  
  
    -   Cambia el nombre del directorio de salida  
  
    > [!NOTE]
    >  Para anular la instalación, presione CTRL+C la primera vez que aparezca el mensaje “Presione cualquier tecla para continuar”. De este modo se detiene la secuencia de comandos y se deja el estado original del ejemplo HelloWorld. Si se presiona CTRL+C en el segundo y último mensaje, la instalación no se detiene. Llegado este caso, ejecute Cleanup.bat para desinstalar el ejemplo OperationsOM y restaurar el ejemplo HelloWorld.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Use el siguiente procedimiento para ejecutar el ejemplo OperationsOM.  
  
#### <a name="to-compile-and-run-the-sample"></a>Procedimiento para compilar y ejecutar el ejemplo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, seleccione **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Las instancias de host**.  
  
3.  Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.  
  
    > [!NOTE]
    >  Puede ser necesario reiniciar la instancia de host BizTalkServerApplication para establecer la base de datos de trabajo correcta para BAM si no ha reiniciado la instancia de host desde la configuración del producto.  
  
4.  En el Explorador de Windows, desplácese a la siguiente carpeta:  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  Haga doble clic en el **OperationsOM.sln** archivo de proyecto para cargarlo en Visual Studio.  
  
6.  Presione F5 para ejecutar el ejemplo.  
  
     --O BIEN--  
  
     En el **compilar** menú, haga clic en **recompilar solución**. Una vez completada la compilación, utilice el Explorador de Windows para navegar a `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` y, a continuación, haga doble clic en **OperationsSamples.exe**.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 [Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx) &#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx) &#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx) &#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx) &#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx) &#124; [ Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx) &#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)  
  
## <a name="see-also"></a>Vea también  
 [Admin\OperationsOM (carpeta de ejemplos de BizTalk Server)](../core/admin-operationsom-biztalk-server-samples-folder.md)