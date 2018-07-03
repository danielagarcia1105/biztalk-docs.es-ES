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
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a><span data-ttu-id="dec68-102">Paso 3b: recuperar detalles de oportunidades de Salesforce con el adaptador WCF-WebHttp</span><span class="sxs-lookup"><span data-stu-id="dec68-102">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>
<span data-ttu-id="dec68-103">En esta sección, mejoraremos la orquestación para procesar la notificación de oportunidad entrante, extraer el nombre de la oportunidad de la notificación y usarlo para crear una consulta que se enviará a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dec68-103">In this section, we’ll enhance the orchestration to process the incoming opportunity notification, extract the opportunity name from the notification, and use that to create a request query to send to Salesforce.</span></span> <span data-ttu-id="dec68-104">Con ella, recuperaremos detalles concretos de los productos asociados con la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="dec68-104">This retrieves specific details about the products associated with the opportunity.</span></span> <span data-ttu-id="dec68-105">La respuesta de Salesforce a la consulta se recibe en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dec68-105">The query response from Salesforce is received back into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="dec68-106">Para lograr esto, realizaremos los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="dec68-106">To achieve this, we’ll perform the following steps:</span></span>  
  
-   <span data-ttu-id="dec68-107">Crear un esquema y variables de mensaje para enviar un mensaje de consulta a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dec68-107">Create a schema and message variables to send a query message to Salesforce.</span></span>  
  
-   <span data-ttu-id="dec68-108">Crear una asignación para usar los valores de la notificación de oportunidad para crear una consulta que recupere detalles de los productos asociados con la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="dec68-108">Create a map to use the values from the opportunity notification for creating a query to retrieve product details associated with the opportunity.</span></span>  
  
-   <span data-ttu-id="dec68-109">Crear un esquema para recibir una respuesta de Salesforce a la consulta.</span><span class="sxs-lookup"><span data-stu-id="dec68-109">Create a schema to receive a query response from Salesforce.</span></span>  
  
-   <span data-ttu-id="dec68-110">Crear variables de mensaje para los esquemas de la solicitud y la respuesta.</span><span class="sxs-lookup"><span data-stu-id="dec68-110">Create message variables for the request and response schemas.</span></span>  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a><span data-ttu-id="dec68-111">Crear un esquema y variables de mensaje para enviar mensajes de consulta a Salesforce</span><span class="sxs-lookup"><span data-stu-id="dec68-111">Create Schema and Message Variables to Send Query Messages to Salesforce</span></span>  
 <span data-ttu-id="dec68-112">Para recuperar detalles de productos de Salesforce usando la información disponible en la notificación de oportunidad, debemos enviar una consulta a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dec68-112">To retrieve product details from Salesforce by using the information available through an Opportunity notification, we need to send a query to Salesforce.</span></span> <span data-ttu-id="dec68-113">La consulta se envía a Salesforce con formato de mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="dec68-113">The query is sent to Salesforce as an XML message.</span></span> <span data-ttu-id="dec68-114">Por tanto, en el procedimiento siguiente, crearemos un esquema para el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="dec68-114">So, in the following procedure we create a schema for the request message.</span></span> <span data-ttu-id="dec68-115">En el procedimiento posterior, asignaremos el esquema de la notificación de oportunidad a este esquema para construir una consulta que nos permita recuperar detalles de los productos de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="dec68-115">In the subsequent procedure, we will map the opportunity notification schema with this schema to construct a query for retrieving product details for the opportunity.</span></span>  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a><span data-ttu-id="dec68-116">Para crear un esquema para enviar la solicitud de consulta</span><span class="sxs-lookup"><span data-stu-id="dec68-116">To create a schema for sending query request</span></span>  
  
1. <span data-ttu-id="dec68-117">Agregue un esquema nuevo al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dec68-117">Add a new schema to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="dec68-118">Asígnele el nombre `QueryRequest.xsd`.</span><span class="sxs-lookup"><span data-stu-id="dec68-118">Name it `QueryRequest.xsd`.</span></span>  
  
2. <span data-ttu-id="dec68-119">Cambiar el nombre del nodo raíz a `QueryRequest`.</span><span class="sxs-lookup"><span data-stu-id="dec68-119">Rename the root node to `QueryRequest`.</span></span> <span data-ttu-id="dec68-120">Agregue un elemento de campo secundario en el registro QueryRequest y asígnele el nombre `Query`.</span><span class="sxs-lookup"><span data-stu-id="dec68-120">Add a child field element under the QueryRequest record and name it `Query`.</span></span>  
  
3. <span data-ttu-id="dec68-121">Promover la **consulta** elemento en el esquema para que esté disponible para su uso dentro de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="dec68-121">Promote the **Query** element in the schema so that it is available for use within the orchestration.</span></span> <span data-ttu-id="dec68-122">En los pasos siguientes, usaremos este elemento promovido para asignar la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="dec68-122">In the later steps we will use this promoted element to assign the query string.</span></span>  
  
    <span data-ttu-id="dec68-123">Haga clic en el **consulta** elemento, seleccione **promover**y, a continuación, haga clic en **promociones rápidas**.</span><span class="sxs-lookup"><span data-stu-id="dec68-123">Right-click the **Query** element, point to **Promote**, and then click **Quick Promotions**.</span></span> <span data-ttu-id="dec68-124">Esto da como resultado en la creación de un **PropertySchema.xsd** esquema con un **consulta** elemento.</span><span class="sxs-lookup"><span data-stu-id="dec68-124">This results in creating a **PropertySchema.xsd** schema with a **Query** element.</span></span> <span data-ttu-id="dec68-125">Tome nota del espacio de nombres para PropertySchema.</span><span class="sxs-lookup"><span data-stu-id="dec68-125">Note the namespace for the PropertySchema.</span></span> <span data-ttu-id="dec68-126">Lo necesitará en pasos futuros para configurar los puertos físicos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dec68-126">You will need this in the future steps while configuring the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4. <span data-ttu-id="dec68-127">Guarde todos los cambios.</span><span class="sxs-lookup"><span data-stu-id="dec68-127">Save all changes.</span></span>  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a><span data-ttu-id="dec68-128">Asignar el esquema de la notificación de oportunidad al esquema de la consulta</span><span class="sxs-lookup"><span data-stu-id="dec68-128">Map the Opportunity Notification Schema to the Query Schema</span></span>  
 <span data-ttu-id="dec68-129">Para recuperar los detalles de productos asociados con la oportunidad, debemos enviar a Salesforce una consulta similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="dec68-129">To retrieve the product details associated with the opportunity, we need to send a query similar to the following to Salesforce:</span></span>  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 <span data-ttu-id="dec68-130">En el procedimiento anterior, ya creamos el esquema del mensaje de consulta.</span><span class="sxs-lookup"><span data-stu-id="dec68-130">In the previous procedure we already created the schema of the query message.</span></span> <span data-ttu-id="dec68-131">En este procedimiento, asignaremos el esquema de la notificación de oportunidad al esquema de la solicitud de consulta y usaremos functoids para construir la consulta.</span><span class="sxs-lookup"><span data-stu-id="dec68-131">In this procedure, we map the opportunity notification schema to the query request schema and use functoids to construct this query.</span></span> <span data-ttu-id="dec68-132">Esta consulta se pasará como un valor para el **consulta** elemento en el **QueryRequest.xsd** esquema.</span><span class="sxs-lookup"><span data-stu-id="dec68-132">This query will be passed as a value to the **Query** element in the **QueryRequest.xsd** schema.</span></span>  
  
#### <a name="to-map-the-opportunity-notification"></a><span data-ttu-id="dec68-133">Para asignar la notificación de oportunidad</span><span class="sxs-lookup"><span data-stu-id="dec68-133">To map the opportunity notification</span></span>  
  
1. <span data-ttu-id="dec68-134">Agregue un esquema al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dec68-134">Add a map to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="dec68-135">Nombre de la asignación `Notification_QueryRequest.btm`.</span><span class="sxs-lookup"><span data-stu-id="dec68-135">Name the map `Notification_QueryRequest.btm`.</span></span>  
  
2. <span data-ttu-id="dec68-136">Establece el esquema de origen en **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span><span class="sxs-lookup"><span data-stu-id="dec68-136">Set the source schema to **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span></span> <span data-ttu-id="dec68-137">Establece el esquema de destino en **QueryRequest**.xsd.</span><span class="sxs-lookup"><span data-stu-id="dec68-137">Set the destination schema to **QueryRequest**.xsd.</span></span>  
  
3. <span data-ttu-id="dec68-138">Agregar un **concatenación de cadenas** functoid a la superficie de asignación.</span><span class="sxs-lookup"><span data-stu-id="dec68-138">Add a **String Concatenate** functoid to the mapping surface.</span></span> <span data-ttu-id="dec68-139">Abra el **configurar Functoid de concatenación de cadenas** diálogo cuadro y especifique los valores de entrada como sigue:</span><span class="sxs-lookup"><span data-stu-id="dec68-139">Open the **Configure String Concatenate Functoid** dialog box and specify the input values as follows:</span></span>  
  
   |||  
   |-|-|  
   |<span data-ttu-id="dec68-140">Entrada[0]</span><span class="sxs-lookup"><span data-stu-id="dec68-140">Input[0]</span></span>|<span data-ttu-id="dec68-141">SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '</span><span class="sxs-lookup"><span data-stu-id="dec68-141">SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '</span></span>|  
   |<span data-ttu-id="dec68-142">Entrada [1]</span><span class="sxs-lookup"><span data-stu-id="dec68-142">Input[1]</span></span>|<span data-ttu-id="dec68-143">Conecte el elemento Name del esquema de origen al functoid para usar el valor del elemento Name como segunda entrada.</span><span class="sxs-lookup"><span data-stu-id="dec68-143">Connect the Name element in the source schema to the functoid to use the value of the Name element as the second input.</span></span>|  
   |<span data-ttu-id="dec68-144">Entrada [2]</span><span class="sxs-lookup"><span data-stu-id="dec68-144">Input[2]</span></span>|<span data-ttu-id="dec68-145">' **Nota:** para el último valor de entrada, especifique solo una comilla simple de cierre (').</span><span class="sxs-lookup"><span data-stu-id="dec68-145">' **Note:**  For the last input value, specify only a closing single quote (').</span></span>|  
  
    <span data-ttu-id="dec68-146">Captura de pantalla siguiente muestra la configuración para el **concatenación de cadenas** functoid.</span><span class="sxs-lookup"><span data-stu-id="dec68-146">The following screenshot depicts the configuration for the **String Concatenate** functoid.</span></span>  
  
    <span data-ttu-id="dec68-147">![Configurar el functoid de concatenación de cadenas](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")</span><span class="sxs-lookup"><span data-stu-id="dec68-147">![Configure String Concatenate functoid](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")</span></span>  
  
    <span data-ttu-id="dec68-148">Una vez concatenados los tres parámetros de entrada, formará la consulta necesaria para enviarla a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dec68-148">When the three input parameters are concatenated, it will form the required query to be sent to Salesforce.</span></span>  
  
4. <span data-ttu-id="dec68-149">Conecte el functoid Concatenación de cadenas al elemento Query en el esquema de destino, como se muestra en la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="dec68-149">Connect the String Concatenate functoid to the Query element in the destination schema, as shown in the following screenshot.</span></span>  
  
    <span data-ttu-id="dec68-150">![Asignar la respuesta de notificación al esquema de la consulta](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")</span><span class="sxs-lookup"><span data-stu-id="dec68-150">![Map notification response to query schema](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")</span></span>  
  
5. <span data-ttu-id="dec68-151">Guarde los cambios de la asignación.</span><span class="sxs-lookup"><span data-stu-id="dec68-151">Save changes to the map.</span></span>  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a><span data-ttu-id="dec68-152">Crear un esquema para recibir el mensaje de respuesta a la consulta</span><span class="sxs-lookup"><span data-stu-id="dec68-152">Creating Schema to Receive the Query Response Message</span></span>  
 <span data-ttu-id="dec68-153">En esta sección, crearemos el esquema para recibir el mensaje de Salesforce en respuesta a la consulta.</span><span class="sxs-lookup"><span data-stu-id="dec68-153">In this section, we create the schema to receive the query response message from Salesforce.</span></span> <span data-ttu-id="dec68-154">Crearemos manualmente el esquema para la respuesta a la consulta.</span><span class="sxs-lookup"><span data-stu-id="dec68-154">In this section, we manually create the schema for the query response.</span></span>  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a><span data-ttu-id="dec68-155">Para crear un esquema para recibir la respuesta a la consulta</span><span class="sxs-lookup"><span data-stu-id="dec68-155">To create a schema to receive the query response</span></span>  
  
1. <span data-ttu-id="dec68-156">Agregue un nuevo esquema para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del proyecto y asígnele el nombre `QueryResult.xsd`.</span><span class="sxs-lookup"><span data-stu-id="dec68-156">Add a new schema to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project and name it `QueryResult.xsd`.</span></span>  
  
2. <span data-ttu-id="dec68-157">Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017) objeto muestra la respuesta de la consulta recibida de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dec68-157">The Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017) object depicts the query response received from Salesforce.</span></span> <span data-ttu-id="dec68-158">Por tanto, compilaremos un esquema para representar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dec68-158">So, we’ll build a schema to depict the following:</span></span>  
  
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
  
    <span data-ttu-id="dec68-159">La estructura del esquema debe ser como esta:</span><span class="sxs-lookup"><span data-stu-id="dec68-159">The schema structure should look like the following:</span></span>  
  
    <span data-ttu-id="dec68-160">![Esquema de respuesta de la consulta de Salesforce](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")</span><span class="sxs-lookup"><span data-stu-id="dec68-160">![Schema for query response from Salesforce](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")</span></span>  
  
3. <span data-ttu-id="dec68-161">Guarde los cambios del esquema.</span><span class="sxs-lookup"><span data-stu-id="dec68-161">Save changes to the schema.</span></span>  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a><span data-ttu-id="dec68-162">Crear variables de mensaje para los esquemas QueryRequest y QueryResult</span><span class="sxs-lookup"><span data-stu-id="dec68-162">Create Message Variables for QueryRequest and QueryResult Schemas</span></span>  
 <span data-ttu-id="dec68-163">Una vez creados los esquemas QueryRequest y QueryResult, debe crear dos variables de mensaje en la orquestación para representar los dos tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="dec68-163">After you have created the QueryRequest and QueryResult schemas, you must create two message variables in the orchestration to represent the two message types.</span></span>  
  
#### <a name="to-create-message-variables"></a><span data-ttu-id="dec68-164">Procedimiento para crear variables de mensaje</span><span class="sxs-lookup"><span data-stu-id="dec68-164">To create message variables</span></span>  
  
1.  <span data-ttu-id="dec68-165">Abra el **NotificationService.odx** orquestación y, en la Vista orquestación, agregue dos nuevos mensajes.</span><span class="sxs-lookup"><span data-stu-id="dec68-165">Open the **NotificationService.odx** orchestration and in the orchestration view, add two new messages.</span></span> <span data-ttu-id="dec68-166">Establecer los nombres de mensaje `QueryRequestMsg` y `QueryResultMsg`.</span><span class="sxs-lookup"><span data-stu-id="dec68-166">Set the message names as `QueryRequestMsg` and `QueryResultMsg`.</span></span>  
  
2.  <span data-ttu-id="dec68-167">Establezca el tipo de mensaje para **QueryRequestMsg** como **BtsSalesforceIntegration.QueryRequest**.</span><span class="sxs-lookup"><span data-stu-id="dec68-167">Set the message type for **QueryRequestMsg** as **BtsSalesforceIntegration.QueryRequest**.</span></span>  
  
3.  <span data-ttu-id="dec68-168">Establezca el tipo de mensaje para **QueryResultMsg** como **BtsSalesforceIntegration.QueryResult**.</span><span class="sxs-lookup"><span data-stu-id="dec68-168">Set the message type for **QueryResultMsg** as **BtsSalesforceIntegration.QueryResult**.</span></span>  
  
4.  <span data-ttu-id="dec68-169">Guarde los cambios de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="dec68-169">Save changes to the orchestration.</span></span>  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a><span data-ttu-id="dec68-170">Actualizar la orquestación para enviar el mensaje a Salesforce y recibir una respuesta</span><span class="sxs-lookup"><span data-stu-id="dec68-170">Update the Orchestration to Send Message to Salesforce and Receive a Response</span></span>  
 <span data-ttu-id="dec68-171">En el tema [paso 3a: recibir notificaciones de oportunidades de Salesforce en BizTalk Server](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md), creamos la orquestación que recibe notificaciones de oportunidades de Salesforce y envía una confirmación.</span><span class="sxs-lookup"><span data-stu-id="dec68-171">In the topic [Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md), we built the orchestration that receives opportunity notifications from Salesforce and sends an acknowledgement.</span></span> <span data-ttu-id="dec68-172">En este paso, ampliaremos esta orquestación para enviar una solicitud de consulta a Salesforce con el fin de obtener detalles de los productos relacionados con la oportunidad y recibir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="dec68-172">In this step, we build on this orchestration to send a query request to Salesforce to get product details related to the opportunity and receive a response.</span></span> <span data-ttu-id="dec68-173">Ya hemos creado los esquemas (QueryRequest.xsd y QueryResult.xsd) y las variables de mensaje (QueryRequestMsg y QueryResultMsg) que usaremos en este paso.</span><span class="sxs-lookup"><span data-stu-id="dec68-173">We have already created the schemas (QueryRequest.xsd and QueryResult.xsd) and the message variables (QueryRequestMsg and QueryResultMsg) that we’ll use in this step.</span></span>  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a><span data-ttu-id="dec68-174">Para enviar una solicitud de consulta a Salesforce y recibir una respuesta</span><span class="sxs-lookup"><span data-stu-id="dec68-174">To send a query request to Salesforce and receive a response</span></span>  
  
1. <span data-ttu-id="dec68-175">Agregar una forma construir mensaje después de la **SendNotificationAck** forma.</span><span class="sxs-lookup"><span data-stu-id="dec68-175">Add a Construct Message shape after the **SendNotificationAck** shape.</span></span> <span data-ttu-id="dec68-176">Establezca el nombre de la forma a `ConstructQuery` y establezca el **mensajes construidos** propiedad **QueryRequestMsg**.</span><span class="sxs-lookup"><span data-stu-id="dec68-176">Set the name of the shape to `ConstructQuery` and set the **Messages Constructed** property to **QueryRequestMsg**.</span></span>  
  
2. <span data-ttu-id="dec68-177">Dentro de la **ConstructQuery** forma, agregue un **transformar** forma.</span><span class="sxs-lookup"><span data-stu-id="dec68-177">Within the **ConstructQuery** shape, add a **Transform** shape.</span></span> <span data-ttu-id="dec68-178">Haga doble clic en la forma Transformar para abrir el cuadro de diálogo Configuración de Transformación.</span><span class="sxs-lookup"><span data-stu-id="dec68-178">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="dec68-179">En el cuadro de diálogo, seleccione el **mapa existente** opción y, a continuación, en la lista desplegable seleccione **BtsSalesforceIntegration.Notification_QueryRequest**.</span><span class="sxs-lookup"><span data-stu-id="dec68-179">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.Notification_QueryRequest**.</span></span> <span data-ttu-id="dec68-180">Establecer **origen** a **NotificaitonMessage**, **destino** a **QueryRequestMsg**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dec68-180">Set **Source** to **NotificaitonMessage**, **Destination** to **QueryRequestMsg**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="dec68-181">Dentro de la **ConstructQuery** forma, después de la forma transformación, agregue una forma asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dec68-181">Within the **ConstructQuery** shape, after the Transform shape, add a Message Assignment shape.</span></span> <span data-ttu-id="dec68-182">Haga doble clic en la forma Asignación de mensajes y agregue la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="dec68-182">Double-click the Message Assignment shape and add the following expression:</span></span>  
  
   ```  
   QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
   ```  
  
    <span data-ttu-id="dec68-183">Haciendo esto, pasamos el valor de la **consulta** elemento en el **QueryRequestMsg** esquema para el elemento promovido **consulta** en el esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="dec68-183">By doing this, we pass on the value of the **Query** element in the **QueryRequestMsg** schema to the promoted element **Query** in the property schema.</span></span> <span data-ttu-id="dec68-184">Para la configuración del puerto WCF-WebHttp, usaremos este elemento para pasar de forma dinámica el valor de la consulta al mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="dec68-184">While configuring the WCF-WebHttp port, we’ll use this element to dynamically pass on the query value to the request message.</span></span>  
  
4. <span data-ttu-id="dec68-185">Después de la **ConstructQuery** forma, agregue una forma envío.</span><span class="sxs-lookup"><span data-stu-id="dec68-185">After the **ConstructQuery** shape, add a Send shape.</span></span> <span data-ttu-id="dec68-186">Nombre de la forma `SendQueryRequest` y establezca el tipo de mensaje **QueryRequestMsg**.</span><span class="sxs-lookup"><span data-stu-id="dec68-186">Name the shape `SendQueryRequest` and set the message type as **QueryRequestMsg**.</span></span>  
  
5. <span data-ttu-id="dec68-187">Después de la forma envío, agregue una forma recepción y asígnele el nombre `ReceiveQueryResult`.</span><span class="sxs-lookup"><span data-stu-id="dec68-187">After the Send shape, add a Receive shape and name it `ReceiveQueryResult`.</span></span> <span data-ttu-id="dec68-188">Establezca el tipo de mensaje de la forma en **QueryResultMsg**.</span><span class="sxs-lookup"><span data-stu-id="dec68-188">Set the message type of the shape to **QueryResultMsg**.</span></span>  
  
6. <span data-ttu-id="dec68-189">Agregue un puerto para enviar solicitudes de consulta a Salesforce y recibir el resultado de las consultas en respuesta.</span><span class="sxs-lookup"><span data-stu-id="dec68-189">Add a port to send query requests to Salesforce and receive the query result in response.</span></span> <span data-ttu-id="dec68-190">En el Asistente para configuración de puertos, seleccione las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dec68-190">In the Port Configuration wizard, select the following options:</span></span>  
  
   - <span data-ttu-id="dec68-191">Especifique el nombre de puerto `SalesforceRESTInterface`.</span><span class="sxs-lookup"><span data-stu-id="dec68-191">Specify the port name as `SalesforceRESTInterface`.</span></span>  
  
   - <span data-ttu-id="dec68-192">Seleccione la opción Crear un nuevo tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="dec68-192">Select the option to create a new port type.</span></span>  
  
   - <span data-ttu-id="dec68-193">Establecer **patrón de comunicación** a *solicitud-respuesta*.</span><span class="sxs-lookup"><span data-stu-id="dec68-193">Set **Communication Pattern** to *Request-Response*.</span></span>  
  
   - <span data-ttu-id="dec68-194">Establecer **dirección de puerto de comunicación** a *enviaré una solicitud y recibiré una respuesta* y establecer **enlace de puerto** a *especificarposterior*.</span><span class="sxs-lookup"><span data-stu-id="dec68-194">Set **Port direction of communication** to *I’ll be sending a request and receiving a response* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="dec68-195">Conectar el **solicitar** operación del puerto a la forma envío (*SendQueryRequest*) y el **respuesta** operación del puerto a la forma recepción ( *ReceiveQueryResult*).</span><span class="sxs-lookup"><span data-stu-id="dec68-195">Connect the **Request** operation of port to the Send shape (*SendQueryRequest*) and the **Response** operation of the port to the Receive shape (*ReceiveQueryResult*).</span></span> <span data-ttu-id="dec68-196">La siguiente captura de pantalla muestra la parte de la orquestación que representa el proceso de envío de la solicitud de consulta a Salesforce y la recepción de una respuesta.</span><span class="sxs-lookup"><span data-stu-id="dec68-196">The following screenshot depicts the part of the orchestration that represents the process of sending the query request to Salesforce and receiving a response.</span></span>  
  
     <span data-ttu-id="dec68-197">![Enviar una consulta a Salesforce y recibir respuesta](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")</span><span class="sxs-lookup"><span data-stu-id="dec68-197">![Send a query to Salesforce and receive response](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")</span></span>  
  
   <span data-ttu-id="dec68-198">En este tema, hemos actualizado la orquestación para enviar una solicitud de consulta a Salesforce y recibir más detalles (como productos, cantidad, etc.) de la oportunidad que se creó en Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dec68-198">In this topic, we updated the orchestration to send a query request to Salesforce and receive more details (such as products, quantity, etc.) about the opportunity that is created in Salesforce.</span></span> <span data-ttu-id="dec68-199">En los temas siguientes, actualizaremos esta solución para incluir la respuesta de Salesforce en una base de datos de SQL Server local.</span><span class="sxs-lookup"><span data-stu-id="dec68-199">In the subsequent topics, we will update this solution to enter the Salesforce response into an on-premise SQL Server database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec68-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="dec68-200">See Also</span></span>  
 [<span data-ttu-id="dec68-201">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dec68-201">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)