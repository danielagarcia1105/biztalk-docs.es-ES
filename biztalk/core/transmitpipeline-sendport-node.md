---
title: "TransmitPipeline (nodo puertoEnvío) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransmitPipeline node [binding file]
ms.assetid: cee55451-6c3f-4e37-aef9-870d4b5d23aa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4addad5ea98781865b44470f2d07b577afce6c0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transmitpipeline-sendport-node"></a>TransmitPipeline (nodo puertoEnvío)
El nodo TransmitPipeline del nodo puertoEnvío de un archivo de enlace proporciona información específica acerca del enlazado de una canalización de envío a un puerto de envío que se exporta con un archivo de enlace.  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>Nodos del nodo TransmitPipeline  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre de la canalización de envío.|No requerido|Valor predeterminado: vacío|  
|FullyQualifiedName|Atributo|xs:string|Especifica el nombre completo de la canalización, incluido el nombre del ensamblado al que pertenece la canalización implementada.|No requerido|Valor predeterminado: vacío|  
|Tipo|Atributo|xs:int|Especifica el tipo de canalización.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles están documentados en la enumeración [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx) .|  
|TrackingOption|Atributo|PipelineTrackingTypes (SimpleType)|Especifica las opciones de seguimiento de la canalización.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles están documentados en la enumeración [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) .|  
|Descripción|Atributo|xs:string|Especifica una descripción para la canalización de envío.|No requerido|Valor predeterminado: vacío|