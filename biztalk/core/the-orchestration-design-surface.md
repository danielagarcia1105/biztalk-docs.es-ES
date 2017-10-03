---
title: "La superficie de diseño de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5fb190b-60d7-45e4-9883-7b3d2ed6b0c0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f943c1543cf50e4ecb1f25627cbccd7b4d72eab5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-orchestration-design-surface"></a><span data-ttu-id="af4e2-102">La superficie de diseño de la orquestación</span><span class="sxs-lookup"><span data-stu-id="af4e2-102">The Orchestration Design Surface</span></span>
<span data-ttu-id="af4e2-103">La superficie de diseño de orquestación es un diseñador visual que se puede usar para crear una orquestación de BizTalk, además de ser el componente central del diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="af4e2-103">The Orchestration Design Surface is a visual designer that you can use to create a BizTalk Orchestration, and is the central component of Orchestration Designer.</span></span> <span data-ttu-id="af4e2-104">Es un lienzo en el que puede arrastrar formas desde el cuadro de herramientas y configurar las formas.</span><span class="sxs-lookup"><span data-stu-id="af4e2-104">It is a canvas that you can drag shapes onto from the Toolbox, and then configure the shapes.</span></span> <span data-ttu-id="af4e2-105">Como ventana del editor de Visual Studio, ocupa el área de la ventana principal usada por otras ventanas del editor de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af4e2-105">As a Visual Studio editor window, it occupies the main window area used by other Visual Studio editor windows.</span></span>  
  
 <span data-ttu-id="af4e2-106">![Diseñadores de orquestaciones](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span><span class="sxs-lookup"><span data-stu-id="af4e2-106">![Orchestration Designers](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span></span>  
<span data-ttu-id="af4e2-107">Superficie de diseño de orquestación</span><span class="sxs-lookup"><span data-stu-id="af4e2-107">Orchestration Design Surface</span></span>  
  
 <span data-ttu-id="af4e2-108">El nombre de la orquestación se muestra en la pestaña superior de la ventana Superficie de diseño de orquestación y en la barra de título de la ventana Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af4e2-108">The name of the orchestration is displayed on the top tab of the Orchestration Design Surface window and in the Visual Studio window title bar.</span></span>  
  
 <span data-ttu-id="af4e2-109">La superficie de diseño se divide en tres áreas: el área de proceso y dos superficies de puerto.</span><span class="sxs-lookup"><span data-stu-id="af4e2-109">The design surface itself is divided into three areas: the Process Area and two Port Surfaces.</span></span> <span data-ttu-id="af4e2-110">El área central de proceso contiene formas que describen el flujo de proceso actual de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="af4e2-110">The central Process Area contains shapes that describe the actual process flow of the orchestration.</span></span> <span data-ttu-id="af4e2-111">Se encuentra rodeada a ambos lados por superficies de puerto, que contienen formas puerto y el vínculo de función que interactúan con la **enviar** y **recepción** formas en el área de proceso.</span><span class="sxs-lookup"><span data-stu-id="af4e2-111">It is flanked on both sides by Port Surfaces, which contain only Port and Role Link shapes that interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="af4e2-112">**Área de proceso**</span><span class="sxs-lookup"><span data-stu-id="af4e2-112">**Process Area**</span></span>  
  
 <span data-ttu-id="af4e2-113">El Área de proceso es la parte principal de la superficie de diseño de orquestación de diseñador de orquestaciones y siempre se centra horizontalmente en la superficie de diseño de orquestación.</span><span class="sxs-lookup"><span data-stu-id="af4e2-113">The Process Area is the main part of the Orchestration Design Surface of Orchestration Designer, and is always horizontally centered in the Orchestration Design Surface.</span></span>  
  
 <span data-ttu-id="af4e2-114">En cualquier lado del área de proceso ve las superficies de puerto.</span><span class="sxs-lookup"><span data-stu-id="af4e2-114">On either side of the Process Area you see Port Surfaces.</span></span> <span data-ttu-id="af4e2-115">El **comenzar** forma se coloca en la parte superior de la superficie de diseño y la orquestación se expande hacia abajo cuando se agregan formas.</span><span class="sxs-lookup"><span data-stu-id="af4e2-115">The **Begin** shape is placed at the top of the design surface and the orchestration grows downward as you add shapes.</span></span>  
  
 <span data-ttu-id="af4e2-116">**Superficies de puerto**</span><span class="sxs-lookup"><span data-stu-id="af4e2-116">**Port Surfaces**</span></span>  
  
 <span data-ttu-id="af4e2-117">Se muestran dos superficies de puerto en la superficie de diseño de orquestación, una a cada lado del área de proceso.</span><span class="sxs-lookup"><span data-stu-id="af4e2-117">Two Port Surfaces are displayed in the Orchestration Design Surface, one on either side of the Process Area.</span></span> <span data-ttu-id="af4e2-118">Superficies de puerto pueden contener dos tipos de formas: **puertos** y **vínculos de función**.</span><span class="sxs-lookup"><span data-stu-id="af4e2-118">Port Surfaces can contain two kinds of shapes: **Ports** and **Role Links**.</span></span> <span data-ttu-id="af4e2-119">Estas formas de interactúan con el **enviar** y **recepción** formas en el área de proceso.</span><span class="sxs-lookup"><span data-stu-id="af4e2-119">These shapes interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="af4e2-120">No importa qué superficie de puerto se use para una forma; es decir, la forma funciona de forma idéntica tanto en la superficie de puerto derecha como en la superficie de puerto izquierda.</span><span class="sxs-lookup"><span data-stu-id="af4e2-120">It makes no difference which Port Surface you use for a shape; that is, the shape functions identically on either the right or the left Port Surface.</span></span> <span data-ttu-id="af4e2-121">Tener dos superficies de puerto en las que colocar puertos nuevos permite crear orquestaciones con menos conectores de entrelazado que, por tanto, son más fáciles de leer.</span><span class="sxs-lookup"><span data-stu-id="af4e2-121">Having two Port Surfaces on which to place new ports lets you create orchestrations with fewer crisscrossing connectors that therefore are easier to read.</span></span>  
  
 <span data-ttu-id="af4e2-122">Las superficies de puerto se pueden contraer o expandir al hacer doble clic en ellas o al hacer clic en el icono de doble flecha.</span><span class="sxs-lookup"><span data-stu-id="af4e2-122">Both Port Surfaces can be collapsed or expanded by double-clicking on them or by clicking on the double arrow icon.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af4e2-123">La mayoría de las tareas del diseñador de orquestaciones requieren que seleccione varios elementos, por ejemplo, esquemas u orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="af4e2-123">Many Orchestration Designer tasks require you to select various items such as schemas or orchestrations.</span></span> <span data-ttu-id="af4e2-124">Si estos elementos no se encuentran en el proyecto actual, debe recordar agregar una referencia del proyecto al ensamblado que contenga el elemento que desee seleccionar.</span><span class="sxs-lookup"><span data-stu-id="af4e2-124">If these items are not in the current project, you must remember to add a reference in your project to the assembly that contains the item that you want to select.</span></span> <span data-ttu-id="af4e2-125">Para ello, haga clic en el proyecto y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="af4e2-125">To do this, right-click the project and select **Add Reference**.</span></span>  
  
 <span data-ttu-id="af4e2-126">**Compatibilidad con zoom**</span><span class="sxs-lookup"><span data-stu-id="af4e2-126">**Zoom Support**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="af4e2-127">proporciona la capacidad de acercar o alejar la superficie del Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="af4e2-127"> provides the ability to zoom in or zoom out of the Orchestration designer surface.</span></span> <span data-ttu-id="af4e2-128">Puede usar la compatibilidad con zoom completando uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="af4e2-128">You can use zoom support by completing one of the following steps:</span></span>  
  
-   <span data-ttu-id="af4e2-129">Haga clic en la superficie del Diseñador de orquestaciones y haga clic en el **Zoom** opción de menú.</span><span class="sxs-lookup"><span data-stu-id="af4e2-129">Right-click the Orchestration designer surface and click the **Zoom** menu option.</span></span> <span data-ttu-id="af4e2-130">Se puede seleccionar el porcentaje de ampliación que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="af4e2-130">You can then select the percentage of magnification that you would like to apply.</span></span>  
  
-   <span data-ttu-id="af4e2-131">Use la combinación CTRL + RUEDA DEL MOUSE para acercar o alejar. Mantenga presionado el botón CTRL y gire de forma simultánea la rueda del mouse hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="af4e2-131">Use the CTRL + MWHEEL combination to zoom in or zoom out. Hold down the CTRL button and simultaneously rotate the mouse wheel up or down.</span></span> <span data-ttu-id="af4e2-132">Use la combinación CTRL+RUEDA DEL MOUSE HACIA ARRIBA para alejar y la combinación CTRL+RUEDA DEL MOUSE HACIA ABAJO para acercar.</span><span class="sxs-lookup"><span data-stu-id="af4e2-132">Use the CTRL+MWHEELUP combination to zoom out and the CTRL+MWHEELDOWN combination to zoom in.</span></span>