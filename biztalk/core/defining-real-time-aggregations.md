---
title: "Definición de agregaciones en tiempo real | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b2df32149f67a002a5a6281b6f1abd848523a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-real-time-aggregations"></a>Definición de agregaciones en tiempo real
A veces, las agregaciones multidimensionales tienen sectores con tales limitaciones temporales que conviene tenerlos disponibles en tiempo real. Por ejemplo, una empresa vende productos perecederos y el usuario desea tener disponible en tiempo real la agregación de la cantidad de productos en diferentes fases de entrega. Al mismo tiempo, también desea tener otras agregaciones, tal como la edad de los clientes, pero solo a finales de mes para el análisis de inteligencia empresarial.  
  
-   Mediante el **tabla dinámica** barra de herramientas, marque la tabla dinámica seleccionada como una agregación en tiempo real (ATR), si es aplicable. El tipo de datos de la tabla dinámica debe determinar si necesita verla en tiempo real. Por ejemplo, si un informe somete a seguimiento los pedidos por web cada hora, puede ser necesario verlo en tiempo real. En cambio, esto no será necesario para un informe que somete a seguimiento los totales de ventas diarios.  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
Botón ATR  
  
> [!IMPORTANT]
>  No defina varias ATR que usan la misma actividad de BAM . Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.  
  
 Para obtener más información acerca de las tablas dinámicas, consulte la Ayuda en pantalla de Excel. Una vez creada la tabla dinámica, podrá ver sus datos de BAM activos.  
  
## <a name="see-also"></a>Vea también  
 [Ver datos de BAM en vivo](../core/viewing-live-bam-data.md)   
 [Dimensión de progreso](../core/progress-dimension.md)   
 [Dimensión de datos](../core/data-dimension.md)   
 [Dimensión de tiempo](../core/time-dimension.md)   
 [Dimensión de rango numérico](../core/numeric-range-dimension.md)   
 [Definir dimensiones](../core/defining-dimensions.md)