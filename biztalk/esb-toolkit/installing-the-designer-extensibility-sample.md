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
# <a name="installing-the-designer-extensibility-sample"></a>Instalación del ejemplo de extensibilidad del diseñador
Esta sección describe el proceso de instalación del ejemplo de extensibilidad del diseñador. Debe instalar los ejemplos de [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) antes de instalar y usar este ejemplo.  

 **Para instalar el ejemplo de extensibilidad del diseñador**  

1. En el Explorador de Windows, abra la carpeta \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución Microsoft Visual Studio Extenders.Itinerary.OrchestrationSample.sln.  

2. En Visual Studio, haga clic en **compilar solución** en el **compilar** menú.  

3. Cierre Visual Studio.  

4. En el Explorador de Windows, abra la carpeta \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio con nombre Extenders.Resolvers.ResolverSample.sln.  

5. En Visual Studio, haga clic en **compilar solución** en el **compilar** menú.  

6. Cierre Visual Studio.  

7. En el Explorador de Windows, abra la carpeta \Lib bajo la ruta de instalación del Diseñador de itinerario.  

8. Desde las carpetas \bin\Debug de las soluciones de Visual Studio creadas en los pasos anteriores, copie los archivos Extenders.Resolvers.ResolverSample.dll y Extenders.Itinerary.OrchestrationSample.dll en el directorio \Lib.
