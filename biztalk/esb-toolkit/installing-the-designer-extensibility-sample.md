---
title: Instalación del ejemplo de extensibilidad del diseñador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eba13a4a-1b87-4268-af91-29af3a5bc5ef
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7068f86f3e6be2cd71741a6afe5f2438ac3800b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985717"
---
# <a name="installing-the-designer-extensibility-sample"></a><span data-ttu-id="ce350-102">Instalación del ejemplo de extensibilidad del diseñador</span><span class="sxs-lookup"><span data-stu-id="ce350-102">Installing the Designer Extensibility Sample</span></span>
<span data-ttu-id="ce350-103">Esta sección describe el proceso de instalación del ejemplo de extensibilidad del diseñador.</span><span class="sxs-lookup"><span data-stu-id="ce350-103">This section describes the process for installing the Designer Extensibility sample.</span></span> <span data-ttu-id="ce350-104">Debe instalar los ejemplos de [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) antes de instalar y usar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce350-104">You must install the samples in [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) before you install and use this sample.</span></span>  

 <span data-ttu-id="ce350-105">**Para instalar el ejemplo de extensibilidad del diseñador**</span><span class="sxs-lookup"><span data-stu-id="ce350-105">**To install the Designer Extensibility sample**</span></span>  

1. <span data-ttu-id="ce350-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución Microsoft Visual Studio Extenders.Itinerary.OrchestrationSample.sln.</span><span class="sxs-lookup"><span data-stu-id="ce350-106">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Microsoft Visual Studio solution file named Extenders.Itinerary.OrchestrationSample.sln.</span></span>  

2. <span data-ttu-id="ce350-107">En Visual Studio, haga clic en **compilar solución** en el **compilar** menú.</span><span class="sxs-lookup"><span data-stu-id="ce350-107">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  

3. <span data-ttu-id="ce350-108">Cierre Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce350-108">Close Visual Studio.</span></span>  

4. <span data-ttu-id="ce350-109">En el Explorador de Windows, abra la carpeta \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio con nombre Extenders.Resolvers.ResolverSample.sln.</span><span class="sxs-lookup"><span data-stu-id="ce350-109">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named Extenders.Resolvers.ResolverSample.sln.</span></span>  

5. <span data-ttu-id="ce350-110">En Visual Studio, haga clic en **compilar solución** en el **compilar** menú.</span><span class="sxs-lookup"><span data-stu-id="ce350-110">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  

6. <span data-ttu-id="ce350-111">Cierre Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce350-111">Close Visual Studio.</span></span>  

7. <span data-ttu-id="ce350-112">En el Explorador de Windows, abra la carpeta \Lib bajo la ruta de instalación del Diseñador de itinerario.</span><span class="sxs-lookup"><span data-stu-id="ce350-112">In Windows Explorer, open the \Lib folder under the Itinerary Designer install path.</span></span>  

8. <span data-ttu-id="ce350-113">Desde las carpetas \bin\Debug de las soluciones de Visual Studio creadas en los pasos anteriores, copie los archivos Extenders.Resolvers.ResolverSample.dll y Extenders.Itinerary.OrchestrationSample.dll en el directorio \Lib.</span><span class="sxs-lookup"><span data-stu-id="ce350-113">From the \bin\Debug folders of the Visual Studio solutions built in the preceding steps, copy the files Extenders.Resolvers.ResolverSample.dll and Extenders.Itinerary.OrchestrationSample.dll to the \Lib directory.</span></span>
