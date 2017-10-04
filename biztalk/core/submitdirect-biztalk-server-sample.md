---
title: SubmitDirect (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- receive adapters, examples
- examples, receive adapters
ms.assetid: 3540368b-cf46-4c83-a87b-94aec9cd1b36
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1e355f752241135d781c3425e05f017b0d86d93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="submitdirect-biztalk-server-sample"></a>SubmitDirect (ejemplo de BizTalk Server)
El ejemplo SubmitDirect muestra cómo enviar mediante programación mensajes unidireccionales y de solicitud-respuesta a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde aplicaciones basadas en .NET. El ejemplo muestra el uso de las API de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para los adaptadores. También proporciona un adaptador de recepción, conocido como adaptador de envío, que puede usarse para enviar mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar este ejemplo, asegúrese de que está registrado como usuario que pertenece al grupo Usuarios de hosts aislados de BizTalk.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo realizar varias tareas relacionadas con los adaptadores de BizTalk. En concreto, muestra cómo:  
  
-   Trabajar con adaptadores aislados que se ejecutan fuera del proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de envío es un adaptador aislado, ya que se crea mediante un proceso externo al proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (se inicia como una aplicación .NET).  
  
-   Enviar lotes de mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de envío usa la funcionalidad de envío de mensajes por lotes para enviar varios mensajes a la vez.  
  
-   Enviar mensajes de forma sincrónica mediante el uso de un paradigma de solicitud-respuesta, así como de forma asíncrona mediante el uso de un paradigma unidireccional.  
  
-   Registrar un adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este ejemplo se muestra cómo registrar un adaptador y se proporciona un ejecutable de registro que automatiza el registro de un adaptador.  
  
 En realidad, este ejemplo son dos ejemplos en uno:  
  
-   **Envío de un lote de mensajes unidireccionales.** La aplicación de consola SubmitMessages.exe toma las cadenas de su línea de comandos y las envía como un mensaje independiente a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recoge cada uno de estos mensajes enviados en la ubicación de recepción. A continuación, estos mensajes se envían a través de canalizaciones de envío y de recepción de paso a través y, finalmente, se escriben en un archivo de texto.  
  
-   **Envío de mensaje de solicitud/respuesta.** La aplicación de consola SubmitRequest.exe toma el archivo .xml especificado en su línea de comandos y lo envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El esquema de este archivo .xml define elementos que contienen dos campos enteros. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recoge el archivo .xml y lo procesa con una orquestación (con un puerto de solicitud-respuesta). Usa una asignación para producir un mensaje de respuesta XML que devuelva un entero, que será el producto de los dos enteros en la solicitud. Cuando la aplicación de consola reciba la respuesta, mostrará el resultado.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\SubmitDirect\  
  
 En la siguiente tabla se enumeran los archivos de este ejemplo y se describe el propósito de cada uno de ellos.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.|  
|Setup.bat|Crea e inicializa este ejemplo.|  
|SubmitDirect.sln|Archivo de solución que incluye el proyecto de BizTalk en la carpeta ProcessRequest y los proyectos de Microsoft Visual C# en las otras carpetas.|  
|SubmitMessagesBinding.xml, SubmitRequestBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puerto.|  
|En la carpeta \ProcessRequest:<br /><br /> DocIn.xsd, DocOut.xsd, Multiplier.odx, Multiply.btm, ProcessRequest.btproj|Proporciona un proyecto de BizTalk que realiza la multiplicación de los enteros en el escenario de solicitud-respuesta.|  
|En la carpeta \SubmitMessages:<br /><br /> AssemblyInfo.cs, SubmitMessages.cs, SubmitMessages.csproj|Proporciona un proyecto de Visual C# para la aplicación de consola que pasa los parámetros de la cadena de la línea de comandos como un lote de mensajes independientes.|  
|En la carpeta \SubmitRequest:<br /><br /> AssemblyInfo.cs, DocInstance.xml, SubmitRequest.cs, SubmitRequest.csproj|Proporciona un proyecto de C# para la aplicación de consola que pasa un archivo .xml (DocInstance.xml) que contiene dos enteros que van a multiplicarse.|  
|En la carpeta \TransportProxyUtils:<br /><br /> AssemblyInfo.cs, MessageHelper.cs, MessagingAPIInterface.cs, MessagingAPIs.cs, ResponseCallBack.cs, TpBatchAsyncCallback.cs, TpBatchAsyncResult.cs, TpBatchStatus.cs, TransportProxyUtils.csproj|Proporciona un proyecto de C# para la parte en tiempo de ejecución del adaptador de envío, que implementa métodos para el envío de mensajes de forma sincrónica y asíncrona, y para el envío de mensajes de solicitud únicos y por lotes.|  
|En la carpeta \TransportProxyUtilsReg:<br /><br /> AssemblyInfo.cs, RegisterAdapter.cs, TransportProxyUtilsReg.csproj|Proporciona un proyecto de Visual C# que muestra el código que puede usar para registrar adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|En la carpeta \TransportProxyUtilsUI:<br /><br /> AssemblyInfo.cs, TransportProxyUtilsMgmt.cs, TransportProxyUtilsUI.csproj|Proporciona un proyecto de Visual C# para la parte de la interfaz de usuario del adaptador de envío.|  
  
## <a name="building-and-initializing-the-sample"></a>Crear e inicializar el ejemplo  
  
#### <a name="to-build-and-initialize-the-submitdirect-sample"></a>Para crear e inicializar el ejemplo SubmitDirect  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\SubmitDirect  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea la siguiente carpeta de salida para la parte de envío por lotes de este ejemplo.  
  
         \<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\SubmitDirect\Out  
  
    -   Compila los diversos proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Registra el adaptador de envío con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    -   Crea y enlaza las ubicaciones de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], así como los puertos de envío y recepción.  
  
        > [!NOTE]
        >  Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos:  
        >   
        >  `Warning: Receive handler not specified for receive location "SubmitDirectRL"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.ProcessRequest.Multiplier"; updating with first available host.`  
        >   
        >  Puede omitir estas advertencias de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    -   Habilita las ubicaciones de recepción e inicia los puertos de envío y orquestación.  
  
        > [!NOTE]
        >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
        > [!NOTE]
        >  Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
        > [!NOTE]
        >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Dado que este ejemplo usa el adaptador de archivo, el host de BizTalk (BizTalkServerApplication) debe estar en ejecución. Use los procedimientos que se exponen a continuación para ejecutar el ejemplo SubmitDirect.  
  
#### <a name="to-run-the-batch-submission-portion-of-the-submitdirect-sample"></a>Para ejecutar la parte de envío por lotes del ejemplo SubmitDirect  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\SubmitDirect\SubmitMessages\bin\Debug  
  
2.  Ejecute el archivo SubmitMessages.exe, y pase varias cadenas de la línea de comandos.  
  
     Ejemplo: SubmitMessages msg1 msg2 msg3  
  
3.  Observe los diversos archivos de texto creados en la carpeta de salida Out. Estos archivos contienen las cadenas pasadas de la línea de comandos, una por archivo.  
  
#### <a name="to-run-the-requestresponse-portion-of-the-submitdirect-sample"></a>Para ejecutar la parte de solicitud-respuesta del ejemplo SubmitDirect  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\SubmitDirect\SubmitRequest\bin\Debug  
  
2.  Ejecute el archivo SubmitRequest.exe. Para ello, pase un nombre de archivo .xml correspondiente en la línea de comandos.  
  
     Ejemplo: SubmitRequest... \\.. \DocInstance.Xml  
  
3.  Observe el mensaje de respuesta XML, que contiene el resultado de la operación de multiplicación, que aparece en la consola.  
  
## <a name="comments"></a>Comentarios  
 Puede usar el adaptador de envío en otras aplicaciones. Puede usarlo desde cualquier código basado en .NET para enviar mensajes a su servidor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante programación. Para usar este adaptador con su código, lleve a cabo el procedimiento que se expone a continuación.  
  
#### <a name="to-use-the-sample-adapter-with-your-code"></a>Para usar el adaptador de ejemplo con su código  
  
1.  Registra el adaptador de envío con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si ha ejecutado el archivo Setup.bat proporcionado con este ejemplo, el adaptador debe estar registrado y listo para usarse. En caso contrario, puede registrarlo mediante la generación de los proyectos TransportProxyUtils.csproj, TransportProxyUtilsUI.csproj y TransportProxyUtilsReg.csproj y, a continuación, mediante la ejecución el ejecutable producido por el último proyecto, RegisterAdapter.exe.  
  
    > [!IMPORTANT]
    >  Si instala BizTalk en un equipo de 64 bits, cambie todas las instancias de la entrada de registro HKEY_CLASSES_ROOT\CLSID\ a HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ en el **RegisterAdapter.cs** archivo.  
  
2.  Cree un puerto de recepción con una ubicación de recepción que use el adaptador de envío. Especifique la dirección de la ubicación de recepción. La dirección puede ser cualquier cadena que sea única en las ubicaciones de recepción que usen este adaptador.  
  
3.  En su proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga referencia al ensamblado Microsoft.BizTalk.SDKSamples.AdaptersDevelopment.TransportProxyUtils.dll.  
  
4.  Envíe mensajes a su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el uso de uno o varios de los métodos siguientes proporcionados por el ensamblado.  
  
    |Métodos|Description|  
    |-----------------|-----------------|  
    |**SubmitMessage()**<br /><br /> **BeginSubmitMessage()**<br /><br /> **EndSubmitMessage()**|Métodos sincrónicos y asíncronos para enviar un mensaje unidireccional a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La dirección de la ubicación de recepción que se envía el mensaje debe establecerse en el contexto del mensaje.<br /><br /> Un valor booleano que indica que el estado del envío (correcto o con errores) se ha devuelto.|  
    |**SubmitMessages()**<br /><br /> **BeginSubmitMessages()**<br /><br /> **EndSubmitMessages()**|Métodos sincrónicos y asíncronos para enviar una matriz de mensajes unidireccionales a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Las direcciones de las ubicaciones de recepción en las que se envían los mensajes deben estar establecidas en el contexto de los mensajes.<br /><br /> Un valor booleano que indica que el estado del envío (correcto o con errores) se ha devuelto.|  
    |**SubmitSyncMessage()**<br /><br /> **BeginSubmitSyncMessage()**<br /><br /> **EndSubmitSyncMessage()**|Métodos sincrónicos y asíncronos para enviar un mensaje de solicitud a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La dirección de la ubicación de recepción en la que se envía el mensaje debe estar establecida en el contexto del mensaje.<br /><br /> Se devuelve el mensaje de respuesta.|  
    |**CreateMessageFromString()**|Crea un objeto de mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde una cadena y establece la propiedad de dirección de ubicación de recepción en el contexto del mensaje.<br /><br /> Devuelve un objeto de mensaje de BizTalk.|  
    |**CreateMessageFromStream()**|Crea un objeto de mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde una secuencia y establece la propiedad de dirección de ubicación de recepción en el contexto del mensaje.<br /><br /> Devuelve un objeto de mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
  
     Para obtener más detalles sobre los parámetros y los tipos de valores devueltos de estos métodos, vea el archivo MessagingAPIInterface.cs, que se encuentra en la carpeta TransportProxyUtils.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptador: desarrollo](../core/adapter-samples-development.md)   
 [Registrar un adaptador](../core/registering-an-adapter.md)