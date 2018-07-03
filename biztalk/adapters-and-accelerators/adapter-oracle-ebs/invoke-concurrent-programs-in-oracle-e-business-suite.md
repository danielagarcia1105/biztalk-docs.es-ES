---
title: Invocar programas simultáneos en Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85c55a35-bee4-4b50-8b00-e4198ad4c2af
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdd5b182267009a6b2591ffb06f5ba75db1b7e3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969693"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite"></a>Invocar programas simultáneos en Oracle E-Business Suite
Oracle E-Business Suite expone programas simultáneos que se pueden ejecutar para realizar operaciones concretas en las aplicaciones de Oracle. Cada aplicación de Oracle tiene un conjunto de programas simultáneos estándares (que son los mismos en todas las operaciones) y ciertos programas simultáneos que son específicas de una aplicación de Oracle. La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone todos los programas simultáneos como operaciones que pueden invocar a los clientes del adaptador. Para obtener más información sobre cómo el adaptador es compatible con programas simultáneos, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md). Para obtener información sobre la estructura de SOAP de los mensajes para invocar programas simultáneos, consulte [esquemas de mensaje para programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md).  

> [!NOTE]
>  Para los programas simultáneos que no exponen sus metadatos, el adaptador de Oracle E-Business expone 100 parámetros opcionales para cada uno de estos programas simultáneos. Para llamar correctamente a estos programas simultáneos, el usuario debe consultar la documentación de Oracle E-Business Suite para averiguar los parámetros de un programa simultáneo que requieren un valor y especificarlos, a continuación. Un ejemplo de este tipo de programa simultáneo es **importación de Journal** (nombre real: **GLLEZL**) en el **contabilidad** aplicación.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado los pasos descritos en [requisitos previos para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md).

## <a name="how-to-invoke-concurrent-programs-in-oracle-applications"></a>Cómo invocar programas simultáneos en aplicaciones de Oracle  
 Realizar una operación en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para invocar un programa simultáneo, estas tareas son:  

- Cree un proyecto de BizTalk y genere el esquema para el programa simultáneo que desea invocar.  

- Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes hacia y desde Oracle E-Business Suite.  

- Crear una orquestación para invocar el programa simultáneo.  

- Compile e implemente el proyecto de BizTalk.  

- Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  

- Inicie la aplicación de BizTalk.  

  Este tema proporciona instrucciones para realizar estas tareas.  

## <a name="generating-schema"></a>Generar el esquema  
 En este tema se muestra cómo invocar el **interfaz cliente** programa simultáneo desde el **cuentas por cobrar** aplicación. Esta aplicación está disponible con la aplicación predeterminada de Oracle E-Business Suite. Este programa simultáneo devuelve un identificador de solicitud. Para comprobar el estado del programa simultáneo, ejecutamos el **Get_Status** programa simultáneo pasando el identificador de solicitud recibido en la respuesta de la **interfaz cliente** programa simultáneo.  

 En este tema, se generan esquemas para ambos el **interfaz cliente** y **Get_Status** programas simultáneos. Para obtener más información acerca de cómo generar un esquema, vea [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  

## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes para la orquestación y vincularlos a los esquemas que generó en el paso anterior.  

 En esta orquestación debe crear cuatro mensajes, Establece una respuesta de recepción para invocar el **interfaz cliente** programa simultáneo y la otra recepción de respuesta se establecen para invocar el **Get_Status** programa simultáneo.  

#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  

1. Agregar una orquestación al proyecto de BizTalk. Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  

2. Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  

3. En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  

4. Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  

5. En el **propiedades** panel para el **Message_1**, realice lo siguiente:  


   |   Use   |                                                                                                                                                                                                                                                                                           Para                                                                                                                                                                                                                                                                                           |
   |--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  Identificador  |                                                                                                                                                                                                                                                                                         Escriba `Request`                                                                                                                                                                                                                                                                                         |
   | Tipo de mensaje | En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *ConcurrentProgram.OracleEBSBindingSchema.RACUST*, donde ConcurrentProgram es el nombre de su proyecto de BizTalk. OracleEBSBindingSchema es el esquema generado para invocar el **interfaz cliente** programa simultáneo. **Nota:** RACUST es el nombre real de la **interfaz cliente** programa simultáneo. Mientras el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra el nombre descriptivo (**interfaz cliente**), el esquema contiene el nombre real del programa simultáneo. |


6. Repita el paso 3 para crear tres nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  

   |Identificador de conjunto para|Establecer el tipo de mensaje en|  
   |-----------------------|-------------------------|  
   |Respuesta|*ConcurrentProgram.OracleEBSBindingSchema.RACUSTResponse*|  
   |Get_StatusRequest|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgram*|  
   |Get_StatusResponse|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgramResponse*|  

## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar programas simultáneos en Oracle E-Business Suite. En esta orquestación, se puede quitar un mensaje de solicitud en una determinada ubicación de recepción. La orquestación consume este mensaje y lo pasa a Oracle E-Business Suite para invocar el **interfaz cliente** programa simultáneo. La respuesta para el programa simultáneo se recibe de Oracle y se guarda en otra ubicación. El mensaje de respuesta contiene un identificador de solicitud. La orquestación se incluye un **construir mensaje** forma para extraer el identificador de solicitud de la respuesta y construir un mensaje que se ajusta al esquema de la **Get_Status** programa simultáneo. El mensaje para invocar el **Get_Status** programa simultáneo se envía a Oracle E-Business Suite con el identificador de solicitud como un parámetro. Debe incluir el envío y recepción de formas, las formas de construcción de mensajes y puertos para enviar mensajes a Oracle y recibir respuestas.  

 Normalmente, el **interfaz cliente** programa simultáneo tardará bastante tiempo en ejecutarse, por lo que deberá esperar antes de ejecutar el **Get_Status** simultáneas. Puede automatizar mediante la adición de un **retraso** forma.  

 Una orquestación de ejemplo es similar al siguiente:  

 ![Orquestación para invocar programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a02e9d8-8ea8-4898-8d05-c060761f4feb.gif "2a02e9d8-8ea8-4898-8d05-c060761f4feb")  

### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la **forma** columna corresponden a las formas de mensaje como se muestra en la orquestación anterior.  

|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
|SendGetStatus|Send|-Establecer **nombre** a *SendGetStatus*|  
|ReceiveStatusResponse|Receive|-Establecer **nombre** a *ReceiveStatusResponse*<br />-Establecer **activar** a *False*|  
|SaveStatusResponse|Send|-Establecer **nombre** a *SaveStatusResponse*|  

### <a name="adding-a-delay-shape"></a>Agregar una forma retraso  
 Si desea que la orquestación debe esperar entre invocar el **interfaz cliente** y **Get_Status** programas simultáneos, debe agregar un **retraso** forma a la orquestación. Debe agregar un **retraso** forma después de la orquestación de copia de la respuesta para la **interfaz cliente** programa simultáneo en un archivo de puerto de envío. Por lo tanto, debe agregar un **retraso** forma después de la **SendResponse** forma.  

 Dentro de la **retraso** forma, puede especificar el intervalo de tiempo para el que la orquestación debe esperar antes de continuar agregando el código siguiente en el Editor de expresiones para la **retraso** forma:  

```  
new System.TimeSpan(0,2,0)  
```  

 Al agregar este código, la orquestación esperará durante dos minutos antes de continuar. Para obtener más información sobre cómo configurar el **retraso** forma, vea [cómo configurar la forma retraso](../../core/how-to-configure-the-delay-shape.md).  

### <a name="adding-the-construct-message-shape"></a>Adición de la forma construir mensaje  
 La respuesta de Oracle E-Business Suite para la **interfaz cliente** programa simultáneo contiene un identificador de solicitud. Para obtener el estado del programa simultáneo, debe pasar el mismo identificador de solicitud como un parámetro a la **Get_Status** programa simultáneo. Para ello, en la orquestación, debe incluir un **construir mensaje** forma y dentro de ese un **asignación de mensajes** forma. El propósito de la **construir mensaje** forma es:  

- Para extraer el identificador de solicitud de la respuesta que se recibió para la **interfaz cliente** programa simultáneo.  

- Para construir un mensaje que se ajusta al esquema de mensajes para el **Get_Status** programa simultáneo.  

  Para el **construir mensaje** forma, establezca el **mensaje construido** propiedad **Get_StatusRequest**.  

  Para el **asignación de mensajes** forma, agregue la siguiente. Antes de agregar el código, debe tener:  

```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<GetStatusForConcurrentProgram xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR'><RequestId /></GetStatusForConcurrentProgram>");  
Get_StatusRequest = XmlDoc;  
Get_StatusRequest.RequestId = xpath(Response,"string(/*[local-name()='RACUSTResponse']/*[local-name()='RACUSTResult']/text())");  
```  

### <a name="adding-ports"></a>Agregar puertos  
 Para configurar los puertos, especifique las propiedades enumeradas en la tabla siguiente para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna corresponden a los nombres de los puertos que se muestran en la orquestación.  

|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*<br />-Creación de una operación *Cust_Interface*. Esta operación se usa para la **interfaz cliente** programa simultáneo.<br />-Creación de una operación *Get_Status*. Esta operación se usa para la **Get_Status** programa simultáneo.|  
|LOBPort_GetStatus|-Establecer **identificador** a *LOBPort_GetStatus*<br />-Establecer **tipo** a *LOBPort_GetStatusType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica los valores de propiedad para especificar los mensajes de las formas de acción y vincularlos a los puertos. Los nombres que aparecen en la **forma** columna se corresponden con los nombres de las formas de mensaje como se muestra en el diagrama de orquestación.  

 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  

 Debe ahora compile la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  

|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.Cust_Interface.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBport.Cust_Interface.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBport.Cust_Interface.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.Cust_Interface.Request*|  
|SendGetStatus|-Establecer **mensaje** a *Get_StatusRequest*<br />-Establecer **operación** a *LOBPort_GetStatus.Get_Status.Request*|  
|ReceiveStatusResponse|-Establecer **mensaje** a *Get_StatusResponse*<br />-Establecer **operación** a *LOBPort_GetStatus.Get_Status.Response*|  
|SaveStatusResponse|-Establecer **mensaje** a *Get_StatusResponse*<br />-Establecer **operación** a *ResponseOut.Get_Status.Request*|  

 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  

 Debe ahora compile la solución de BizTalk y, a continuación, implementarlo en un servidor BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  

## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).  

 Configuración de una aplicación implica:  

- Selección de un host de la aplicación.  

- Asignación de los puertos que ha creado en la orquestación con puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para esta orquestación, debe:  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a Oracle E-Business Suite.  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de Oracle E-Business Suite.  

  - Definir dos físico WCF-Custom o WCF-OracleEBS de puertos de envío: uno para enviar mensajes a Oracle E-Business Suite para ejecutar el **interfaz cliente** programa simultáneo y otro para ejecutar el **Get_Status**programa simultáneo. También debe especificar la acción en los puertos de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).  

     Para invocar programas simultáneos con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe establecer el contexto de la aplicación correcta en el que se invoca la operación. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona algunas propiedades de enlace para especificar el contexto de la aplicación para cualquier operación. Debe establecer estas propiedades de enlace en el puerto de WCF-Custom o WCF-OracleEBS utilizado para invocar programas simultáneos.  

    - Si el **ClientCredentialType** enlaza la propiedad se establece en **base de datos**, a continuación, debe especificar las siguientes propiedades de enlace para establecer el contexto de las aplicaciones.  


      |        Propiedad de enlace         |                                                                                                                                                                                                                                                                                     Valor                                                                                                                                                                                                                                                                                     |
      |---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |       **OracleUserName**        | Especifique el nombre de un usuario de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no conserva el caso del valor que especifique para la **OracleUserName** enlaza la propiedad cuando se conecta a Oracle E-Business Suite. El nombre de usuario se pasa a Oracle E-Business Suite utilizando las reglas estándar de SQL\*Plus. Sin embargo, si desea que el caso de que se conserve el nombre de usuario o si desea especificar un nombre de usuario que contiene caracteres especiales, debe especificar el valor entre comillas dobles. |
      |       **OraclePassword**        |   La contraseña del usuario de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no conserva el caso del valor que especifique para la **OraclePassword** enlaza la propiedad cuando se conecta a Oracle E-Business Suite. La contraseña se pasa a Oracle E-Business Suite utilizando las reglas estándar de SQL\*Plus. Sin embargo, si desea que el caso de la contraseña que se va a conservar o si desea escribir una contraseña que contiene caracteres especiales, debe especificar el valor entre comillas dobles.    |
      | **OracleEBSResponsibilityName** |                                                                                                                                                                                                                                                     La responsabilidad asociada con el usuario de Oracle E-Business Suite.                                                                                                                                                                                                                                                      |


    - Si el **ClientCredentialType** enlaza la propiedad se establece en **EBusiness**, deben haber especificado las credenciales de Oracle E-Business al establecer la conexión. En este caso sólo debe especificar el valor para el **OracleEBSResponsibilityName** enlaza la propiedad.  

      Para obtener más información acerca de las propiedades de enlace diferente, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener más información sobre cómo el adaptador admite establecer el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

    > [!NOTE]
    >  Puede establecer el contexto de la aplicación mediante la especificación de las propiedades de enlace o estableciendo las propiedades de contexto expuestas por el mensaje el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener instrucciones sobre cómo establecer el contexto de la aplicación mediante las propiedades de contexto de mensaje, consulte [configurar las propiedades del mensaje utilizando aplicación contexto contexto en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).  
    > 
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un físico puerto de enlace con un archivo de enlace de puerto para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  

## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk antes de invocar los programas simultáneos. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  

 En esta etapa, asegúrese de que:  

-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  

-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  

-   El WCF-Custom o WCF-OracleEBS puerto de envío para invocar el **interfaz cliente** se está ejecutando el programa simultáneo.  

-   El WCF-Custom o WCF-OracleEBS puerto de envío para invocar el **Get_Status** se está ejecutando el programa simultáneo.  

-   La orquestación de BizTalk para la operación se está ejecutando.  

## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud que se ajusta al esquema para invocar el **interfaz cliente** programa simultáneo. Por ejemplo, el mensaje de solicitud para invocar la **interfaz cliente** programa simultáneo es:  

```  
<RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <Description>Customer Interface Program</Description>  
  <StartTime></StartTime>  
  <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
  <ORG_ID>203</ORG_ID>  
</RACUST>  
```  

> [!NOTE]
>  El mensaje de solicitud para invocar un programa simultáneo requiere algunos parámetros opcionales como SetOptions, SetPrintOptions y SetRepeatOptions. El mensaje de solicitud que se proporcionan aquí no contiene estos parámetros opcionales. Para obtener información sobre el mensaje de solicitud completa, incluidos los parámetros opcionales, vea [esquemas de mensaje para programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md).  

 La orquestación consume el mensaje, lo pasa a Oracle E-Business Suite y recibe una respuesta. El mensaje de respuesta se guarda en la otra ubicación de archivo especificada como parte de la orquestación. La respuesta para el programa de interfaz de cliente simultánea es similar al siguiente:  

```  
<?xml version="1.0" encoding="utf-8"?>  
<RACUSTResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <RACUSTResult>2794708</RACUSTResult>  
</RACUSTResponse>  
```  

 La respuesta de Oracle E-Business Suite contiene un identificador de solicitud. La orquestación extrae el identificador de solicitud del mensaje de respuesta, construye un mensaje para invocar el **Get_Status** programa simultáneo y lo pasa a Oracle E-Business Suite para ejecutar el **Get_Status** programa simultáneo. Después de recibir la respuesta para th **Get_Status** programa simultáneo, se copia en la misma ubicación de archivo que la primera respuesta. La respuesta para la **Get_Status** programa simultáneo es similar al siguiente:  

```  
<?xml version="1.0" encoding="utf-8" ?>   
<GetStatusForConcurrentProgramResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <GetStatusForConcurrentProgramResult>true</GetStatusForConcurrentProgramResult>   
  <Phase>Pending</Phase>   
  <Status>Standby</Status>   
  <DevPhase>PENDING</DevPhase>   
  <DevStatus>STANDBY</DevStatus>   
  <Message>null</Message>   
</GetStatusForConcurrentProgramResponse>  
```  

## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Después de generar un archivo de enlace, puede importar la configuración del archivo, por lo que no es necesario crear elementos como puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)