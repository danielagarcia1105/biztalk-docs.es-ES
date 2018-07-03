---
title: Ejecutar operaciones en componentes empresariales con campos de lista desplegable mediante BizTalk Server y el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, perform operations with picklist fields by using BizTalk Server
- business components, performing operations with picklist fields by using BizTalk Server
ms.assetid: b62d32fa-903a-442b-951b-2343ef719bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c722caaad6e1474ac80a14843171550aa53b9d77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986085"
---
# <a name="run-operations-on-business-components-with-picklist-fields-using-biztalk-server-and-the-siebel-adapter"></a>Ejecutar operaciones en componentes empresariales con campos de lista desplegable mediante BizTalk Server y el adaptador de Siebel
Un tipo de campo de lista desplegable de Siebel constituye una colección de valores posibles de cliente que puede especificar un valor determinado que se pasarán al sistema Siebel. En otras palabras, un campo de lista desplegable contiene una lista de valores aceptados para un campo. Para obtener más información acerca de la lista desplegable y sus tipos, consulte la documentación de Siebel. Para obtener más información acerca de cómo los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite operaciones en componentes empresariales con campos de lista desplegable, vea [operaciones en componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md).  
  
 Al generar metadatos para un componente de negocio que contenga un campo estático de lista desplegable delimitado (un tipo de lista desplegable), los valores aceptados para la lista desplegable también se publican como parte de los metadatos. Si va a insertar un valor en un campo de lista desplegable, debe especificar un valor que se publica en los metadatos.  
  
## <a name="how-to-perform-operations-on-business-components-with-picklist-fields"></a>¿Cómo realizar operaciones en componentes empresariales con campos de lista desplegable?  
 Realizar una operación en un sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md). 
 
 Para completar una operación en un componente empresarial con el campo de lista desplegable, estas tareas son:  
  
1. Cree un proyecto de BizTalk y generar el esquema para llevar a cabo una operación en un componente empresarial que contiene campos de lista desplegable.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema Siebel.  
  
3. Crear la orquestación para invocar una operación en el sistema Siebel.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, SiebelPicklist, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo invocar operaciones en componentes empresariales con campos de lista desplegable, se generará el esquema para el **insertar** operación para la **cuenta** componente empresarial. El **cuenta** componente empresarial tiene una lista desplegable estática, *tipo de encuesta*.  
  
 Consulte [recuperación de metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) para obtener más información acerca de cómo generar un esquema.  
  
 Al generar los metadatos de la operación de inserción para el **cuenta** componente empresarial, obtendrá un archivo .xsd independiente que contiene los campos de lista desplegable y sus valores posibles. Tenga en cuenta que el .xsd contiene solo los valores para las listas desplegables estáticas, incluidos *tipo de encuesta*.  
  
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
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *SiebelPicklist.SiebelBindingSchema.Insert*, donde *SiebelPicklist* es el nombre de su proyecto de BizTalk. *SiebelBindingSchema* es el esquema generado para invocar el *insertar* operación en *cuenta* componente empresarial.|  
  
5.  Repita el paso anterior para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *SiebelPicklist.SiebelBindingSchema.InsertResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo una operación de inserción en un componente empresarial de Siebel con campos de lista desplegable. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consume este mensaje y lo pasa por el sistema Siebel. La respuesta en el sistema Siebel se guarda en otra ubicación. Contendría una orquestación para realizar operaciones en componentes empresariales de Siebel típica:  
  
- Enviar y recibir las formas para enviar mensajes a Siebel y recibir respuestas.  
  
- Puerto para recibir mensajes de solicitud para enviar a Siebel de recepción unidireccional.  
  
- Puerto para enviar mensajes de solicitud a Siebel y recibir respuestas de envío bidireccional.  
  
- Un puerto de envío unidireccional para enviar las respuestas de Siebel a una carpeta.  
  
  Una orquestación de ejemplo para el *insertar* operación en un *cuenta* componente empresarial es similar al siguiente:  
  
  ![Orquestación para insertar valores de lista desplegable para Siebel](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")  
  
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
|ReceiveXml|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.Picklist.Request*|  
|SendToLOB|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Picklist.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Picklist.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.Picklist.Request*|  
  
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
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para llevar a cabo una *insertar* operación en el *cuenta* componente empresarial de Siebel. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [iniciar una aplicación de BizTalk](../../core/how-to-start-and-stop-a-biztalk-application.md) o [iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   Se está ejecutando el puerto de envío WCF-Custom o WCF-Siebel para enviar mensajes al sistema Siebel  
  
-   La orquestación de BizTalk para la operación se está ejecutando  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Debe quitar el mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema generado anteriormente en este tema. Consulte [esquemas de mensaje para operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) para obtener más información acerca del esquema para los mensajes de solicitud.  
  
 Para insertar un valor para el campo de lista desplegable, examine el esquema generado para determinar la lista de valores aceptables para la lista desplegable. Asegúrese de que el mensaje de solicitud tiene un elemento que se va a insertar un valor para el campo de lista desplegable. Por ejemplo, el mensaje de solicitud debe contener el siguiente elemento para insertar el valor para el *tipo de encuesta* lista desplegable.  
  
 `<Survey_x0020_Type>1</Survey_x0020_Type>`  
  
 En este caso, "1" es un valor aceptable para la lista de selección del tipo de encuesta.  
  
 Es un mensaje de solicitud de ejemplo que contiene un parámetro de la lista desplegable:  
  
```  
<Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <ArrayOfAccountInsertRecord>  
    <AccountInsertRecord xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">  
      <Currency_x0020_Code>usd</Currency_x0020_Code>  
      <Current_x0020_Volume>9</Current_x0020_Volume>  
      <Customer_x0020_Account_x0020_Group>Sold-To Party</Customer_x0020_Account_x0020_Group>  
      <Location>Location_1</Location>  
      <Main_x0020_Phone_x0020_Number>4256543212</Main_x0020_Phone_x0020_Number>  
      <Name>Name_Surname</Name>  
      <Party_x0020_Name>test_party</Party_x0020_Name>  
      <Primary_x0020_Address_x0020_Id>1212 street</Primary_x0020_Address_x0020_Id>  
      <Survey_x0020_Type>1</Survey_x0020_Type>  
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 La orquestación consume el mensaje de solicitud y lo pasa al sistema Siebel. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación.  
  
> [!NOTE]
>  También puede intentar una inserción de un valor no válido para la lista desplegable. En ese caso, debe obtener un `TargetSystemException`.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede aparecer al realizar una operación en el componente empresarial con campos de lista desplegable con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío, recepción, puertos, etc., de la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar los enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)