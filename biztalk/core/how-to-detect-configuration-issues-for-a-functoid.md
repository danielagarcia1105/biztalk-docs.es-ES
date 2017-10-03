---
title: "Cómo detectar problemas de configuración de un Functoid | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 322a97aba4ec5e02cf754106df30b0c9f0088e1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="5d419-102">Detección de problemas de configuración de un functoid</span><span class="sxs-lookup"><span data-stu-id="5d419-102">How to Detect Configuration Issues for a Functoid</span></span>
<span data-ttu-id="5d419-103">Mientras se trabaja con mapas, pueden surgir problemas con la configuración de un functoid o vínculo.</span><span class="sxs-lookup"><span data-stu-id="5d419-103">While working with maps, you might encounter issues with configuration of a functoid and/or link.</span></span> <span data-ttu-id="5d419-104">El Asignador de BizTalk usa un mecanismo de visualización que ayuda a identificar rápidamente problemas asociados con una configuración de functoid.</span><span class="sxs-lookup"><span data-stu-id="5d419-104">The BizTalk Mapper uses a visualization mechanism to help quickly identify problems associated with a functoid configuration.</span></span> <span data-ttu-id="5d419-105">Esta indicación visual se representa como una anotación de advertencia en el icono del functoid (para p. ej. ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) en la vista de relaciones.</span><span class="sxs-lookup"><span data-stu-id="5d419-105">This visual indication renders as a warning annotation on the functoid icon (for e.g. ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) in the relationship view.</span></span> <span data-ttu-id="5d419-106">En este tema se proporciona información acerca de cómo detectar los problemas de configuración para un functoid.</span><span class="sxs-lookup"><span data-stu-id="5d419-106">This topic provides information about how to detect the configuration issues for a functoid.</span></span>  
  
 <span data-ttu-id="5d419-107">El icono de estado de advertencia aparece cuando el Asignador detecta que un functoid no está correctamente configurado.</span><span class="sxs-lookup"><span data-stu-id="5d419-107">The warning status icon appears when the Mapper detects that a functoid is not properly configured.</span></span> <span data-ttu-id="5d419-108">Mover el mouse sobre functoid también muestra breve información sobre el problema identificado por el Asignador.</span><span class="sxs-lookup"><span data-stu-id="5d419-108">Moving the mouse over the functoid also displays brief information of the issue identified by the Mapper.</span></span> <span data-ttu-id="5d419-109">Por ejemplo, si un functoid no cuenta con un número mínimo de entradas válidas, la información sobre herramientas del functoid menciona el número de parámetros de entrada requeridos.</span><span class="sxs-lookup"><span data-stu-id="5d419-109">For example, if a functoid does not have minimum number of valid inputs, the tooltip for the functoid mentions the number of input parameters required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d419-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5d419-110">Prerequisites</span></span>  
 <span data-ttu-id="5d419-111">Esta operación requiere que se está ejecutando el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5d419-111">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="5d419-112">Procedimiento para detectar problemas de configuración para un functoid</span><span class="sxs-lookup"><span data-stu-id="5d419-112">To detect configuration issues for a functoid</span></span>  
  
1.  <span data-ttu-id="5d419-113">Arrastre el functoid necesario desde el cuadro de herramientas hasta la página de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="5d419-113">Drag the required functoid from the toolbox onto the grid page.</span></span> <span data-ttu-id="5d419-114">Verá el functoid con un icono de advertencia.</span><span class="sxs-lookup"><span data-stu-id="5d419-114">You see the functoid with a warning icon.</span></span>  
  
2.  <span data-ttu-id="5d419-115">Puede hacer una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5d419-115">You can do one of the following:</span></span>  
  
    -   <span data-ttu-id="5d419-116">Mover el puntero del mouse en el functoid.</span><span class="sxs-lookup"><span data-stu-id="5d419-116">Move the mouse pointer on the functoid.</span></span> <span data-ttu-id="5d419-117">La información sobre herramientas muestra información acerca del error y lo que tiene que hacer.</span><span class="sxs-lookup"><span data-stu-id="5d419-117">The tooltip displays information about the error and what you need to do.</span></span>  
  
         <span data-ttu-id="5d419-118">La figura siguiente muestra información sobre herramientas con información de error mientras configura el functoid “Suma”.</span><span class="sxs-lookup"><span data-stu-id="5d419-118">The following figure displays a tooltip with error information while configuring the functoid “Addition.”</span></span>  
  
         <span data-ttu-id="5d419-119">![Detección de errores en la configuración de functoid](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span><span class="sxs-lookup"><span data-stu-id="5d419-119">![Error detection in functoid configuration](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span></span>  
  
    -   <span data-ttu-id="5d419-120">Haga doble clic en el functoid.</span><span class="sxs-lookup"><span data-stu-id="5d419-120">Double-click the functoid.</span></span> <span data-ttu-id="5d419-121">El **configurar \<Functoid > Functoid** cuadro de diálogo muestra iconos de advertencia contra los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="5d419-121">The **Configure \<Functoid> Functoid** dialog box displays warning icons against the input parameters.</span></span> <span data-ttu-id="5d419-122">Esto indica que los parámetros de entrada del functoid seleccionado no están configurados.</span><span class="sxs-lookup"><span data-stu-id="5d419-122">This indicates that the input parameters of the selected functoid are not configured.</span></span>  
  
         <span data-ttu-id="5d419-123">En la siguiente ilustración se muestra información de error acerca de los parámetros de entrada para el functoid “Suma”.</span><span class="sxs-lookup"><span data-stu-id="5d419-123">The following figure displays error information about input parameters for the “Addition” functoid.</span></span>  
  
         <span data-ttu-id="5d419-124">![Advertencia aparece si no está configurado el functoid](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span><span class="sxs-lookup"><span data-stu-id="5d419-124">![Warning displayed when functoid is not configured](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d419-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d419-125">See Also</span></span>  
 [<span data-ttu-id="5d419-126">Uso de características mejoradas en el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5d419-126">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)