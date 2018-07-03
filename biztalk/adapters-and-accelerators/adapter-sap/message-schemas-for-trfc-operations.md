---
title: Los esquemas de mensajes para operaciones de tRFC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC operations, message structure for
- tRFC operations, message schemas for
- tRFC operations, message actions for
ms.assetid: 0e269555-f0a1-40ae-a1b5-d8c4981e730f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a25413854b35a7bd27b3621a9c8ddfff31f083a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999781"
---
# <a name="message-schemas-for-trfc-operations"></a>Esquemas de mensaje para operaciones de tRFC
Llamadas a funciones remotas Transactiostructnal (trfc) se usan para ejecutar las llamadas a RFC en una unidad lógica de trabajo (LUW). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite varios trfc por LUW para llamadas de tRFC de entrada. Para las llamadas de tRFC salientes (cliente), el adaptador puede admitir solo un único tRFC en un LUW; por lo tanto, para crea un LUW en SAP para cada llamada de cliente tRFC. Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite operaciones de tRFC, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). Esta sección describen los esquemas de mensaje y las acciones para las operaciones de tRFC.  

## <a name="message-structure-for-trfc-operations"></a>Estructura de mensaje para operaciones de tRFC  
 Cada operación tRFC consta de un mensaje de solicitud y un mensaje de respuesta (respuesta). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asocia un GUID de la transacción de sistema SAP TID (Id.) que identifica el LUW en el sistema SAP. Este GUID puede estar presente en los tRFC de solicitud y respuesta mensajes en el \<TransactionalRfcOperationIdentifier\> elemento.  

-   Para las llamadas de tRFC saliente, puede pasar un GUID para el adaptador en el mensaje de solicitud tRFC. Si no se proporciona un GUID, el adaptador genera uno automáticamente. El adaptador siempre devuelve el GUID en el mensaje de respuesta tRFC. Pase este GUID en la operación RfcConfirmTransID para confirmar el TID en el sistema SAP.  

-   Para las llamadas de tRFC de entrada, el adaptador pasa un GUID que ha generado y asignada para el TID de SAP en el mensaje de solicitud tRFC. Si lo desea, puede devolver este GUID en el mensaje de respuesta.  

> [!IMPORTANT]
>  En algunos escenarios, por ejemplo, para solucionar un problema en el sistema SAP, es posible que necesita el valor real del TID de SAP que identifica el tRFC en el sistema SAP. Puede obtener el valor del TID de SAP que está asociado con un GUID mediante una llamada a la **ConvertGuidToTid** método. Para obtener más información acerca de **ConvertGuidToTid**, consulte [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md).  

 La siguiente tabla muestra los esquemas de mensaje utilizados para operaciones de tRFC y para la operación RfcConfirmTransID. La operación RfcConfirmTransID es obtenida por el adaptador para que pueda confirmar el TID de SAP en las llamadas de tRFC de cliente.  


|                             Operación                             |                                                                                                                                                                                                                                                                         Operaciones de recepción de estructuras de mensajes para IDOC                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                             Descripción                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   tRFC<br /><br /> ([RFC_NAME])                   | `<[RFC_NAME] xmlns="[VERSION]/Trfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Trfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   …   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]>` | Invoca un tRFC en el sistema SAP.<br /><br /> -Importar, cambiar, y se admiten parámetros de la tabla.<br /><br /> -Importar y cambiar los parámetros puede ser de tipos de estructura de SAP, SAP tabla tipos o tipos de datos simples de SAP.<br /><br /> -llamadas de cliente tRFC no tienen valores devueltos en el lado de salida. SAP ejecuta de forma asincrónica ellos con solo los valores de lado de entrada.<br /><br /> El \<TransactionalRfcOperationIdentifier\> elemento:<br /><br /> -Para las llamadas de tRFC saliente, también puede especificar un GUID que se debe asignar al TID SAP el adaptador en este elemento. Si no se especifica un GUID, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno y le asigna el TID de SAP para el tRFC.<br /><br /> -Para las llamadas de tRFC de entrada, el adaptador pasa el GUID que se asigna al TID SAP de este elemento. |
|          Respuesta de tRFC<br /><br /> (Respuesta [RFC_NAME])           |                                                                                                                                                                                                   `<[RFC_NAME]Response xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]Response>`                                                                                                                                                                                                   |                                                                                                                                                                   Indica que se ha enviado la solicitud de cambio al sistema SAP.<br /><br /> -llamadas de cliente tRFC no tienen valores devueltos en el lado de salida. SAP ejecuta de forma asincrónica ellos con solo los valores de lado de entrada.<br /><br /> El \<TransactionalRfcOperationIdentifier\> elemento:<br /><br /> -Para las llamadas de tRFC saliente, el adaptador envía el GUID asociado con el TID de SAP para la tRFC de este elemento.<br /><br /> -Para las llamadas de tRFC de entrada, opcionalmente, puede devolver el GUID que se envió el adaptador en el mensaje de solicitud.                                                                                                                                                                    |
|         RfcConfirmTransID<br /><br /> (RfcConfirmTransID)         |                                                                                                                                                                                                    `<RfcConfirmTransID xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </RfcConfirmTransID>`                                                                                                                                                                                                    |                                                                                                                                                             La operación RfcConfirmTransID confirma el TID utilizado en una operación de tRFC saliente en el sistema SAP.<br /><br /> El \<TransactionalRfcOperationIdentifier\> elemento contiene el GUID que se asigna al TID asociado con la llamada saliente tRFC. Debe establecerlo en el valor del GUID que se devolvió el adaptador en el mensaje de respuesta tRFC.<br /><br /> Para obtener más información acerca de la operación RfcConfirmTransID, consulte [operaciones especiales](../../adapters-and-accelerators/adapter-sap/special-operations.md).                                                                                                                                                              |
| RfcConfirmTransIDResponse<br /><br /> (RfcConfirmTransIDResponse) |                                                                                                                                                                                                                                      `<RfcConfirmTransIDResponse xmlns="[VERSION]/Trfc/"> </RfcConfirmTransIDResponse>`                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                   Indica que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ha confirmado el TID en el sistema SAP.                                                                                                                                                                                                                                                                                                                                                                    |

 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [RFC_NAME] = nombre de la solicitud de cambio; Por ejemplo, RFC_CUSTOMER_GET.  

 [IN_PARAM_NAME] = el nombre del parámetro de importación de RFC.  

 [INOUT_PARAM_NAME] = el nombre de un parámetro RFC cambiar.  

 [TABLE_PARAM_NAME] = el nombre de un parámetro de la tabla de RFC.  

 [STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura de RFC.  

 GUID = GUID que identifica el TID SAP asociado con el tRFC.  

## <a name="message-actions-for-trfc-operations"></a>Acciones de mensaje para operaciones de tRFC  
 La siguiente tabla muestra las acciones de mensaje que se usan para las operaciones de tRFC.  


|         Operación          |              Acción de mensaje              |                                 Ejemplo                                  |
|----------------------------|------------------------------------------|--------------------------------------------------------------------------|
|         [RFC_NAME]         |        /Trfc/ [versión] [RFC_NAME]         |      http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET      |
|    [RFC_NAME] Respuesta     |    /Trfc/ [versión] [RFC_NAME] / respuesta    | http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET/response  |
|     RfcConfirmTransID      |     [Versión] / Trfc/RfcConfirmTransID     |     http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID      |
| Respuesta RfcConfirmTransID | [Versión/Trfc/RfcConfirmTransID/respuesta | http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID/response |

 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [RFC_NAME] = nombre de la solicitud de cambio que se debe invocar; Por ejemplo, RFC_CUSTOMER_GET.  

## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)