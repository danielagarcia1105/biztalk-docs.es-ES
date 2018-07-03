---
title: Cómo depurar asignaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f30d26b7c722ea4e4896bc7d19130e41eec5c719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989725"
---
# <a name="how-to-debug-maps"></a><span data-ttu-id="37957-102">Depuración de asignaciones</span><span class="sxs-lookup"><span data-stu-id="37957-102">How to Debug Maps</span></span>
<span data-ttu-id="37957-103">El **depurar asignación** característica es útil para identificar y corregir problemas de asignación complejos.</span><span class="sxs-lookup"><span data-stu-id="37957-103">The **Debug Map** feature is useful in identifying and fixing complex mapping issues.</span></span> <span data-ttu-id="37957-104">Este tema proporciona instrucciones paso a paso para la depuración de asignaciones mediante el depurador XSLT en línea.</span><span class="sxs-lookup"><span data-stu-id="37957-104">This topic provides step-by-step instructions for debugging maps using the inline XSLT debugger.</span></span>  

> [!NOTE]
>  <span data-ttu-id="37957-105">Al depurar la asignación, el **depurar asignación** característica usa las propiedades de archivo de asignación **instancia de entrada de comprobar asignación** y **instancia de salida de comprobar asignación**.</span><span class="sxs-lookup"><span data-stu-id="37957-105">When debugging the map, the **Debug Map** feature uses the map file properties **TestMap Input Instance** and **TestMap Output Instance**.</span></span> <span data-ttu-id="37957-106">Por lo tanto, antes de depurar la asignación, se recomienda que configure la entrada y propiedades de instancia en el archivo de asignación de salida.</span><span class="sxs-lookup"><span data-stu-id="37957-106">Therefore, before you debug the map, we recommend that you configure the input and output instance properties in the map file.</span></span>  

### <a name="to-debug-a-biztalk-map"></a><span data-ttu-id="37957-107">Para depurar un asignación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="37957-107">To debug a BizTalk map</span></span>  

1. <span data-ttu-id="37957-108">En el Explorador de soluciones, haga clic en el mapa que desee probar y, a continuación, haga clic en **depurar asignación**.</span><span class="sxs-lookup"><span data-stu-id="37957-108">In Solution Explorer, right-click the map you want to test, and then click **Debug Map**.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="37957-109"> Muestra la asignación en formato XSLT en su editor.</span><span class="sxs-lookup"><span data-stu-id="37957-109"> displays the map in XSLT format in its editor.</span></span>  

2. <span data-ttu-id="37957-110">Presione F10 o F11 para depurar el código XSL.</span><span class="sxs-lookup"><span data-stu-id="37957-110">Press F10 or F11 to debug the XSL code.</span></span> <span data-ttu-id="37957-111">Al presionar F11 en una llamada de functoid, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] pasa al código C# del functoid.</span><span class="sxs-lookup"><span data-stu-id="37957-111">When you press F11 on a functoid call, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] steps into the C# code for the functoid.</span></span> <span data-ttu-id="37957-112">Los valores de las variables usadas en el código fuente del functoid se pueden ver en el Depurador local de Windows.</span><span class="sxs-lookup"><span data-stu-id="37957-112">You can view the values of variables used in the functoid source code in the Local Windows Debugger.</span></span>
