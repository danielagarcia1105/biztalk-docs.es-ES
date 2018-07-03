---
title: Los esquemas de mensajes para operaciones de BAPI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations, message schemas for
- BAPI operations, message structure for
- BAPI operations, message actions for
ms.assetid: ef4d88e8-f31a-4b68-a303-6885b6f8c083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796e7beb428e6f9a4f0df63eff9cf45e9d5410bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995221"
---
# <a name="message-schemas-for-bapi-operations"></a>Esquemas de mensaje para operaciones de BAPI
Las secciones siguientes describen los esquemas de mensaje y las acciones de mensaje utilizadas para invocar BAPI en el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como métodos de objetos de negocios. También puede invocar BAPI como operaciones de RFC en el adaptador. Para obtener más información acerca de los mensajes utilizados para invocar RFC, consulte [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md). Independientemente de cómo invocar una BAPI en el adaptador, el adaptador siempre invoca la BAPI como una solicitud de cambio en el sistema SAP. Para obtener información general de cómo el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite BAPI, vea [operaciones en BAPI de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).  

## <a name="message-structure-for-business-object-operations"></a>Estructura de mensaje para operaciones de objeto de negocios  
 La siguiente tabla muestra los esquemas de mensaje utilizados para invocar una BAPI como un método del objeto comercial.  

|Operación|Operaciones de recepción de estructuras de mensajes para IDOC|Descripción|  
|---------------|-------------------|-----------------|  
|[BUSOBJ_METHOD]|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|Invocar un método del objeto comercial en un sistema SAP.<br /><br /> Se admiten la importación, cambiar y parámetros de la tabla.|  
|[BUSOBJ_METHOD] Respuesta|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|Respuesta del método de objeto de negocios.<br /><br /> Exportar, cambiar, y se admiten parámetros de la tabla.<br /><br /> **Tenga en cuenta** de forma predeterminada, los parámetros de la tabla no se exponen en el mensaje de respuesta. Si se requieren parámetros de la tabla en el mensaje de respuesta, debe pasar los parámetros de la tabla vacía en el mensaje de solicitud.|  

 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [BUSOBJ_METHOD] = el nombre de un método del objeto comercial; Por ejemplo, CREATEFROMDAT2.  

 [IN_PARAM_NAME] = el nombre de un parámetro de importación BAPI.  

 [OUT_PARAM_NAME] = el nombre de un parámetro de exportación BAPI.  

 [INOUT_PARAM_NAME] = el nombre de un BAPI cambiando el parámetro.  

 [TABLE_PARAM_NAME] = nombre del parámetro de tabla BAPI.  

 [STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura BAPI.  

## <a name="message-actions-for-business-object-operations"></a>Acciones de mensaje para operaciones de objeto de negocios  
 La siguiente tabla muestra las acciones de mensaje que se usan para invocar BAPI como métodos de objetos comerciales.  


|        Operación         |                            Acción de mensaje                             |                                                   Ejemplo                                                    |
|--------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|     [BUSOBJ_METHOD]      |     /Bapi/ [versión] [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME]      |     http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2      |
| [BUSOBJ_METHOD] Respuesta | /Bapi/ [versión] [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME] / respuesta | http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response |

 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  

 [BUSOBJ_NAME] = el nombre del objeto comercial; Por ejemplo, BUS2032.  

 [BUSOBJ_METHOD] = el método del objeto comercial; Por ejemplo, CREATEFROMDAT2.  

 [BAPI_RFC_NAME] = nombre de la RFC para la BAPI; Por ejemplo, BAPI_SALESORDER_CREATEFROMDAT2.  

## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)