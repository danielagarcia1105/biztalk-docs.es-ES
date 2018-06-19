---
title: Filtro | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8dad59d-4a47-4794-bbf9-cba02fe7f0bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efa69998b1782f42d7730744fd88534d26a87835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245804"
---
# <a name="filter"></a>Filtro
El elemento `Filter` contiene una `Expression` que se evalúa como `true` o `false` y determina cuándo se debe procesar u omitir un evento.  
  
## <a name="format"></a>Formato  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente define un filtro que se evalúa como `true` cuando la clave del usuario del flujo de trabajo asociado al evento es igual a "DocumentUrl":  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>Vea también  
 [Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md)