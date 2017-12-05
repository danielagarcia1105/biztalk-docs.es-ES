---
title: "Instalar el ejemplo de extensibilidad del diseñador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eba13a4a-1b87-4268-af91-29af3a5bc5ef
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea0cd71c22fdd614d2e49c996939b785ecadf8bd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-designer-extensibility-sample"></a>Instalar el ejemplo de extensibilidad del diseñador
Esta sección describe el proceso de instalación del ejemplo de extensibilidad del diseñador. Debe instalar los ejemplos en [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) antes de instalar y utilizar este ejemplo.  
  
 **Para instalar el ejemplo de extensibilidad del diseñador**  
  
1.  En el Explorador de Windows, abra el \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample carpeta, donde se instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Microsoft Visual Studio denominado Extenders.Itinerary.OrchestrationSample.sln.  
  
2.  En Visual Studio, haga clic en **generar solución** en el **generar** menú.  
  
3.  Cierre Visual Studio.  
  
4.  En el Explorador de Windows, abra el \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample carpeta, donde se instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio con el nombre Extenders.Resolvers.ResolverSample.sln.  
  
5.  En Visual Studio, haga clic en **generar solución** en el **generar** menú.  
  
6.  Cierre Visual Studio.  
  
7.  En el Explorador de Windows, abra la carpeta \Lib de la ruta de instalación del Diseñador de itinerario.  
  
8.  Desde las carpetas \bin\Debug de las soluciones de Visual Studio generadas en los pasos anteriores, copie los archivos Extenders.Resolvers.ResolverSample.dll y Extenders.Itinerary.OrchestrationSample.dll en el directorio \Lib.