---
title: "Asignaciones genéricas y específicas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6ad84e23c3981730ee4cf7655a42d87c46158e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="specific-and-generic-maps"></a>Asignaciones genéricas y específicas
Cuando se crea una asignación que transforma los datos, puede crear un *específico* o un *genérico* mapa.  
  
 La asignación específica se utiliza para ajustarse a las necesidades de un socio comercial en particular. Utilice una asignación específica cuando tenga necesidades empresariales muy específicas o acuerdos empresariales con su socio comercial. La ventaja de una asignación específica es que se personaliza para adaptarse a las necesidades de las funciones empresariales que tenga con socios comerciales específicos. La desventaja de una asignación específica es que normalmente no puede utilizarse con varios socios comerciales. Si multiplica el número de socios comerciales por el número de tipos de mensajes diferentes que intercambia con dichos socios comerciales, deberá dedicar suficiente tiempo y recursos para administrar todas las asignaciones asociadas.  
  
 Las asignaciones genéricas, por otro lado, están diseñadas para utilizarse con varios socios comerciales. Por tanto, en lugar de desarrollar y mantener varios esquemas para un documento empresarial en concreto, crea un esquema para cada tipo de documento empresarial y los utiliza con todos sus socios comerciales. Aunque el utilizar una asignación con varios socios comerciales ahorra tiempo y recursos, estas asignaciones no están personalizadas y puede que no se ajusten a las necesidades en todos los casos.  
  
 Es posible que cree asignaciones específicas y genéricas, en función de la naturaleza de su empresa.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)