---
title: Esquemas de mensajes para operaciones de RFC | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9d1dfe3ff3cef27269facfe89d3aea8f43cb10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-rfc-operations"></a>Esquemas de mensaje para las operaciones de RFC
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] superficies de llamadas de función remota (RFC) de SAP como operaciones. Este tema contiene información sobre los esquemas de mensaje y acciones de mensaje que se usan para las operaciones de RFC. La estructura del mensaje es el mismo para las operaciones de RFC entrantes y salientes. Para obtener información general de las operaciones de RFC que admite el adaptador, vea [operaciones en RFC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).  
  
 También puede invocar BAPI como operaciones de RFC en el adaptador. Un ejemplo de la estructura del mensaje de una llamada de este tipo se incluye en este tema.  
  
## <a name="message-structure-for-rfc-operations"></a>Estructura de los mensajes para las operaciones de RFC  
 La siguiente tabla muestra los esquemas de mensaje RFC. Cada operación de RFC consta de un mensaje de solicitud y un mensaje de respuesta (respuesta).  
  
|de mensaje|Estructura de los mensajes XML|Description|  
|-------------|---------------------------|-----------------|  
|RFC<br /><br /> ([RFC_NAME])|`<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>`|Invocar una solicitud de cambio en el sistema SAP.<br /><br /> -Import, cambiar, y se admiten los parámetros de la tabla.<br /><br /> -Import y cambiar los parámetros puede ser de tipos de estructura de SAP, tipos de tabla de SAP o tipos de datos simples de SAP.|  
|Respuesta RFC (respuesta [RFC_NAME])|`<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`|Valor devuelto de RFC.<br /><br /> -Exportar, cambiar, y se admiten los parámetros de la tabla.<br /><br /> **Nota:** de forma predeterminada, los parámetros de tabla no aparecen en el mensaje de respuesta. Si se requieren parámetros de la tabla en el mensaje de respuesta, debe pasar parámetros de una tabla vacía en el mensaje de solicitud.<br /><br /> -Import y cambiar los parámetros puede ser de tipos de estructura de SAP, tipos de tabla de SAP o tipos de datos simples de SAP.|  
|RfcGetAttributes<br /><br /> (RfcGetAttributes)|`<RfcGetAttributes> </RfcGetAttributes>`|RfcGetAttributes es una operación de API de RFC SDK que se expone a través de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. La operación de RfcGetAttributes permite que un programa de cliente recuperar el idioma, el identificador del sistema y la página de códigos de socio comercial que están asociados con la conexión de RFC.|  
|Respuesta de RfcGetAttributes<br /><br /> (RfcGetAttributesResponse)|`<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`|La respuesta a la operación de RfcGetAttributes devuelve el idioma, el identificador del sistema y la página de códigos de socio comercial que están asociados con la conexión de RFC.|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.SAP/2007/03.  
  
 [RFC_NAME] = nombre de la solicitud de cambio; Por ejemplo, RFC_CUSTOMER_GET.  
  
 [IN_PARAM_NAME] = el nombre de un parámetro de importación de RFC.  
  
 [OUT_PARAM_NAME] = el nombre de un parámetro de exportación de RFC.  
  
 [INOUT_PARAM_NAME] = el nombre de un parámetro de RFC cambiar.  
  
 [TABLE_PARAM_NAME] = el nombre de un parámetro de tabla de RFC.  
  
 [STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura de RFC.  
  
## <a name="message-actions-for-rfc-operations"></a>Acciones de mensaje para las operaciones de RFC  
 La siguiente tabla muestra las acciones de mensaje para las operaciones de RFC.  
  
|Operación|Acción de mensaje|Ejemplo|  
|---------------|--------------------|-------------|  
|[RFC_NAME]|/Rfc/ [versión] [RFC_NAME]|http://Microsoft.LobServices.SAP/2007/03/RFC/RFC_CUSTOMER_GET|  
|[RFC_NAME] Respuesta|/Rfc/ [versión] [RFC_NAME] / respuesta|http://Microsoft.LobServices.SAP/2007/03/RFC/RFC_CUSTOMER_GET/Response|  
|RfcGetAttributes|[Versión] / RfcGetAttributes|http://Microsoft.LobServices.SAP/2007/03/RfcGetAttributes|  
|Respuesta de RfcGetAttributes|[Versión/RfcGetAttributes/respuesta|http://Microsoft.LobServices.SAP/2007/03/RfcGetAttributes/Response|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [RFC_NAME] = el nombre de la solicitud de cambio que se debe invocar; Por ejemplo, RFC_CUSTOMER_GET.  
  
## <a name="invoking-a-bapi-as-an-rfc-operation"></a>Invocar una BAPI como una operación de RFC  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies BAPI como operaciones de RFC y como métodos de objetos comerciales. Como las operaciones de RFC, BAPI aparecen por nombre. Para obtener más información sobre cómo invocar BAPI mediante la interfaz del objeto de negocios, vea [operaciones de BAPI en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).  
  
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
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)