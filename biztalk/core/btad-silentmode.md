---
title: BTAD_SilentMode | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31715835c98d2f60a3b5f1c18251571ea57641d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="btadsilentmode"></a><span data-ttu-id="f3c11-102">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="f3c11-102">BTAD_SilentMode</span></span>
<span data-ttu-id="f3c11-103">BTAD_SilentMode especifica opciones para ejecutar la secuencia de comando en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="f3c11-103">BTAD_SilentMode specifies options for running the script in silent mode.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3c11-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3c11-104">Remarks</span></span>  
 <span data-ttu-id="f3c11-105">Al especificar una opción en modo silencioso, el instalador de BTS coloca su valor en la variable BTAD_SilentMode.</span><span class="sxs-lookup"><span data-stu-id="f3c11-105">When you specify an option for silent mode, BTS Installer places its value into the BTAD_SilentMode variable.</span></span>  
  
 <span data-ttu-id="f3c11-106">El valor predeterminado de BTAD_SilentMode es 2, que indica que la secuencia de comandos se ejecuta en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="f3c11-106">The default value of BTAD_SilentMode is 2, which specifies that the script runs in silent mode.</span></span> <span data-ttu-id="f3c11-107">En la siguiente tabla se describen los posibles valores para BTAD_SilentMode.</span><span class="sxs-lookup"><span data-stu-id="f3c11-107">The following table describes the possible values for BTAD_SilentMode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f3c11-108">Si inicia la interfaz de usuario de BizTalk Server desde secuencias de comandos, es posible que los cuadros de diálogo modales no estén visibles o tengan foco que dificulte su visión y omisión.</span><span class="sxs-lookup"><span data-stu-id="f3c11-108">If you start the BizTalk Server user interface from scripts, modal dialog boxes may not be visible or have focus, making them difficult to view and dismiss.</span></span> <span data-ttu-id="f3c11-109">Las bases de datos BizTalk pueden bloquearse y ser inaccesibles mientras los cuadros de diálogo modales están abiertos.</span><span class="sxs-lookup"><span data-stu-id="f3c11-109">The BizTalk databases can become locked and inaccessible while modal dialog boxes are open.</span></span> <span data-ttu-id="f3c11-110">Por este motivo, en los sistemas de producción, todas las secuencias de comandos deberían ejecutarse en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="f3c11-110">For this reason, on production systems, all scripts should run in silent mode.</span></span>  
  
|<span data-ttu-id="f3c11-111">Value</span><span class="sxs-lookup"><span data-stu-id="f3c11-111">Value</span></span>|<span data-ttu-id="f3c11-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3c11-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3c11-113">0</span><span class="sxs-lookup"><span data-stu-id="f3c11-113">0</span></span>|<span data-ttu-id="f3c11-114">No cambia el nivel de la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="f3c11-114">Does not change the user interface (UI) level.</span></span>|  
|<span data-ttu-id="f3c11-115">1</span><span class="sxs-lookup"><span data-stu-id="f3c11-115">1</span></span>|<span data-ttu-id="f3c11-116">Usa el nivel de IU predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3c11-116">Uses the default UI level.</span></span>|  
|<span data-ttu-id="f3c11-117">2</span><span class="sxs-lookup"><span data-stu-id="f3c11-117">2</span></span>|<span data-ttu-id="f3c11-118">Realiza una instalación silenciosa (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f3c11-118">Performs a silent installation (the default).</span></span>|  
|<span data-ttu-id="f3c11-119">3</span><span class="sxs-lookup"><span data-stu-id="f3c11-119">3</span></span>|<span data-ttu-id="f3c11-120">Proporciona un progreso simple y control de errores.</span><span class="sxs-lookup"><span data-stu-id="f3c11-120">Provides simple progress and error handling.</span></span>|  
|<span data-ttu-id="f3c11-121">4</span><span class="sxs-lookup"><span data-stu-id="f3c11-121">4</span></span>|<span data-ttu-id="f3c11-122">Proporciona IU creada; suprime asistentes.</span><span class="sxs-lookup"><span data-stu-id="f3c11-122">Provides authored UI; suppresses wizards.</span></span>|  
|<span data-ttu-id="f3c11-123">0x80</span><span class="sxs-lookup"><span data-stu-id="f3c11-123">0x80</span></span>|<span data-ttu-id="f3c11-124">Si se combina con algún valor de los anteriores, Windows Installer muestra un cuadro de diálogo modal si la secuencia de comandos se ha ejecutado correctamente o si se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="f3c11-124">If combined with any above value, Windows Installer displays a modal dialog box if the script has executed successfully or if there has been an error.</span></span> <span data-ttu-id="f3c11-125">No se muestra ningún cuadro de diálogo modal si el usuario cancela la operación.</span><span class="sxs-lookup"><span data-stu-id="f3c11-125">No dialog box is displayed if the user cancels the operation.</span></span>|  
|<span data-ttu-id="f3c11-126">0x40</span><span class="sxs-lookup"><span data-stu-id="f3c11-126">0x40</span></span>|<span data-ttu-id="f3c11-127">Si se combina con el valor 3, Windows Installer muestra cuadros de diálogo de progreso pero no muestra ningún cuadro de diálogo modal ni de error.</span><span class="sxs-lookup"><span data-stu-id="f3c11-127">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="f3c11-128">0x20</span><span class="sxs-lookup"><span data-stu-id="f3c11-128">0x20</span></span>|<span data-ttu-id="f3c11-129">Si se combina con el valor 3, Windows Installer muestra cuadros de diálogo de progreso pero no muestra ningún cuadro de diálogo modal ni de error.</span><span class="sxs-lookup"><span data-stu-id="f3c11-129">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="f3c11-130">0x100</span><span class="sxs-lookup"><span data-stu-id="f3c11-130">0x100</span></span>|<span data-ttu-id="f3c11-131">Si se combina con el valor 3, Windows Installer muestra cuadros de diálogo de progreso pero no muestra ningún cuadro de diálogo modal ni de error.</span><span class="sxs-lookup"><span data-stu-id="f3c11-131">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3c11-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3c11-132">See Also</span></span>  
 <span data-ttu-id="f3c11-133">[Variables de entorno de secuencia de comandos previas y posteriores al procesamiento](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f3c11-133">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="f3c11-134">Cómo las Variables de entorno indican el estado de implementación</span><span class="sxs-lookup"><span data-stu-id="f3c11-134">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)