---
title: Esquemas de mensajes para operaciones de servicio de negocio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message schemas, for business service methods
ms.assetid: ba23248b-5d73-4de0-9f7c-987cd88a4b63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0062b8e6b6ce3961c937e9e5bece81cb24281049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-business-service-operations"></a>Esquemas de mensaje para las operaciones de servicio de negocios
Un servicio de negocios de Siebel es una colección de métodos de negocio que se pueden invocar directamente en un sistema Siebel. La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone los métodos de negocio de un servicio de negocios de Siebel como operaciones.  
  
## <a name="message-schemas-for-siebel-business-service-method-operations"></a>Esquemas de mensaje para operaciones de método de servicio de negocio de Siebel  
 La siguiente tabla muestra los esquemas de mensaje para operaciones de método del servicio de negocio de Siebel obtenidas por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
|Operación|Estructura XML|Description|  
|---------------|-------------------|-----------------|  
|[Business_Service_METHOD_NAME]|Mensaje de solicitud de método de servicio empresarial:<br /><br /> `<[METHOD_NAME] xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]RequestRecord>     <[I_PRM1_NAME]>value1</[I_PRM1_NAME]>     <[I_PRM2_NAME]>value2</[I_PRM2_NAME]>     …   </[METHOD_NAME]RequestRecord>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord> </[METHOD_NAME]>`<br /><br /> [Versión] = la cadena de versión de mensaje; Por ejemplo, "http://Microsoft.LobServices.Siebel/2007/03".<br /><br /> [Servicio de negocio] = nombre del servicio de negocios; Por ejemplo, ExtractDataService.<br /><br /> [NombreMétodo] = el nombre del método de servicio de negocios; Por ejemplo, ExecuteNext.<br /><br /> [I_PRM_NAME] = parámetros nombres de IN.<br /><br /> [IO_PRM_NAME] = nombres de en los parámetros.<br /><br /> Mensaje de respuesta del método de servicio empresarial:<br /><br /> `<[METHOD_NAME]Response xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]Result>     <[O_PRM1_NAME]>value1</[O_PRM1_NAME]>     <[O_PRM2_NAME]>value2</[O_PRM2_NAME]>     …   </[METHOD_NAME]Result>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord > </[METHOD_NAME]Response>`<br /><br /> [Versión] = la cadena de versión de mensaje; Por ejemplo, "http://Microsoft.LobServices.Siebel/2007/03".<br /><br /> [Servicio de negocio] = nombre del servicio de negocios; Por ejemplo, ExtractDataService.<br /><br /> [NombreMétodo] = nombre del método de servicio de negocios; Por ejemplo, ExecuteNext.<br /><br /> [O_PRM_NAME] = nombres de los parámetros.<br /><br /> [IO_PRM_NAME] = parámetros nombres de INOUT.<br /><br /> **Importante:** los parámetros de salida y entrada salida siempre se marcan como opcionales en los metadatos, incluso si requiere el sistema Siebel. Por lo tanto, si un parámetro se marca como opcional en los metadatos, pero es necesario por el sistema Siebel, el adaptador lanza el `TargetSystemException` como recibido de Siebel y no el `XmlReaderParsingException`.|El método de servicio de negocios de Siebel aparece como un nombre de operación.<br /><br /> -EN, en parámetros de salida y se admiten.<br /><br /> -Jerárquicos tipos se exponen como cadenas. El adaptador no valida los valores pasados para estas cadenas. Si estos valores no se ajusta a los esquemas esperados por el sistema Siebel, se generará una excepción en tiempo de ejecución.|  
  
## <a name="message-actions-for-siebel-business-service-method-operations"></a>Acciones de mensaje para operaciones de método de servicio de negocio de Siebel  
 En la tabla siguiente se muestra cómo se forma la acción SOAP para un método de servicio empresarial de Siebel. Solo la acción del mensaje de solicitud no se muestra, la acción para el mensaje de respuesta se forma anexando "/ respuesta" a la acción de mensaje de solicitud; Por ejemplo, "[versión] / BusinessServices/ExtractDataService/ExecuteNext/respuesta".  
  
|Operación|Acción|Description|  
|---------------|------------|-----------------|  
|[Business_Service_METHOD_NAME]|/BusinessServices/ [versión] [servicio de negocio] / [Business_Service_METHOD_NAME]|[Versión] / BusinessServices/ExtractDataService/ExecuteNext|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, "http://Microsoft.LobServices.Siebel/2007/03".  
  
 [Servicio de negocio] = nombre del servicio de negocios; Por ejemplo, ExtractDataService.  
  
 [Business_Service_METHOD_NAME] = el nombre del método de servicio de negocios; Por ejemplo, ExecuteNext.  
  
 Debe especificar explícitamente la acción de mensaje cuando se usan los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en una solución de BizTalk Server o mediante el modelo de canal WCF. Para obtener más información, consulte [desarrolla aplicaciones Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md).  
  
## <a name="siebel-business-service-wcf-client-methods"></a>Métodos de cliente WCF de servicio de Siebel empresarial  
 La tabla siguiente muestra la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] la firma del método de modelo de servicio generadas por el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para Siebel métodos de servicios de negocio.  
  
|Operación|Método de modelo de servicio WCF|  
|---------------|------------------------------|  
|[Business_Service_METHOD_NAME]|`[Business_Service_METHOD_NAME]ResponseRecord client.[Business_Service_METHOD_NAME]([Business_Service_METHOD_NAME]RequestRecord);`<br /><br /> [Business_Service_METHOD_NAME] = nombre del método de servicio de negocios; Por ejemplo, ExecuteNext.|  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)