---
title: Ejecuta operaciones en los componentes empresariales con MVG campos mediante BizTalk Server y el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c5db211-76a2-4c27-97f4-382302c722da
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f2e1f867ba4f7759afa67a271bc6523b93e9a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-mvg-fields-using-biztalk-server-and-the-siebel-adapter"></a>Ejecuta operaciones en los componentes empresariales con MVG campos mediante BizTalk Server y el adaptador de Siebel
Esta sección proporciona instrucciones acerca de cómo realizar la operación en un componente empresarial que contiene campos de valores múltiple. Para mostrar una operación to-end en dichos componentes empresariales, debe realizar:  
  
-   Una operación de INSERCIÓN en un componente empresarial de primario  
  
-   Una operación de INSERCIÓN en un componente empresarial de secundarios  
  
-   Una operación de asociación de los vínculos a varios valores entre el componente empresarial primario y secundario  
  
-   Una operación de Query_ [MVG_Child_Business_Comp] en un registro de componente empresarial primario  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite operaciones en componentes empresariales, vea [operaciones en los componentes empresariales](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md). Para obtener más información acerca de la estructura de SOAP de los mensajes para llevar a cabo estas operaciones, vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
## <a name="how-to-perform-operations-on-a-business-component-with-multi-value-fields"></a>¿Cómo realizar operaciones en un componente empresarial con campos de varios valores?  
 Realizar una operación en un sistema Siebel mediante la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md). Para llevar a cabo una operación en un componente empresarial, estas tareas son:  
  
1.  Cree un proyecto de BizTalk y genere el esquema para todas las operaciones que desea invocar en el componente empresarial. Como se describió anteriormente, para realizar operaciones en un componente empresarial con campos de varios valores, debe generar esquema para la operación de inserción en los componentes empresariales primarios y secundarios, asocie la operación en los vínculos de varios valores entre los primarios y secundarios componentes empresariales y una operación de consulta en el componente empresarial primario.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes desde el sistema Siebel.  
  
3.  Crear la orquestación para invocar las operaciones diferentes en el sistema Siebel.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, MVLDemo, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo asociar el componente empresarial primario, **cuenta** a un componente empresarial secundario, **póngase en contacto con**, se generará el esquema para lo siguiente:  
  
-   Operación de INSERCIÓN en el **cuenta** componente empresarial. Vea [ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md).  
  
-   Operación de INSERCIÓN en el **póngase en contacto con** componente empresarial.  
  
-   Operación de asociación en el **cuenta** componente empresarial.  
  
-   Operación QUERY_CONTACT en la **cuenta** componente empresarial.  
  
 Vea [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 De este tema, debe crear cuatro conjuntos de mensajes de solicitud y respuesta, uno para cada operación que se va a invocar en el sistema Siebel. Cada conjunto debe tener un mensaje de solicitud y un mensaje de respuesta. Por ejemplo, el procedimiento siguiente proporciona instrucciones para crear un mensaje de solicitud y respuesta para la operación de asociación. Debe realizar pasos similares para crear mensajes para otras operaciones.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema:  
  
### <a name="create-messages-and-link-to-schema"></a>Crear mensajes y vincular al esquema  
  
1.  Abra la vista de orquestación del proyecto de BizTalk, si no está abierto. Haga clic en **vista**, seleccione **otras ventanas**y haga clic en **Vista orquestación**.  
  
2.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el recién crear mensaje y seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **AccountAssociate_Request**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *MVLDemo.SiebelBindingSchema.Associate*, donde *MVLDemo* es el nombre de su proyecto de BizTalk. *SiebelBindingSchema* es el esquema generado para llamar la *asociar* operación en *cuenta* componente empresarial.|  
  
5.  Repita el paso anterior para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **AccountAssociate_Response**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *MVLDemo.SiebelBindingSchema.AssociateResponse*.|  
  
## <a name="set-up-the-orchestrations"></a>Configurar las orquestaciones  
 Ahora debe configurar orquestaciones para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para realizar operaciones en los componentes empresariales de cuenta y contacto.  
  
-   Configurar una orquestación para realizar una operación de INSERCIÓN en el **cuenta** componente empresarial. Vea [ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md).  
  
-   Configurar una orquestación para realizar una operación de INSERCIÓN en el **póngase en contacto con** componente empresarial. Esto es similar a la operación de INSERCIÓN en el **cuenta** componente empresarial.  
  
-   Configurar una orquestación para realizar una operación de asociación en el **cuenta** componente empresarial.  
  
-   Configurar una orquestación para realizar una operación de QUERY_CONTACT en el **cuenta** componente empresarial.  
  
 En este tema se explica cómo configurar una orquestación para la operación de asociación en el **cuenta** componente empresarial. Debe realizar otras tareas similares para configurar las orquestaciones restantes también.  
  
 La orquestación para la operación de asociación en el componente de negocio de la cuenta tiene el siguiente aspecto:  
  
 ![Orquestación para trabajar con MVL en Siebel](../../adapters-and-accelerators/adapter-siebel/media/6c7d548d-dc80-490f-89fe-12aff10fa3cf.gif "6c7d548d-dc80-490f-89fe-12aff10fa3cf")  
  
 En la siguiente sección proporciona información sobre cómo configurar esta orquestación colocando las formas de mensaje, puertos, mensajes de vinculación a esquemas, etcetera. Debe realizar otras tareas similares para configurar las otras orquestaciones.  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|AccountAssociateXML|Receive|-Establecer **nombre** a *AccountAssociateXML*<br />-Establecer **activar** a *es True*|  
|SendToLOB|Send|-Establecer **nombre** a *SendToLOB*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la *puerto* columna son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|FileIn_AccountAssociate|-Establecer **identificador** a *FileIn_AccountAssociate*<br />-Establecer **tipo** a *FileInAccountAssociateType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort_AccountAssociate|-Establecer **identificador** a *LOBPort_AccountAssociate*<br />-Establecer **tipo** a *LOBPortAccountAssociateType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse_AccountAssociate|-Establecer **identificador** a *SaveResponse_AccountAssociate*<br />-Establecer **tipo** a *SaveResponseAccountAssociateType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y los valores que se pueden establecer para especificar los mensajes para formas de acción y vincularlos a los puertos. Los nombres que aparecen en la *forma* columna son los nombres de las formas de mensaje como se muestra en la orquestación anterior.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|AccountAssociateXML|-Establecer **mensaje** a *AccountAssociate_Request*<br />-Establecer **operación** a *FileIn_AccountAssociate.Associate.Request*|  
|SendToLOB|-Establecer **mensaje** a *AccountAssociate_Request*<br />-Establecer **operación** a *LOBPort_AccountAssociate.Associate.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *AccountAssociate_Response*<br />-Establecer **operación** a *LOBPort_AccountAssociate.Associate.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse_AccountAssociate.Associate.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [cómo generar orquestaciones](../../core/how-to-build-orchestrations.md) y [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [cómo crear una aplicación](../../core/how-to-create-an-application.md).  
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviar al sistema Siebel. Puede tener el mismo puerto para todas las cuatro orquestaciones.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta en el sistema Siebel. Puede tener el mismo puerto para todas las cuatro orquestaciones.  
  
    -   Definir los puertos de envío WCF-Custom o WCF-Siebel físicos para enviar mensajes al sistema Siebel. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md). Debe tener puertos diferentes para todas las cuatro orquestaciones.  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk para crear puertos de envío (para las llamadas salientes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para asociar un componente de negocio principal para el componente empresarial secundario. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [iniciar una aplicación de BizTalk](../../core/how-to-start-and-stop-a-biztalk-application.md) o [iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   Se ejecutan los cuatro WCF-Custom o WCF-Siebel puertos de envío, uno para enviar mensajes al sistema Siebel,  
  
-   Se ejecutan las orquestaciones de BizTalk cuatro de las distintas operaciones  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Debe quitar la solicitud de puerto de recepción de mensajes en el archivo. El esquema para los mensajes de solicitud debe cumplir el esquema generado anteriormente en este tema. Vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) para obtener más información acerca del esquema del mensaje de solicitud para operaciones diferentes. Debe quitar los mensajes de solicitud en el orden siguiente:  
  
-   Quitar un mensaje de solicitud para insertar un registro en el **cuenta** componente empresarial. El mensaje de solicitud será similar a la que se quitan para insertar un registro en el componente de negocio de la cuenta en el tema [ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md). La orquestación consume el mensaje y lo envía al sistema Siebel. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación.  
  
-   Quitar un mensaje de solicitud para insertar un registro en el **póngase en contacto con** componente empresarial. El mensaje de solicitud será similar a la que se quitan para insertar un registro en el componente de negocio de la cuenta en el tema [ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md). La orquestación consume el mensaje y lo envía al sistema Siebel. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación.  
  
-   Quitar un mensaje de solicitud para realizar una operación de asociación en el **cuenta** componente empresarial. Esto asociará los componentes empresariales primarios y secundarios en función de la expresión de búsqueda y el nombre del campo con varios valores que especifique en el XML de entrada. Tenga en cuenta lo siguiente:  
  
    -   La expresión de búsqueda de elemento primario en la operación de asociación debe coincidir con un registro único en la tabla primaria.  
  
    -   La expresión de búsqueda secundaria en la operación de asociación debe coincidir con un registro único en la tabla secundaria.  
  
     Por ejemplo, el mensaje de solicitud para realizar una operación de asociación en el componente de negocio de la cuenta es:  
  
    ```  
    <Associate xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <ViewMode>3</ViewMode>  
      <ParentSearchExpr>[Name] LIKE "SampleName1"</ns0:ParentSearchExpr>   
      <ParentMVGField>Bill To First Name</ns0:ParentMVGField>   
      <ChildSearchExpr>[First Name] LIKE "SampleName2"</ns0:ChildSearchExpr>   
    </Associate>  
    ```  
  
     La orquestación consume el mensaje y lo envía al sistema Siebel. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta para el mensaje de solicitud anterior es:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <AssociateResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <AssociateResult>  
        <ChildID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8AO09</ChildID>  
        <ParentID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8ANZ5</ParentID>  
      </AssociateResult>  
    </AssociateResponse>  
    ```  
  
-   Quitar un mensaje de solicitud para realizar una operación de QUERY_CONTACT en el **cuenta** componente empresarial. Por ejemplo, el mensaje de solicitud para una operación de QUERY_CONTACT es:  
  
    ```  
    <Query_Contact xmlns ="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <ViewMode>3</ViewMode>   
      <ParentSearchExpr>[Name] LIKE "SampleName1"</ParentSearchExpr>   
      <ParentMVGField>Bill To First Name</ParentMVGField>   
      <ContactQueryInputRecord>  
        <SearchExpr xmlns:ns1="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">[Id] LIKE '*'</SearchExpr>   
      </ContactQueryInputRecord>  
    </Query_Contact>  
    ```  
  
     La orquestación consume el mensaje y lo envía al sistema Siebel. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación.  
  
 Vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) para obtener más información acerca del esquema del mensaje de solicitud.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede surgir al realizar una operación en el componente de negocio con campos multivalor mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)