---
title: "Cómo depurar mapas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40964b267ad0788308a92490a106f940a6cb33e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-debug-maps"></a><span data-ttu-id="1d9f3-102">Depuración de asignaciones</span><span class="sxs-lookup"><span data-stu-id="1d9f3-102">How to Debug Maps</span></span>
<span data-ttu-id="1d9f3-103">El **depurar asignación** característica es útil para identificar y solucionar problemas de asignación complejos.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-103">The **Debug Map** feature is useful in identifying and fixing complex mapping issues.</span></span> <span data-ttu-id="1d9f3-104">Este tema proporciona instrucciones paso a paso para la depuración de asignaciones mediante el depurador XSLT en línea.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-104">This topic provides step-by-step instructions for debugging maps using the inline XSLT debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d9f3-105">Al depurar la asignación, el **depurar asignación** característica usa las propiedades de archivo de asignación **instancia de entrada de comprobar asignación** y **instancia de salida de comprobar asignación**.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-105">When debugging the map, the **Debug Map** feature uses the map file properties **TestMap Input Instance** and **TestMap Output Instance**.</span></span> <span data-ttu-id="1d9f3-106">Por lo tanto, antes de depurar la asignación, se recomienda que configure la entrada y propiedades de instancia en el archivo de asignación de salida.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-106">Therefore, before you debug the map, we recommend that you configure the input and output instance properties in the map file.</span></span>  
  
### <a name="to-debug-a-biztalk-map"></a><span data-ttu-id="1d9f3-107">Para depurar un asignación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1d9f3-107">To debug a BizTalk map</span></span>  
  
1.  <span data-ttu-id="1d9f3-108">En el Explorador de soluciones, haga clic en la asignación que desea probar y, a continuación, haga clic en **depurar asignación**.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-108">In Solution Explorer, right-click the map you want to test, and then click **Debug Map**.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="1d9f3-109">Muestra la asignación en formato XSLT en su editor.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-109"> displays the map in XSLT format in its editor.</span></span>  
  
2.  <span data-ttu-id="1d9f3-110">Presione F10 o F11 para depurar el código XSL.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-110">Press F10 or F11 to debug the XSL code.</span></span> <span data-ttu-id="1d9f3-111">Al presionar F11 en una llamada de functoid, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] pasa al código C# del functoid.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-111">When you press F11 on a functoid call, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] steps into the C# code for the functoid.</span></span> <span data-ttu-id="1d9f3-112">Los valores de las variables usadas en el código fuente del functoid se pueden ver en el Depurador local de Windows.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-112">You can view the values of variables used in the functoid source code in the Local Windows Debugger.</span></span>