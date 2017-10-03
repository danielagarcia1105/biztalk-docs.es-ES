---
title: "Cómo asignar orígenes de eventos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, alerts
- orchestrations, schedules
- events, mapping sources
- orchestrations, tracking profiles
- events, orchestration schedules
- tracking profiles, orchestrations
- tracking profiles, alerts
- alerts, tracking profiles
- alerts, BAM
- tracking profiles, mapping event sources
- events, tracking profiles
ms.assetid: 507f1624-2cd8-4960-8c63-7797ab22519e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 588a394fb3404872554fc786efa3fe24fdd9b47a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-event-sources"></a>Cómo asignar orígenes de eventos
Se asignan orígenes de eventos para obtener acceso a elementos de datos a los que BAM realiza un seguimiento para generar alertas.  
  
> [!NOTE]
>  Puede asignar elementos de datos en cuatro tipos de orígenes de eventos diferentes: programaciones de orquestaciones, cargas de mensajes, propiedades de contexto o propiedades de mensajería. El procedimiento de este tema describe cómo asignar elementos de datos desde una programación de orquestación.  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a>Para asignar una programación de orquestación como un origen de eventos  
  
1.  Abra un perfil de seguimiento existente o cree uno nuevo. Para obtener más información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).  
  
2.  Haga clic en el **Seleccionar origen de eventos** (situado sobre el panel derecho, en el Editor de perfiles de seguimiento).  
  
3.  Seleccione el **seleccionar programación de orquestación** elemento de menú en el menú en cascada.  
  
4.  Seleccione el ensamblado primario desde el que se va a dibujar la orquestación, haga clic en el ensamblado que contiene la orquestación en el **nombre de ensamblado** cuadro de lista y, a continuación, haga clic en **siguiente**.  
  
     ![Seleccionar ensamblado primario como origen del evento en el TPE](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")  
  
5.  Seleccione la orquestación que es el origen de los elementos de datos en el **nombre de la orquestación** cuadro de lista y, a continuación, haga clic en **Aceptar**.  
  
6.  Seleccione los elementos de datos en el panel derecho y arrástrelos a los nodos correspondientes de la actividad en el panel izquierdo.  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)   
 [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)