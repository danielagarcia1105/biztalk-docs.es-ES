---
title: Servicio (nodo de servicios) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Service node [binding file]
ms.assetid: 19e977b4-55bd-453f-9053-5590b9553b07
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 834555f43620d428d18a04938e18612793b2ab51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270252"
---
# <a name="service-services-node"></a>Servicio (nodo de servicios)
El nodo Servicio de un archivo de enlace contiene información específica acerca de un servicio que se exporta con el archivo de enlace. El nodo de servicio también contiene nodos que describen los puertos y los roles asociados al servicio, así como un nodo que describe el host asociado con el servicio.  
  
## <a name="nodes-in-the-service-node"></a>Nodos del nodo Servicio  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del servicio.|Necesario|Valor predeterminado: vacío|  
|State|Attribute|ServiceRefState (SimpleType)|Especifica el estado del servicio.|Necesario|Valor predeterminado: predeterminado<br /><br /> Los valores posibles incluyen:<br /><br /> -Valor predeterminado<br />-Dado de baja<br />-Dado de alta<br />-Se inició|  
|TrackingOption|Attribute|OrchestrationTrackingTypes (SimpleType)|Especifica las opciones de seguimiento de mensajes del servicio.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la [Microsoft.BizTalk.ExplorerOM.OrchestrationTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.orchestrationtrackingtypes.aspx) enumeración.|  
|Description|Atributo|xs:string|Especifica la descripción del servicio.|No requerido|Valor predeterminado: vacío|  
|[Puertos](../core/ports-service-node.md)|Grabar|ArrayOfServicePortRef (ComplexType)|Nodo contenedor para los puertos enlazados al servicio.|No requerido|Valor predeterminado: ninguno|  
|[Roles](../core/roles-service-node.md)|Grabar|ArrayOfRoleRef (ComplexType)|Nodo contenedor para los roles enlazados al servicio.|No requerido|Valor predeterminado: ninguno|  
|[Host](../core/host-service-node.md)|Grabar|HostRef (ComplexType)|Nodo contenedor para el host enlazado al servicio.|Necesario|Valor predeterminado: ninguno|