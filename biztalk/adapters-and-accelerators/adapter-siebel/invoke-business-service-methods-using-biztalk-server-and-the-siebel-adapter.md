---
title: Invocar métodos de servicio de negocio mediante BizTalk Server y el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke business service methods
- business service methods, invoking
ms.assetid: cf437c4f-fa65-4f89-a197-c83869930b2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efe8faae6e29663be03d32483e6bafd1d6649269
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023394"
---
# <a name="invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter"></a>Invocar métodos de servicio de negocio mediante BizTalk Server y el adaptador de Siebel
Un servicio de negocio de Siebel es una colección de métodos de negocio que se pueden invocar directamente en Siebel. Para obtener más información acerca de cómo los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite la invocación de servicios de negocio en un sistema de Siebel, consulte [operaciones en servicios empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md). Para obtener más información sobre la estructura de SOAP de los mensajes para realizar operaciones de servicio empresarial, consulte [esquemas de mensaje para las operaciones de servicio de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md).  
  
## <a name="how-to-invoke-business-services"></a>¿Cómo invocar los servicios de negocios?  
 Realizar una operación en un sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md). Para invocar un servicio empresarial, estas tareas son:  
  
1. Cree un proyecto de BizTalk y genere el esquema para el método de servicio comercial que desea invocar.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema Siebel.  
  
3. Crear la orquestación para invocar un método de servicio empresarial en el sistema Siebel.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, BusinessService, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo invocar un método de servicio empresarial, se generará el esquema para el **Execute** método expuesto por el **TimeStamp** servicio empresarial. Consulte [recuperación de metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) para obtener más información acerca de cómo generar un esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 Este tema, debe crear dos mensajes: uno para enviar una solicitud al sistema Siebel y otro para recibir una respuesta.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, apunte a **Other Windows**y haga clic en **Vista orquestación**.  
  
2.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en la recién cree el mensaje y seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *BusinessService.SiebelBindingSchema.Execute*, donde *BusinessService* es el nombre de su proyecto de BizTalk. *SiebelBindingSchema* es el esquema generado para invocar el *Execute* método de servicio de negocio.|  
  
5.  Repita el paso anterior para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *BusinessService.SiebelBindingSchema.ExecuteResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar un servicio empresarial. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consume este mensaje y lo pasa por el sistema Siebel. La respuesta en el sistema Siebel se guarda en otra ubicación. Contendría una orquestación para invocar métodos de servicio empresarial típica:  
  
- Enviar y recibir las formas para enviar mensajes a Siebel y recibir respuestas.  
  
- Puerto para recibir mensajes de solicitud para enviar a Siebel de recepción unidireccional.  
  
- Puerto para enviar mensajes de solicitud a Siebel y recibir respuestas de envío bidireccional.  
  
- Un puerto de envío unidireccional para enviar las respuestas de Siebel a una carpeta.  
  
  Una orquestación de ejemplo para llamar a la *Execute* método para el *TimeStamp* servicio empresarial es similar al siguiente:  
  
  ![Orquestación para invocar un servicio empresarial](../../adapters-and-accelerators/adapter-siebel/media/5a776e5d-855f-4d1b-8d26-7de747b1865d.gif "5a776e5d-855f-4d1b-8d26-7de747b1865d")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveXML|Receive|-Establecer **nombre** a *ReceiveXML*<br />-Establecer **activar** a *True*|  
|SendToLOB|Send|-Establecer **nombre** a *SendToLOB*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores se establezcan para especificar los mensajes de las formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveXML|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.ServiceInvoke.Request*|  
|SendToLOB|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.ServiceInvoke.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.ServiceInvoke.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.ServiceInvoke.Request*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  
  
 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [cómo generar orquestaciones](../../core/how-to-build-orchestrations.md) y [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md). 
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo crear una aplicación](../../core/how-to-create-an-application.md).  
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarlo al sistema Siebel.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta en el sistema Siebel.  
  
  - Definir un puerto de envío WCF-Custom o WCF-Siebel físico para enviar mensajes al sistema Siebel. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md).
  
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para ejecutar el *Execute* método en el *TimeStamp* servicio empresarial de Siebel. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [iniciar una aplicación de BizTalk](../../core/how-to-start-and-stop-a-biztalk-application.md) o [iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   Se está ejecutando el puerto de envío WCF-Custom o WCF-Siebel para enviar mensajes al sistema Siebel.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Debe quitar el mensaje de solicitud en el archivo de ubicación de recepción. Debe confirmar el esquema del mensaje de solicitud en el esquema generado anteriormente en este tema. Consulte [esquemas de mensaje para las operaciones de servicio de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md) para obtener más información acerca del esquema para invocar un servicio empresarial. Por ejemplo, el mensaje de solicitud para invocar la *Execute* método en el *TimeStamp* servicio empresarial:  
  
```  
<Execute xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp/Operation" />  
```  
  
 La orquestación consume el mensaje de solicitud y lo pasa al sistema Siebel. La respuesta en el sistema Siebel se guarda en la ubicación de envío de archivo. La respuesta para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ExecuteResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp/Operation">  
  <ExecuteResult>  
    <Time xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp">2007-11-25T20:42:11.0000000</Time>  
  </ExecuteResult>  
</ExecuteResponse>  
```  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede aparecer al realizar una operación de servicio de negocio con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío, recepción, puertos, etc., de la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar los enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)