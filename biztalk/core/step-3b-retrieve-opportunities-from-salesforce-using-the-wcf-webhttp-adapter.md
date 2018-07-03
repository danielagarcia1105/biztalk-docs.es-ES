---
title: 'Paso 3b: recuperar detalles de oportunidades de Salesforce con el adaptador WCF-WebHttp | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 115c908f-777b-4c51-85ea-71d639b01775
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66337277e2a84edbe8802b739988bcee030bc054
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008117"
---
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a>Paso 3b: recuperar detalles de oportunidades de Salesforce con el adaptador WCF-WebHttp
En esta sección, mejoraremos la orquestación para procesar la notificación de oportunidad entrante, extraer el nombre de la oportunidad de la notificación y usarlo para crear una consulta que se enviará a Salesforce. Con ella, recuperaremos detalles concretos de los productos asociados con la oportunidad. La respuesta de Salesforce a la consulta se recibe en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para lograr esto, realizaremos los siguientes pasos:  
  
-   Crear un esquema y variables de mensaje para enviar un mensaje de consulta a Salesforce.  
  
-   Crear una asignación para usar los valores de la notificación de oportunidad para crear una consulta que recupere detalles de los productos asociados con la oportunidad.  
  
-   Crear un esquema para recibir una respuesta de Salesforce a la consulta.  
  
-   Crear variables de mensaje para los esquemas de la solicitud y la respuesta.  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a>Crear un esquema y variables de mensaje para enviar mensajes de consulta a Salesforce  
 Para recuperar detalles de productos de Salesforce usando la información disponible en la notificación de oportunidad, debemos enviar una consulta a Salesforce. La consulta se envía a Salesforce con formato de mensaje XML. Por tanto, en el procedimiento siguiente, crearemos un esquema para el mensaje de solicitud. En el procedimiento posterior, asignaremos el esquema de la notificación de oportunidad a este esquema para construir una consulta que nos permita recuperar detalles de los productos de la oportunidad.  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a>Para crear un esquema para enviar la solicitud de consulta  
  
1. Agregue un esquema nuevo al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Asígnele el nombre `QueryRequest.xsd`.  
  
2. Cambiar el nombre del nodo raíz a `QueryRequest`. Agregue un elemento de campo secundario en el registro QueryRequest y asígnele el nombre `Query`.  
  
3. Promover la **consulta** elemento en el esquema para que esté disponible para su uso dentro de la orquestación. En los pasos siguientes, usaremos este elemento promovido para asignar la cadena de consulta.  
  
    Haga clic en el **consulta** elemento, seleccione **promover**y, a continuación, haga clic en **promociones rápidas**. Esto da como resultado en la creación de un **PropertySchema.xsd** esquema con un **consulta** elemento. Tome nota del espacio de nombres para PropertySchema. Lo necesitará en pasos futuros para configurar los puertos físicos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
4. Guarde todos los cambios.  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a>Asignar el esquema de la notificación de oportunidad al esquema de la consulta  
 Para recuperar los detalles de productos asociados con la oportunidad, debemos enviar a Salesforce una consulta similar a la siguiente:  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 En el procedimiento anterior, ya creamos el esquema del mensaje de consulta. En este procedimiento, asignaremos el esquema de la notificación de oportunidad al esquema de la solicitud de consulta y usaremos functoids para construir la consulta. Esta consulta se pasará como un valor para el **consulta** elemento en el **QueryRequest.xsd** esquema.  
  
#### <a name="to-map-the-opportunity-notification"></a>Para asignar la notificación de oportunidad  
  
1. Agregue un esquema al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Nombre de la asignación `Notification_QueryRequest.btm`.  
  
2. Establece el esquema de origen en **NotificationService_soap_sforce_com_2005_09_outbound.xsd**. Establece el esquema de destino en **QueryRequest**.xsd.  
  
3. Agregar un **concatenación de cadenas** functoid a la superficie de asignación. Abra el **configurar Functoid de concatenación de cadenas** diálogo cuadro y especifique los valores de entrada como sigue:  
  
   |||  
   |-|-|  
   |Entrada[0]|SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '|  
   |Entrada [1]|Conecte el elemento Name del esquema de origen al functoid para usar el valor del elemento Name como segunda entrada.|  
   |Entrada [2]|' **Nota:** para el último valor de entrada, especifique solo una comilla simple de cierre (').|  
  
    Captura de pantalla siguiente muestra la configuración para el **concatenación de cadenas** functoid.  
  
    ![Configurar el functoid de concatenación de cadenas](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")  
  
    Una vez concatenados los tres parámetros de entrada, formará la consulta necesaria para enviarla a Salesforce.  
  
4. Conecte el functoid Concatenación de cadenas al elemento Query en el esquema de destino, como se muestra en la siguiente captura de pantalla.  
  
    ![Asignar la respuesta de notificación al esquema de la consulta](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")  
  
5. Guarde los cambios de la asignación.  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a>Crear un esquema para recibir el mensaje de respuesta a la consulta  
 En esta sección, crearemos el esquema para recibir el mensaje de Salesforce en respuesta a la consulta. Crearemos manualmente el esquema para la respuesta a la consulta.  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a>Para crear un esquema para recibir la respuesta a la consulta  
  
1. Agregue un nuevo esquema para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto y asígnele el nombre `QueryResult.xsd`.  
  
2. Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017) objeto muestra la respuesta de la consulta recibida de Salesforce. Por tanto, compilaremos un esquema para representar lo siguiente:  
  
   ```  
   <?xml version="1.0" encoding="utf-16" ?>  
   - <xs:schema xmlns="http://BtsSalesforceIntegration.QueryResult" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://BtsSalesforceIntegration.QueryResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
     - <xs:element name="QueryResult">  
       - <xs:complexType>  
         - <xs:sequence>  
           <xs:element name="done" type="xs:string" />  
           - <xs:sequence>  
             - <xs:element name="records">  
               - <xs:complexType>  
                 - <xs:sequence>  
                   <xs:element name="Id" type="xs:string" />  
                   <xs:element name="Amount" type="xs:string" />  
                   <xs:element name="Name" type="xs:string" />  
                   - <xs:sequence>  
                     - <xs:element name="OpportunityLineItems">  
                       - <xs:complexType>  
                         - <xs:sequence>  
                           <xs:element name="done" type="xs:string" />  
                           - <xs:sequence minOccurs="1" maxOccurs="unbounded">  
                             - <xs:element name="records">  
                               - <xs:complexType>  
                                 - <xs:sequence>  
                                   <xs:element name="Quantity" type="xs:string" />  
                                   <xs:element name="ListPrice" type="xs:string" />  
                                   - <xs:element name="PricebookEntry">  
                                     - <xs:complexType>  
                                       - <xs:sequence>  
                                         <xs:element name="UnitPrice" type="xs:string" />  
                                         <xs:element name="Name" type="xs:string" />  
                                       </xs:sequence>  
                                       <xs:attribute name="type" type="xs:string" />  
                                       <xs:attribute name="url" type="xs:string" />  
                                     </xs:complexType>  
                                   </xs:element>  
                                 </xs:sequence>  
                                 <xs:attribute name="type" type="xs:string" />  
                                 <xs:attribute name="url" type="xs:string" />  
                               </xs:complexType>  
                             </xs:element>  
                           </xs:sequence>  
                           <xs:element name="totalSize" type="xs:string" />  
                         </xs:sequence>  
                       </xs:complexType>  
                     </xs:element>  
                   </xs:sequence>  
                 </xs:sequence>  
                 <xs:attribute name="type" type="xs:string" />  
                 <xs:attribute name="url" type="xs:string" />  
               </xs:complexType>  
             </xs:element>  
           </xs:sequence>  
           <xs:element name="totalSize" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
     </xs:element>  
   </xs:schema>  
   ```  
  
    La estructura del esquema debe ser como esta:  
  
    ![Esquema de respuesta de la consulta de Salesforce](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")  
  
3. Guarde los cambios del esquema.  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a>Crear variables de mensaje para los esquemas QueryRequest y QueryResult  
 Una vez creados los esquemas QueryRequest y QueryResult, debe crear dos variables de mensaje en la orquestación para representar los dos tipos de mensaje.  
  
#### <a name="to-create-message-variables"></a>Procedimiento para crear variables de mensaje  
  
1.  Abra el **NotificationService.odx** orquestación y, en la Vista orquestación, agregue dos nuevos mensajes. Establecer los nombres de mensaje `QueryRequestMsg` y `QueryResultMsg`.  
  
2.  Establezca el tipo de mensaje para **QueryRequestMsg** como **BtsSalesforceIntegration.QueryRequest**.  
  
3.  Establezca el tipo de mensaje para **QueryResultMsg** como **BtsSalesforceIntegration.QueryResult**.  
  
4.  Guarde los cambios de la orquestación.  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a>Actualizar la orquestación para enviar el mensaje a Salesforce y recibir una respuesta  
 En el tema [paso 3a: recibir notificaciones de oportunidades de Salesforce en BizTalk Server](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md), creamos la orquestación que recibe notificaciones de oportunidades de Salesforce y envía una confirmación. En este paso, ampliaremos esta orquestación para enviar una solicitud de consulta a Salesforce con el fin de obtener detalles de los productos relacionados con la oportunidad y recibir una respuesta. Ya hemos creado los esquemas (QueryRequest.xsd y QueryResult.xsd) y las variables de mensaje (QueryRequestMsg y QueryResultMsg) que usaremos en este paso.  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a>Para enviar una solicitud de consulta a Salesforce y recibir una respuesta  
  
1. Agregar una forma construir mensaje después de la **SendNotificationAck** forma. Establezca el nombre de la forma a `ConstructQuery` y establezca el **mensajes construidos** propiedad **QueryRequestMsg**.  
  
2. Dentro de la **ConstructQuery** forma, agregue un **transformar** forma. Haga doble clic en la forma Transformar para abrir el cuadro de diálogo Configuración de Transformación. En el cuadro de diálogo, seleccione el **mapa existente** opción y, a continuación, en la lista desplegable seleccione **BtsSalesforceIntegration.Notification_QueryRequest**. Establecer **origen** a **NotificaitonMessage**, **destino** a **QueryRequestMsg**y, a continuación, haga clic en **Aceptar**.  
  
3. Dentro de la **ConstructQuery** forma, después de la forma transformación, agregue una forma asignación de mensajes. Haga doble clic en la forma Asignación de mensajes y agregue la siguiente expresión:  
  
   ```  
   QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
   ```  
  
    Haciendo esto, pasamos el valor de la **consulta** elemento en el **QueryRequestMsg** esquema para el elemento promovido **consulta** en el esquema de propiedades. Para la configuración del puerto WCF-WebHttp, usaremos este elemento para pasar de forma dinámica el valor de la consulta al mensaje de solicitud.  
  
4. Después de la **ConstructQuery** forma, agregue una forma envío. Nombre de la forma `SendQueryRequest` y establezca el tipo de mensaje **QueryRequestMsg**.  
  
5. Después de la forma envío, agregue una forma recepción y asígnele el nombre `ReceiveQueryResult`. Establezca el tipo de mensaje de la forma en **QueryResultMsg**.  
  
6. Agregue un puerto para enviar solicitudes de consulta a Salesforce y recibir el resultado de las consultas en respuesta. En el Asistente para configuración de puertos, seleccione las siguientes opciones:  
  
   - Especifique el nombre de puerto `SalesforceRESTInterface`.  
  
   - Seleccione la opción Crear un nuevo tipo de puerto.  
  
   - Establecer **patrón de comunicación** a *solicitud-respuesta*.  
  
   - Establecer **dirección de puerto de comunicación** a *enviaré una solicitud y recibiré una respuesta* y establecer **enlace de puerto** a *especificarposterior*.  
  
     Conectar el **solicitar** operación del puerto a la forma envío (*SendQueryRequest*) y el **respuesta** operación del puerto a la forma recepción ( *ReceiveQueryResult*). La siguiente captura de pantalla muestra la parte de la orquestación que representa el proceso de envío de la solicitud de consulta a Salesforce y la recepción de una respuesta.  
  
     ![Enviar una consulta a Salesforce y recibir respuesta](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")  
  
   En este tema, hemos actualizado la orquestación para enviar una solicitud de consulta a Salesforce y recibir más detalles (como productos, cantidad, etc.) de la oportunidad que se creó en Salesforce. En los temas siguientes, actualizaremos esta solución para incluir la respuesta de Salesforce en una base de datos de SQL Server local.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)