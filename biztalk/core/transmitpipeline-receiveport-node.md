---
title: "TransmitPipeline (nodo puertoRecepción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransmitPipeline node [binding file]
ms.assetid: 0f3b728f-1e4a-40e5-9ca9-f7dcdf995cbe
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf1b105f2e7cfc5601469ac55cac6af22aa21a16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transmitpipeline-receiveport-node"></a>TransmitPipeline (nodo ReceivePort)
El nodo TransmitPipeline del nodo puertoRecepción de un archivo de enlace proporciona información específica acerca del enlazado de una canalización de envío a un puerto de recepción bidireccional que se exporta con el archivo de enlace.  
  
> [!NOTE]
>  Puesto que canalizaciones de envío para recepciones bidireccionales se enlazan en el nivel de la ubicación de recepción en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], este nodo se proporciona para ofrecer compatibilidad con BizTalk Server 2004. Enviar canalizaciones para recepciones bidireccionales se enlazan en el nivel de puerto de recepción de BizTalk Server 2004. Propiedades que se establecen para este nodo de un archivo de enlace que se haya exportado desde BizTalk Server 2004 se aplicarán al nodo SendPipeline de cada ubicación de recepción bidireccional que se hace referenciada mediante el puerto de recepción al importar el archivo de enlace en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>Nodos del nodo TransmitPipeline  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre de la canalización de envío.|No requerido|Valor predeterminado: vacío|  
|FullyQualifiedName|Atributo|xs:string|Especifica el nombre completo de la canalización, que incluye el nombre del ensamblado implementada como parte de la canalización.|No requerido|Valor predeterminado: vacío|  
|Tipo|Atributo|xs:int|Especifica el tipo de canalización.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles se describen en la enumeración <br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx) enumeración.|  
|TrackingOption|Atributo|PipelineTrackingTypes (SimpleType)|Especifica las opciones de seguimiento de la canalización.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles están documentados en la enumeración [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) .|  
|Descripción|Atributo|xs:string|Especifica una descripción para la canalización de envío.|No requerido|Valor predeterminado: vacío|  
  
## <a name="see-also"></a>Vea también  
 [SendPipeline](../core/sendpipeline-receivelocation-node.md)   
 [ReceiveLocation](../core/receivelocation-receivelocations-node.md)