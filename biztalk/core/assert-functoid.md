---
title: "Functoid de aserción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03237c27e0e35642be197b549c8b0102d9350702
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="assert-functoid"></a>Functoid de aserción

## <a name="overview"></a>Información general
El **Assert** functoid muestra un valor de cadena o produce una excepción basada en un valor booleano. Si este functoid se combina con uno o varios de los **lógicos** functoids, puede probar eficazmente suposiciones acerca de las condiciones de la asignación. Por ejemplo, si tiene un mapa que espera cantidades de pedido de compra nunca a superar un umbral determinado, puede probar el valor de orden de compra mediante el **Greater Than** functoid y, a continuación, conéctese a la **Assert**functoid. Si el functoid lógico devuelve **True**, **Assert** functoid iniciará una excepción utilizando una cadena que proporcione.  
  
 ![Functoid de aserción](../core/media/assertfunctoid.gif "AssertFunctoid")  
  
## <a name="see-also"></a>Vea también  
 **Referencia de Functoid de aserción** y **referencia a Functoids lógicos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]