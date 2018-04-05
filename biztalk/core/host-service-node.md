---
title: Host (nodo servicio) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Host node [binding file]
ms.assetid: 597522db-0336-43b1-b464-d17cffbf25be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c70c23105a8d2f2ebe389b22ddf910b4166994
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="host-service-node"></a>Host (nodo Servicio)
El nodo Host del nodo Servicio de un archivo de enlace describe el host asociado al servicio que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-host-node"></a>Nodos del nodo Host  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del host.|No requerido|Valor predeterminado: vacío|  
|NTGroupName|Attribute|xs:string|Especifica el nombre del grupo de Windows NT asociado al host.|No requerido|Valor predeterminado: vacío|  
|Tipo|Atributo|xs:int|Especifica el tipo de host como En curso o Aislado.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles se describen en la [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx) enumeración.|  
|De confianza|Attribute|xs:boolean|Especifica si se puede confiar en un host de BizTalk para recopilar información de autenticación.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** si el host es de confianza, en caso contrario, se establece en **false**.|