---
title: "Cómo asignar varios ensamblados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a55b6e88889ccfa36adcac11fe548ab1b25bc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-multiple-assemblies"></a>Cómo asignar varios ensamblados
Las aplicaciones de BizTalk se pueden componer de varios ensamblados en los que residen los elementos de datos a los que la actividad de BAM hace referencia. El procedimiento siguiente muestra cómo asignar varios ensamblados a un perfil de seguimiento.  
  
### <a name="to-map-multiple-assemblies"></a>Para asignar varios ensamblados  
  
1.  Abra un perfil de seguimiento existente o cree uno nuevo. Para obtener más información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).  
  
2.  Haga clic en el **Seleccionar origen de eventos** (situado sobre el panel derecho, en el Editor de perfiles de seguimiento).  
  
3.  Seleccione el **seleccionar programación de orquestación** elemento de menú en el menú en cascada.  
  
4.  Seleccione el ensamblado primario desde el que se va a dibujar la orquestación, haga clic en el ensamblado que contiene la orquestación en el **nombre de ensamblado** cuadro de lista y, a continuación, haga clic en **siguiente**.  
  
5.  Seleccione la orquestación que es el origen de los elementos de datos en el **nombre de la orquestación** cuadro de lista y, a continuación, haga clic en **Aceptar**.  
  
6.  Seleccione los elementos de datos en el panel derecho y arrástrelos a los nodos correspondientes de la actividad en el panel izquierdo.  
  
7.  Repita los pasos de 2 a 6 para asignar ensamblados adicionales.  
  
### <a name="to-map-the-second-assembly"></a>Para asignar el segundo ensamblado  
  
1.  Haga clic en el **Seleccionar origen de eventos**.  
  
2.  Seleccione el **seleccionar programación de orquestación** elemento de menú en el menú en cascada.  
  
3.  Seleccione el ensamblado primario siguiente desde el que se va a dibujar la orquestación, haga clic en el ensamblado que contiene la orquestación en el **nombre de ensamblado** cuadro de lista y, a continuación, haga clic en el **siguiente** botón.  
  
4.  Seleccione la orquestación que es el origen de los elementos de datos en el **nombre de la orquestación** cuadro de lista y, a continuación, haga clic en **Aceptar**.  
  
5.  Seleccione los elementos de datos en el panel derecho y arrástrelos a los nodos correspondientes de la actividad en el panel izquierdo.  
  
## <a name="see-also"></a>Vea también  
 [Cómo asignar orígenes de eventos](../core/how-to-map-event-sources.md)   
 [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)