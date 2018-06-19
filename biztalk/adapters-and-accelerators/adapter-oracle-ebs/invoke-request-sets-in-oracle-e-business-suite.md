---
title: Invocar conjuntos de solicitudes en Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a79bff63-325d-4745-ab0e-839e00476ab1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b00fd382bb46df9de740b2308ad87c28720165a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967778"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite"></a>Invocar conjuntos de solicitudes en Oracle E-Business Suite
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]permite ejecutar conjuntos de solicitudes en Oracle E-Business Suite. Solicitar conjuntos se dividen en una o varias fases y cada fase contiene un conjunto de informes y programas simultáneos. Para obtener más información sobre cómo el adaptador admite conjuntos de solicitudes, consulte [operaciones en la solicitud establece](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md). Para obtener información acerca de la estructura de SOAP de los mensajes para invocar conjuntos de solicitudes, consulte [esquemas de mensaje para la solicitud establece](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado los pasos descritos en [requisitos previos para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md).  
  
## <a name="how-to-invoke-request-sets-in-oracle-e-business-suite"></a>Cómo invocar la solicitud se establece en Oracle E-Business Suite  
 Realizar una operación en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para invocar una solicitud de conjunto, estas tareas son:  
  
-   Crear un proyecto de BizTalk y genere el esquema para el conjunto de solicitud que desea invocar.  
  
-   Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes hacia y desde Oracle E-Business Suite.  
  
-   Crear una orquestación para invocar el conjunto de solicitud.  
  
-   Compilar e implementar el proyecto de BizTalk.  
  
-   Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
-   Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema se muestra cómo invocar un conjunto de solicitud, invocando la **informes de seguridad de la función** solicitud (nombre descriptivo) establece desde el **biblioteca de objetos de aplicación** aplicación. El nombre real del conjunto de solicitud es **FNDRSSUB43**. Este conjunto de solicitud está disponible con la aplicación de Oracle E-Business Suite predeterminada. Este conjunto de solicitud devuelve un identificador de solicitud.  
  
 Por lo tanto, en este tema, se genere el esquema para el **FNDRSSUB43** solicitar conjunto. Vea [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes de la orquestación y vincularlos a los esquemas que generó en el paso anterior.  
  
 En esta orquestación debe crear dos mensajes: uno para enviar el mensaje para invocar el conjunto de solicitud y otro para recibir una respuesta para el conjunto de solicitud.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *RequestSet.OracleEBSBindingRequestSets_FND. FNDRSSUB43*, donde RequestSet es el nombre de su proyecto de BizTalk. OracleEBSBindingRequestSets es el esquema generado para invocar la **FNDRSSUB43** solicitar conjunto.|  
  
6.  Repita el paso 3 para crear un mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Respuesta|*RequestSet.OracleEBSBindingRequestSets_FND. FNDRSSUB43Response*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar conjuntos de solicitudes en Oracle E-Business Suite. En esta orquestación, puede quitar un mensaje de solicitud en una determinada ubicación de recepción. La orquestación consume este mensaje y lo pasa al Oracle E-Business Suite para invocar la **FNDRSSUB43** solicitar conjunto. La respuesta para el conjunto de solicitud se recibe de Oracle y se guarda en otra ubicación. Contendría una orquestación típica para invocar un conjunto de solicitud:  
  
-   Enviar y recibir formas a fin de enviar mensajes a Oracle E-Business Suite y recibir respuestas.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar a Oracle E-Business Suite.  
  
-   Puerto para enviar mensajes de solicitud para Oracle E-Business Suite y recibir respuestas de envío bidireccional.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de Oracle E-Business Suite a una carpeta.  
  
 Una orquestación de ejemplo para invocar un conjunto de solicitud es similar al siguiente:  
  
 ![Orquestación para invocar conjuntos de solicitudes](../../adapters-and-accelerators/adapter-oracle-ebs/media/ea161292-8613-4c0b-ac24-2f26c54bf3a3.gif "ea161292-8613-4c0b-ac24-2f26c54bf3a3")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *es True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y los valores que se pueden establecer para especificar los mensajes para formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.RequestSet.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.RequestSet.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.RequestSet.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.RequestSet.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Debe compilar ahora la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, la orquestación que creó anteriormente se muestra en el panel de orquestaciones en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).  
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviar a Oracle E-Business Suite.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de Oracle E-Business Suite.  
  
    -   Definir un puerto de envío WCF-Custom o WCF-OracleEBS físico para enviar mensajes a Oracle E-Business Suite. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de envío, consulte [configurar manualmente un puerto físico enlazado con el adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).  
  
         Para invocar la solicitud establece mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe establecer el contexto de la aplicación correcta en el que se invoca la operación. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona ciertas propiedades de enlace para especificar el contexto de la aplicación para cualquier operación. Debe establecer estas propiedades de enlace en el puerto WCF-Custom o WCF-OracleEBS que se usa para invocar conjuntos de solicitudes.  
  
        -   Si el **ClientCredentialType** enlaza la propiedad se establece en **base de datos**, a continuación, debe especificar las siguientes propiedades de enlace para establecer el contexto de las aplicaciones.  
  
            |Propiedad de enlace|Valor|  
            |----------------------|-----------|  
            |**OracleUserName**|Especifique el nombre de un usuario de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no conserva el caso del valor que especifique para la **OracleUserName** propiedad de enlace cuando se conecta a Oracle E-Business Suite. El nombre de usuario se pasa a Oracle E-Business Suite utilizando las reglas estándar de SQL * Plus. Sin embargo, si desea que el caso de que se conserve el nombre de usuario o si desea escribir un nombre de usuario que contiene caracteres especiales, debe especificar el valor entre comillas dobles.|  
            |**OraclePassword**|La contraseña para el usuario de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no conserva el caso del valor que especifique para la **OraclePassword** propiedad de enlace cuando se conecta a Oracle E-Business Suite. La contraseña se pasa a Oracle E-Business Suite utilizando las reglas estándar de SQL * Plus. Sin embargo, si desea que el caso de la contraseña que se va a conservar o si desea escribir una contraseña que contiene caracteres especiales, debe especificar el valor entre comillas dobles.|  
            |**OracleEBSResponsibilityName**|La responsabilidad asociada al usuario de Oracle E-Business Suite.|  
  
        -   Si el **ClientCredentialType** enlaza la propiedad se establece en **EBusiness**, deben haber especificado las credenciales de Oracle E-Business al establecer la conexión. En tal caso solo se debe especificar valor de la **OracleEBSResponsibilityName** propiedad de enlace.  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite ](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener más información sobre cómo el adaptador admite establecer el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
        > [!NOTE]
        >  Puede establecer el contexto de la aplicación mediante la especificación de las propiedades de enlace o estableciendo el mensaje propiedades de contexto expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener instrucciones sobre cómo establecer el contexto de la aplicación mediante las propiedades de contexto de mensaje, consulte [configurar las propiedades contexto de mensaje usando de contexto de aplicación en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un físico puerto de enlace utilizando un archivo de enlace de puerto para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para invocar los conjuntos de solicitud. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El WCF-Custom o WCF-OracleEBS puerto de envío para invocar la **FNDRSSUB43** conjunto de solicitud se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud que se ajusta al esquema para invocar la **FNDRSSUB43** solicitar conjunto. Por ejemplo, el mensaje de solicitud para invocar la **FNDRSSUB43** conjunto de solicitud es:  
  
```  
<FNDRSSUB43 xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <StartTime></ StartTime>  
  <All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
    <FNDMNNAV xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNNAV>  
    <ns2:FNDMNMNU xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</ns3:Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNMNU>  
    <ns2:FNDMNFUN xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</ns3:Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNFUN>  
  </ns0:All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
</ns0:FNDRSSUB43>  
```  
  
> [!NOTE]
>  El mensaje de solicitud para llamar a un conjunto de solicitud requiere algunos parámetros opcionales, como SetRelClassOptions, SetPrintOptions, SetRepeatOptions y SetNlsOptions. El mensaje de solicitud que se muestran a continuación no contiene estos parámetros opcionales. Para obtener información sobre el mensaje de solicitud completa, incluidos los parámetros opcionales, vea [esquemas de mensaje para conjuntos de solicitudes](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md).  
  
 La orquestación consume el mensaje, pasa a Oracle E-Business Suite y recibe una respuesta. El mensaje de respuesta se guarda en la otra ubicación de archivo especificada como parte de la orquestación. La respuesta para la **FNDRSSUB43** solicitud conjunto es similar al siguiente:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<FNDRSSUB43Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <FNDRSSUB43Result>2543208</FNDRSSUB43Result>  
</FNDRSSUB43Response>  
```  
  
 La respuesta de Oracle E-Business Suite contiene un identificador de solicitud. Solicitud de Id. de '0' indica que la última operación en la solicitud establezca error de envío. En tal caso, puede especificar otros parámetros opcionales en el mensaje de solicitud, como ContinueOnFail, para averiguar el motivo del error y para depurar aún más.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos, como los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)