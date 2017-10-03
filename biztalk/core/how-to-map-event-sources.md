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
# <a name="how-to-map-event-sources"></a><span data-ttu-id="fc939-102">Cómo asignar orígenes de eventos</span><span class="sxs-lookup"><span data-stu-id="fc939-102">How to Map Event Sources</span></span>
<span data-ttu-id="fc939-103">Se asignan orígenes de eventos para obtener acceso a elementos de datos a los que BAM realiza un seguimiento para generar alertas.</span><span class="sxs-lookup"><span data-stu-id="fc939-103">You map event sources to gain access to data items that BAM tracks to generate alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc939-104">Puede asignar elementos de datos en cuatro tipos de orígenes de eventos diferentes: programaciones de orquestaciones, cargas de mensajes, propiedades de contexto o propiedades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="fc939-104">You can map data items from four different event source types: orchestration schedules, message payloads, context properties, or messaging properties.</span></span> <span data-ttu-id="fc939-105">El procedimiento de este tema describe cómo asignar elementos de datos desde una programación de orquestación.</span><span class="sxs-lookup"><span data-stu-id="fc939-105">The procedure in this topic outlines mapping data items from an orchestration schedule.</span></span>  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a><span data-ttu-id="fc939-106">Para asignar una programación de orquestación como un origen de eventos</span><span class="sxs-lookup"><span data-stu-id="fc939-106">To map an orchestration schedule as an event source</span></span>  
  
1.  <span data-ttu-id="fc939-107">Abra un perfil de seguimiento existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc939-107">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="fc939-108">Para obtener más información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).</span><span class="sxs-lookup"><span data-stu-id="fc939-108">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="fc939-109">Haga clic en el **Seleccionar origen de eventos** (situado sobre el panel derecho, en el Editor de perfiles de seguimiento).</span><span class="sxs-lookup"><span data-stu-id="fc939-109">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="fc939-110">Seleccione el **seleccionar programación de orquestación** elemento de menú en el menú en cascada.</span><span class="sxs-lookup"><span data-stu-id="fc939-110">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="fc939-111">Seleccione el ensamblado primario desde el que se va a dibujar la orquestación, haga clic en el ensamblado que contiene la orquestación en el **nombre de ensamblado** cuadro de lista y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fc939-111">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
     <span data-ttu-id="fc939-112">![Seleccionar ensamblado primario como origen del evento en el TPE](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span><span class="sxs-lookup"><span data-stu-id="fc939-112">![Select Parent Assembly as event Source in the TPE](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span></span>  
  
5.  <span data-ttu-id="fc939-113">Seleccione la orquestación que es el origen de los elementos de datos en el **nombre de la orquestación** cuadro de lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc939-113">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="fc939-114">Seleccione los elementos de datos en el panel derecho y arrástrelos a los nodos correspondientes de la actividad en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="fc939-114">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc939-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc939-115">See Also</span></span>  
 <span data-ttu-id="fc939-116">[Editor de perfiles de seguimiento](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="fc939-116">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="fc939-117">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fc939-117">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)