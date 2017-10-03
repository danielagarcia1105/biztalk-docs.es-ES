---
title: "Cómo asignar una aplicación a un adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1ea2773-c53c-40a0-a312-015191746451
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5052d06576988ed71da8458a9d55115fb0b1c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-an-application-to-an-adapter"></a>Cómo asignar una aplicación a un adaptador
Para procesar información entre una aplicación local y un servidor remoto, el adaptador debe tener una o más aplicaciones asignadas.  
  
### <a name="to-assign-an-application-to-an-adapter"></a>Para asignar una aplicación a un adaptador  
  
1.  Agregar la aplicación al adaptador mediante `ISSOPSAdmin.AssignApplicationToAdapter`.  
  
2.  Puede recuperar la lista actual de las aplicaciones asignadas a un adaptador mediante el uso de `ISSOAdmin.GetApplicationsForAdapter`.  
  
3.  Una vez haya terminado, puede quitar una aplicación de un adaptador mediante `ISSOPSAdmin.RemoveApplicationFromAdapter`.