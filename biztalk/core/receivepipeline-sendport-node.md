---
title: ReceivePipeline (nodo puertoEnvío) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceivePipeline node [binding file]
ms.assetid: 5305f255-e7a2-4052-bf50-4fb207cfae8d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 210c54b18cc174f31ff795a657f7d23044cebc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268876"
---
# <a name="receivepipeline-sendport-node"></a>ReceivePipeline (nodo puertoEnvío)
El nodo ReceivePipeline del nodo puertoEnvío de un archivo de enlace contiene información específica acerca de una canalización de recepción enlazada a un puerto de envío bidireccional que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-receivepipeline-node"></a>Nodos del nodo ReceivePipeline  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre de la canalización de envío.|No requerido|Valor predeterminado: vacío|  
|FullyQualifiedName|Atributo|xs:string|Especifica el nombre completo de la canalización, que incluye el nombre del ensamblado implementada como parte de la canalización.|No requerido|Valor predeterminado: vacío|  
|Tipo|Atributo|xs:int|Especifica el tipo de canalización.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles se describen en la enumeración <br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx) enumeración.|  
|TrackingOption|Atributo|PipelineTrackingTypes (SimpleType)|Especifica las opciones de seguimiento de la canalización.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles están documentados en la enumeración [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) .|  
|Descripción|Atributo|xs:string|Especifica una descripción para la canalización de envío.|No requerido|Valor predeterminado: vacío|