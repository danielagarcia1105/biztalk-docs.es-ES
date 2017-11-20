---
title: "Cómo configurar la forma construir mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07b73e7fe62463767894808d7e95f12cf963e4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-construct-message-shape"></a><span data-ttu-id="ce1d8-102">Cómo configurar la forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="ce1d8-102">How to Configure the Construct Message Shape</span></span>
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
<span data-ttu-id="ce1d8-103">Forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="ce1d8-103">Construct Message shape</span></span>  
  
 <span data-ttu-id="ce1d8-104">Especifique la variable de mensaje que desee construir y haga nuevas asignaciones al mensaje o sus partes.</span><span class="sxs-lookup"><span data-stu-id="ce1d8-104">You specify the message variable that you want to construct, and make assignments to the message or its parts.</span></span> <span data-ttu-id="ce1d8-105">Todas las asignaciones a un mensaje determinado deben tener lugar dentro de la misma forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="ce1d8-105">All assignments to any given message must take place within the same Construct Message shape.</span></span>  
  
 <span data-ttu-id="ce1d8-106">Si desea modificar una propiedad de un mensaje que ya se haya construido, como un mensaje que se haya recibido, debe construir una nueva instancia de mensaje asignando el primero al segundo y modificando la propiedad de la nueva instancia de mensaje. Tanto la construcción como la modificación se realizan dentro de la misma forma Construir mensaje .</span><span class="sxs-lookup"><span data-stu-id="ce1d8-106">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message instance by assigning the first to the second and then modifying the property on the new message instance; both the construction and modification occur within the same Construct Message shape.</span></span>  
  
### <a name="to-configure-a-construct-message-shape"></a><span data-ttu-id="ce1d8-107">Para configurar una forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="ce1d8-107">To configure a Construct Message shape</span></span>  
  
1.  <span data-ttu-id="ce1d8-108">En la ventana Propiedades, use el **mensajes construidos** propiedad para especificar qué mensajes de esta forma se construirá.</span><span class="sxs-lookup"><span data-stu-id="ce1d8-108">In the Properties window, use the **Messages Constructed** property to specify which messages this shape will construct.</span></span>  
  
2.  <span data-ttu-id="ce1d8-109">Agregar y configurar uno o varios **transformar** o **asignación de mensajes** formas dentro de la **forma construir mensaje**.</span><span class="sxs-lookup"><span data-stu-id="ce1d8-109">Add and configure one or more **Transform** or **Message Assignment** shapes inside the **Construct Message shape**.</span></span>