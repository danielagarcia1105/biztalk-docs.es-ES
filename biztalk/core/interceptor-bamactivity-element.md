---
title: Elemento bamactivity de intercepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dee61b4-83cd-4a22-b8a6-1c1a7ea3648b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43869922e46187c8b2e06155d525e428edd905
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257068"
---
# <a name="interceptor-bamactivity-element"></a>Elemento BamActivity de intercepción
El **BamActivity** elemento define una sola actividad BAM.  
  
## <a name="format"></a>Formato  
 El `BamActivity` elemento incluye un **nombre** de atributo y contiene uno o varios `OnEvent` elementos.  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a>Atributos  
  
|Nombre del atributo|Description|  
|--------------------|-----------------|  
|Nombre|Nombre de la actividad de BAM definido por el usuario.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene una muestra de BamActivity para "MyOrderWorkflow" con un único elemento OnEvent.  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a>Vea también  
 [Elemento EventSource del interceptor](../core/interceptor-eventsource-element.md)   
 [Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md)