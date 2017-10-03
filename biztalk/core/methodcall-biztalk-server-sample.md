---
title: MethodCall (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, calling
- examples, orchestrations
- orchestrations, methods
ms.assetid: 6bdc72da-9478-403a-b706-3089b7374ac7
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3973a5137075732d3c648bb8b0e575dd0d49c57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="methodcall-biztalk-server-sample"></a>MethodCall (ejemplo de BizTalk Server)
El ejemplo de MethodCall muestra cómo llamar a un método basado en .NET desde una orquestación de BizTalk Server.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo interactúa con un método basado en .NET que utiliza la siguiente secuencia de pasos:  
  
1.  La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera un archivo de entrada XML de la carpeta In. Este archivo contiene información acerca de las sumas y restas que desea que realice la biblioteca matemática.  
  
2.  La orquestación llama a la biblioteca matemática incluida para realizar la suma o la resta especificada en el archivo de entrada XML.  
  
3.  El caso método de la biblioteca matemática, ya sea **agregar** o **restar**, realiza el cálculo solicitado y guarda el resultado como un documento XML.  
  
4.  La orquestación coloca el archivo resultante .xml en la carpeta Out.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El siguiente ejemplo muestra las siguientes funcionalidades:  
  
-   Aprovechar las propiedades promocionadas en una orquestación. Los tres elementos en InputSchema.xsd se promueven como campos distintivos. Cuando la orquestación recibe el mensaje de entrada, obtiene los valores de estos tres campos y los asigna a las variables correspondientes declaradas en la orquestación.  
  
-   Mediante el **decidir** forma para expresar la lógica "if-then-else" en una orquestación. Después de la orquestación asigna los valores de los campos distintivos a variables internas, entra en el **decidir** forma para comprobar si se debe realizar una suma o resta. Si no se debe realizar ninguna operación, se interrumpe la orquestación.  
  
-   Llamar a un ensamblado externo desde una orquestación. Si se va a realizar una suma, la orquestación llama a un ensamblado externo de C# y pasa en dos parámetros para realizar la suma. Los mismos procedimientos se aplican a una resta.  
  
    > [!NOTE]
    >  Debe instalar el ensamblado a la caché de ensamblados global antes de poder llamar al ensamblado desde la orquestación. De lo contrario, recibirá un error XLANG durante el tiempo de ejecución.  
  
-   Mediante el **asignación de mensajes** forma para construir el mensaje de salida.  
  
-   Coloque el siguiente código en la forma Expresión para depurar la orquestación:  
  
    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  
  
     También puede escribir el resultado en el registro de eventos utilizando:  
  
    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*> \Orchestrations\MethodCall\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|Input.xml|Archivo de entrada de ejemplo.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta \MathLibrary:<br /><br /> AssemblyInfo.cs, MathHelper.cs, MathLibrary.csproj|Archivos de proyecto y de origen para la biblioteca matemática utilizada en este ejemplo.|  
|En la carpeta \MethodCallSample:<br /><br /> InputSchema.xsd, OutputSchema.xsd|Esquemas para los archivos de entrada y de salida .xml respectivamente.|  
|En la carpeta \MethodCallSample:<br /><br /> MethodCallSample.btproj, MethodCallSample.sln|Archivos de proyectos y de soluciones de este ejemplo.|  
|En la carpeta \MethodCallSample:<br /><br /> MethodCallSampleBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puerto.|  
|En la carpeta \MethodCallSample:<br /><br /> MethodCallService.odx|Orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que llama a la biblioteca matemática para realizar el cálculo solicitado.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-methodcall-sample"></a>Para crear e iniciar el ejemplo MethodCall  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \orchestrations\methodcall\  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta MethodCall.  
  
    -   Compila los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo e implementa los ensamblados resultantes.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción a la orquestación.  
  
    -   Habilita la ubicación de recepción e inicia el puerto de envío. Se da de alta e inicia la orquestación.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-methodcall-sample"></a>Para ejecutar el ejemplo de MethodCall  
  
1.  Pegue una copia del archivo Input.xml en la carpeta In.  
  
2.  Observe el archivo .xml que se ha creado en la carpeta Out. Este archivo contiene el resultado del cálculo solicitado de suma o resta. El formato del nombre de este archivo es \< *MessageID*> .xml, donde  *\<MessageID >* es el GUID generado para identificar de forma exclusiva el mensaje.  
  
3.  Puede modificar el archivo de entrada para solicitar que se realicen cálculos de suma o resta diferentes.  
  
## <a name="uninstalling-this-sample"></a>Desinstalar este ejemplo  
  
#### <a name="to-uninstall-the-methodcall-sample"></a>Para desinstalar el ejemplo MethodCall  
  
1.  En un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a \< *ruta de ejemplos*> \orchestrations\methodcall\\\.  
  
2.  Ejecute Cleanup.bat.  
  
## <a name="see-also"></a>Vea también  
 [Orquestaciones (carpeta de ejemplos de BizTalk Server)](../core/orchestrations-biztalk-server-samples-folder.md)