---
title: Esquemas de mensajes para operaciones de tRFC | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC operations, message structure for
- tRFC operations, message schemas for
- tRFC operations, message actions for
ms.assetid: 0e269555-f0a1-40ae-a1b5-d8c4981e730f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5667d2f6a9f18bbccbdebc0d5dc36ad73e4867ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-trfc-operations"></a>Esquemas de mensaje para operaciones de tRFC
Llamadas a funciones remotas Transactiostructnal (tRFCs) se usan para ejecutar llamadas RFC en una unidad lógica de trabajo (LUW). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite varios tRFCs por LUW para llamadas de tRFC entrante. Para las llamadas de tRFC saliente (cliente), el adaptador puede admitir solo un único tRFC en un LUW; por lo tanto, para crea un LUW en SAP para cada llamada de cliente tRFC. Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite operaciones de tRFC, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). En esta sección se describe los esquemas de mensaje y las acciones para las operaciones de tRFC.  
  
## <a name="message-structure-for-trfc-operations"></a>Estructura de los mensajes para operaciones de tRFC  
 Cada operación de tRFC consta de un mensaje de solicitud y un mensaje de respuesta (respuesta). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asocia un GUID de la transacción de sistema SAP TID (Id.) que identifica el LUW en el sistema SAP. Este GUID puede estar presente en los tRFC solicitud y respuesta mensajes en el \<TransactionalRfcOperationIdentifier\> elemento.  
  
-   Para las llamadas de tRFC saliente, puede pasar un GUID para el adaptador en el mensaje de solicitud de tRFC. Si no se proporciona un GUID, el adaptador genera uno automáticamente. El adaptador siempre devuelve el GUID en el mensaje de respuesta de tRFC. Pase este GUID en la operación de RfcConfirmTransID para confirmar el TID en el sistema SAP.  
  
-   Para las llamadas de tRFC entrantes, el adaptador pasa un GUID que ha generado y asignado al TID de SAP en el mensaje de solicitud de tRFC. Si lo desea, puede devolver este GUID en el mensaje de respuesta.  
  
> [!IMPORTANT]
>  En algunos escenarios, por ejemplo, para solucionar un problema en el sistema SAP, tendrá el valor real del TID de SAP que identifica el tRFC en el sistema SAP. Puede obtener el valor del TID de SAP que está asociado con un GUID mediante una llamada a la **ConvertGuidToTid** método. Para obtener más información acerca de **ConvertGuidToTid**, consulte [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md).  
  
 La siguiente tabla muestra los esquemas de mensaje utilizados para operaciones de tRFC y para la operación de RfcConfirmTransID. La operación de RfcConfirmTransID es obtenida por el adaptador para que pueda confirmar el TID de SAP en las llamadas de cliente tRFC.  
  
|Operación|Estructura XML|Description|  
|---------------|-------------------|-----------------|  
|TRFC<br /><br /> ([RFC_NAME])|`<[RFC_NAME] xmlns="[VERSION]/Trfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Trfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   …   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]>`|Se invoca un tRFC en el sistema SAP.<br /><br /> -Import, cambiar, y se admiten los parámetros de la tabla.<br /><br /> -Import y cambiar los parámetros puede ser de tipos de estructura de SAP, tipos de tabla de SAP o tipos de datos simples de SAP.<br /><br /> -las llamadas de cliente tRFC no tienen valores devueltos en el lado de salida. SAP ejecuta de forma asincrónica ellos con valores de lado de entrada solamente.<br /><br /> El \<TransactionalRfcOperationIdentifier\> elemento:<br /><br /> -Para las llamadas de tRFC saliente, también puede especificar un GUID que debe asignarse al TID SAP el adaptador en este elemento. Si no se especifica un GUID, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno y lo asigna al TID de SAP para el tRFC.<br /><br /> -Para las llamadas de tRFC entrantes, el adaptador pasa el GUID que se asigna al TID de SAP en este elemento.|  
|Respuesta de tRFC<br /><br /> (Respuesta [RFC_NAME])|`<[RFC_NAME]Response xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]Response>`|Indica que se ha enviado la solicitud de cambio al sistema SAP.<br /><br /> -las llamadas de cliente tRFC no tienen valores devueltos en el lado de salida. SAP ejecuta de forma asincrónica ellos con valores de lado de entrada solamente.<br /><br /> El \<TransactionalRfcOperationIdentifier\> elemento:<br /><br /> -Para las llamadas de tRFC saliente, el adaptador envía el GUID asociado con el TID de SAP para el tRFC en este elemento.<br /><br /> -Para las llamadas de tRFC entrante, opcionalmente, puede devolver el GUID que envió el adaptador en el mensaje de solicitud.|  
|RfcConfirmTransID<br /><br /> (RfcConfirmTransID)|`<RfcConfirmTransID xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </RfcConfirmTransID>`|La operación de RfcConfirmTransID confirma el TID usa en una operación de tRFC saliente en el sistema SAP.<br /><br /> El \<TransactionalRfcOperationIdentifier\> elemento contiene el GUID asignado al TID asociado a la llamada saliente tRFC. Debe establecer esto en el valor del GUID que se devolvió el adaptador en el mensaje de respuesta de tRFC.<br /><br /> Para obtener más información sobre la operación de RfcConfirmTransID, consulte [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md).|  
|RfcConfirmTransIDResponse<br /><br /> (RfcConfirmTransIDResponse)|`<RfcConfirmTransIDResponse xmlns="[VERSION]/Trfc/"> </RfcConfirmTransIDResponse>`|Indica que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ha confirmado el TID en el sistema SAP.|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [RFC_NAME] = nombre de la solicitud de cambio; Por ejemplo, RFC_CUSTOMER_GET.  
  
 [IN_PARAM_NAME] = el nombre del parámetro de importación de RFC.  
  
 [INOUT_PARAM_NAME] = el nombre de un parámetro de RFC cambiar.  
  
 [TABLE_PARAM_NAME] = el nombre de un parámetro de tabla de RFC.  
  
 [STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura de RFC.  
  
 GUID = un GUID que identifica el TID SAP asociados con la tRFC.  
  
## <a name="message-actions-for-trfc-operations"></a>Acciones de mensaje para operaciones de tRFC  
 La siguiente tabla muestra las acciones de mensaje que se utilizan para operaciones de tRFC.  
  
|Operación|Acción de mensaje|Ejemplo|  
|---------------|--------------------|-------------|  
|[RFC_NAME]|/Trfc/ [versión] [RFC_NAME]|http://Microsoft.LobServices.SAP/2007/03/trfc/RFC_CUSTOMER_GET|  
|[RFC_NAME] Respuesta|/Trfc/ [versión] [RFC_NAME] / respuesta|http://Microsoft.LobServices.SAP/2007/03/trfc/RFC_CUSTOMER_GET/Response|  
|RfcConfirmTransID|[Versión] / Trfc/RfcConfirmTransID|http://Microsoft.LobServices.SAP/2007/03/trfc/RfcConfirmTransID|  
|Respuesta de RfcConfirmTransID|[Versión/Trfc/RfcConfirmTransID/respuesta|http://Microsoft.LobServices.SAP/2007/03/trfc/RfcConfirmTransID/Response|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [RFC_NAME] = el nombre de la solicitud de cambio que se debe invocar; Por ejemplo, RFC_CUSTOMER_GET.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)