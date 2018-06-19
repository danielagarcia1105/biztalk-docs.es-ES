---
title: Instalar el ejemplo de extensibilidad del diseñador | Documentos de Microsoft
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
ms.openlocfilehash: ea0cd71c22fdd614d2e49c996939b785ecadf8bd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007981"
---
# <a name="installing-the-designer-extensibility-sample"></a><span data-ttu-id="a870a-102">Instalar el ejemplo de extensibilidad del diseñador</span><span class="sxs-lookup"><span data-stu-id="a870a-102">Installing the Designer Extensibility Sample</span></span>
<span data-ttu-id="a870a-103">Esta sección describe el proceso de instalación del ejemplo de extensibilidad del diseñador.</span><span class="sxs-lookup"><span data-stu-id="a870a-103">This section describes the process for installing the Designer Extensibility sample.</span></span> <span data-ttu-id="a870a-104">Debe instalar los ejemplos en [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) antes de instalar y utilizar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a870a-104">You must install the samples in [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) before you install and use this sample.</span></span>  
  
 <span data-ttu-id="a870a-105">**Para instalar el ejemplo de extensibilidad del diseñador**</span><span class="sxs-lookup"><span data-stu-id="a870a-105">**To install the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="a870a-106">En el Explorador de Windows, abra el \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample carpeta, donde se instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Microsoft Visual Studio denominado Extenders.Itinerary.OrchestrationSample.sln.</span><span class="sxs-lookup"><span data-stu-id="a870a-106">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Microsoft Visual Studio solution file named Extenders.Itinerary.OrchestrationSample.sln.</span></span>  
  
2.  <span data-ttu-id="a870a-107">En Visual Studio, haga clic en **generar solución** en el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="a870a-107">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="a870a-108">Cierre Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a870a-108">Close Visual Studio.</span></span>  
  
4.  <span data-ttu-id="a870a-109">En el Explorador de Windows, abra el \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample carpeta, donde se instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio con el nombre Extenders.Resolvers.ResolverSample.sln.</span><span class="sxs-lookup"><span data-stu-id="a870a-109">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named Extenders.Resolvers.ResolverSample.sln.</span></span>  
  
5.  <span data-ttu-id="a870a-110">En Visual Studio, haga clic en **generar solución** en el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="a870a-110">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  
  
6.  <span data-ttu-id="a870a-111">Cierre Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a870a-111">Close Visual Studio.</span></span>  
  
7.  <span data-ttu-id="a870a-112">En el Explorador de Windows, abra la carpeta \Lib de la ruta de instalación del Diseñador de itinerario.</span><span class="sxs-lookup"><span data-stu-id="a870a-112">In Windows Explorer, open the \Lib folder under the Itinerary Designer install path.</span></span>  
  
8.  <span data-ttu-id="a870a-113">Desde las carpetas \bin\Debug de las soluciones de Visual Studio generadas en los pasos anteriores, copie los archivos Extenders.Resolvers.ResolverSample.dll y Extenders.Itinerary.OrchestrationSample.dll en el directorio \Lib.</span><span class="sxs-lookup"><span data-stu-id="a870a-113">From the \bin\Debug folders of the Visual Studio solutions built in the preceding steps, copy the files Extenders.Resolvers.ResolverSample.dll and Extenders.Itinerary.OrchestrationSample.dll to the \Lib directory.</span></span>