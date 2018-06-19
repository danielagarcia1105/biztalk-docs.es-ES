---
title: Bucle condicional | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, conditional
- Equal functoids
- maps, conditional looping
ms.assetid: eb16efb8-b12c-47d6-afc9-579fc85ea59c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5452f6b8768442b95ac6bddde0e84ba07f68c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231980"
---
# <a name="conditional-looping"></a>Bucle condicional
Puede agregar condiciones a una **bucle** functoid vinculándose a la salida de un **bucle** functoid y un **lógicos** functoid en el mismo registro de destino. Los registros de destino solo se crean cuando se cumple la condición lógica.  
  
## <a name="conditional-looping-map"></a>Asignación de bucle condicional  
 ![Mapa que ilustra el functoid de bucle condicional. ] (../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")  
  
 En la ilustración anterior, la primera **igual** functoid compara el **nombre** campo **FoodSurvey** con "Wendy Wheeler". El segundo **igual** functoid compara el **nombre** campo **FlowerSurvey** con "Kelly Focht". Por lo tanto, la asignación crea el destino **dirección** registros solo para los dos nombres. Con los datos de ejemplo de la **bucle** ejemplo de functoid, podría aparecer el mensaje de instancia de salida como sigue.  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://ConditionalLoop.MasterAddresses">  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290">  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406">  
</ns0:MasterAddresses>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids a una asignación de bucle](../core/how-to-add-looping-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de índice](../core/index-functoid.md)   
 [Functoid de iteración](../core/iteration-functoid.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Functoid de número de registros](../core/record-count-functoid.md)