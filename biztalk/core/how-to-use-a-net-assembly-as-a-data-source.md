---
title: Cómo usar un ensamblado .NET como origen de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: 14dbec48-acc9-4c3c-bd7f-737dabf29543
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa56370cf894d0d18a36320ca97c4d028fee487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-net-assembly-as-a-data-source"></a><span data-ttu-id="aaeb1-102">Cómo utilizar un ensamblado .NET como origen de datos</span><span class="sxs-lookup"><span data-stu-id="aaeb1-102">How to Use a .NET Assembly as a Data Source</span></span>
<span data-ttu-id="aaeb1-103">Puede especificar un ensamblado .NET como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-103">You can specify a .NET assembly as a data source.</span></span> <span data-ttu-id="aaeb1-104">A continuación, puede seleccionar una clase o miembro de clase del ensamblado y arrastrarla hasta una definición de vocabulario o regla.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-104">You can subsequently select a class or class member from the assembly, and drag it onto a vocabulary definition or rule.</span></span>  
  
### <a name="to-specify-a-net-assembly-as-a-data-source"></a><span data-ttu-id="aaeb1-105">Para especificar un ensamblado .NET como origen de datos</span><span class="sxs-lookup"><span data-stu-id="aaeb1-105">To specify a .NET assembly as a data source</span></span>  
  
1.  <span data-ttu-id="aaeb1-106">En la ventana Explorador de hechos, haga clic en el **clases .NET** ficha.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-106">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="aaeb1-107">Haga clic en el **módulos** nodo.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-107">Right-click the **Modules** node.</span></span>  
  
3.  <span data-ttu-id="aaeb1-108">Seleccione un ensamblado .NET de entre los disponibles.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-108">From the available assemblies, select a .NET assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aaeb1-109">Los ensamblados tienen que estar en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="aaeb1-109">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="aaeb1-110">El Compositor de reglas de negocio carga un ensamblado .NET al buscar el ensamblado de .NET en el **Explorador de hechos** ventana o en la **clase .NET o una definición de miembro de clase** página de la **vocabulario Definición de** ventana.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-110">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="aaeb1-111">Si actualiza el ensamblado en la GAC, cierre el Compositor de reglas de negocios y reinícielo para cargar el ensamblado .NET actualizado.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-111">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="aaeb1-112">El Compositor de reglas de negocio no actualiza el ensamblado de forma automática.</span><span class="sxs-lookup"><span data-stu-id="aaeb1-112">The business rule composer does not refresh the assembly automatically.</span></span>  
  
     <span data-ttu-id="aaeb1-113">![Captura de pantalla del explorador de árbol de definición y hechos. ] (../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")</span><span class="sxs-lookup"><span data-stu-id="aaeb1-113">![Screenshot of facts and definition tree browser.](../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")</span></span>