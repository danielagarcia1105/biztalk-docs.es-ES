---
title: Los esquemas de mensajes para operaciones de RFC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 156b8e8c218c4ad23d49959323ed324b0c7cdfd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972853"
---
# <a name="message-schemas-for-rfc-operations"></a>Esquemas de mensaje para operaciones de RFC
La [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone las llamadas de funciones remotas (RFC) de SAP como operaciones. Este tema contiene información sobre los esquemas de mensaje y las acciones de mensaje que se utiliza para operaciones de RFC. La estructura del mensaje es el mismo para las operaciones de RFC de entrada y salidas. Para obtener información general de las operaciones de RFC que admite el adaptador, vea [operaciones en RFC de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).  

 También puede invocar BAPI como operaciones de RFC en el adaptador. En este tema se incluye un ejemplo de la estructura del mensaje de una invocación.  

## <a name="message-structure-for-rfc-operations"></a>Estructura de mensaje para operaciones de RFC  
 La siguiente tabla muestra los esquemas de mensaje RFC. Cada operación de RFC consta de un mensaje de solicitud y un mensaje de respuesta (respuesta).  


|                             de mensaje                              |                                                                                                                                                                                                                         Estructura de los mensajes XML                                                                                                                                                                                                                          |                                                                                                                                                                                                     Descripción                                                                                                                                                                                                      |
|------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   RFC<br /><br /> ([RFC_NAME])                   | `<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>` |                                                                                              Invocación de una solicitud de cambio en el sistema SAP.<br /><br /> -Importar, cambiar, y se admiten parámetros de la tabla.<br /><br /> -Importar y cambiar los parámetros puede ser de tipos de estructura de SAP, SAP tabla tipos o tipos de datos simples de SAP.                                                                                              |
|                RFC respuesta (respuesta [RFC_NAME])                 |     `<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`      | RFC devuelto.<br /><br /> -Exportar, cambiar, y se admiten parámetros de la tabla.<br /><br /> **Nota:** de forma predeterminada, los parámetros de la tabla no se exponen en el mensaje de respuesta. Si se requieren parámetros de la tabla en el mensaje de respuesta, debe pasar los parámetros de la tabla vacía en el mensaje de solicitud.<br /><br /> -Importar y cambiar los parámetros puede ser de tipos de estructura de SAP, SAP tabla tipos o tipos de datos simples de SAP. |
|         RfcGetAttributes<br /><br /> (RfcGetAttributes)          |                                                                                                                                                                                                                `<RfcGetAttributes> </RfcGetAttributes>`                                                                                                                                                                                                                |                                                  RfcGetAttributes es una operación de API de RFC SDK que se expone a través de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. La operación RfcGetAttributes permite que un programa cliente recuperar el idioma, el identificador del sistema y la página de códigos de asociados que están asociados con la conexión RFC.                                                   |
| Respuesta RfcGetAttributes<br /><br /> (RfcGetAttributesResponse) |                                                                                                                                                          `<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`                                                                                                                                                           |                                                                                                                              La respuesta a la operación RfcGetAttributes devuelve el idioma, el identificador del sistema y la página de códigos de asociados que están asociados con la conexión RFC.                                                                                                                              |

 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.SAP/2007/03.  

 [RFC_NAME] = nombre de la solicitud de cambio; Por ejemplo, RFC_CUSTOMER_GET.  

 [IN_PARAM_NAME] = el nombre de un parámetro de importación de RFC.  

 [OUT_PARAM_NAME] = el nombre de un parámetro RFC exportar.  

 [INOUT_PARAM_NAME] = el nombre de un parámetro RFC cambiar.  

 [TABLE_PARAM_NAME] = el nombre de un parámetro de la tabla de RFC.  

 [STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura de RFC.  

## <a name="message-actions-for-rfc-operations"></a>Acciones de mensaje para operaciones de RFC  
 La siguiente tabla muestra las acciones de mensaje para operaciones de RFC.  


|         Operación         |           Acción de mensaje           |                                Ejemplo                                 |
|---------------------------|------------------------------------|------------------------------------------------------------------------|
|        [RFC_NAME]         |      /Rfc/ [versión] [RFC_NAME]      |     http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET      |
|    [RFC_NAME] Respuesta    | /Rfc/ [versión] [RFC_NAME] / respuesta  | http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET/response |
|     RfcGetAttributes      |     [Versión] / RfcGetAttributes     |       http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes        |
| Respuesta RfcGetAttributes | [Versión/RfcGetAttributes/respuesta |   http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes/response   |

 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [RFC_NAME] = nombre de la solicitud de cambio que se debe invocar; Por ejemplo, RFC_CUSTOMER_GET.  

## <a name="invoking-a-bapi-as-an-rfc-operation"></a>Invocar una BAPI como una operación de RFC  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies BAPI como operaciones de RFC y como métodos de objetos de negocios. Como las operaciones de RFC, BAPI aparecen por nombre. Para obtener más información sobre cómo invocar BAPI mediante el uso de la interfaz de objetos de negocios, vea [operaciones en BAPI de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).  

 El siguiente XML muestra la estructura del mensaje para una BAPI (BAPI_CUSTOMER_GETDETAIL2) que se invoca como una solicitud de cambio. La acción de mensaje para esta operación es: http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2.  

```  
<BAPI_CUSTOMER_GETDETAIL2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <COMPANYCODE>1001</COMPANYCODE>  
  <CUSTOMERNO>0000001001</CUSTOMERNO>  
  <CUSTOMERBANKDETAIL>  
    <BAPICUSTOMER_02 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <CUSTOMER />  
      <BANK_CTRY />  
      <BANK_KEY />  
      <BANK_ACCT />  
      <CTRL_KEY />  
      <PARTNER_BK />  
      <COLL_AUTH />  
      <BANK_REF />  
    </BAPICUSTOMER_02>  
  </CUSTOMERBANKDETAIL>  
</BAPI_CUSTOMER_GETDETAIL2>  
```  

## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)