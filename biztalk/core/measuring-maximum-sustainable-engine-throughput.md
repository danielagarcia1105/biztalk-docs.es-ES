---
title: "Medir el rendimiento máximo sostenible del motor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST)
- maximum sustainable throughput (MST), about maximum sustainable throughput (MST)
- performance, maximum sustainable thoughput (MST)
ms.assetid: d83f734f-1a44-4da0-a755-45ba204cadaf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5507aca58669ed5c81034ba91e16d1183e07188
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="measuring-maximum-sustainable-engine-throughput"></a><span data-ttu-id="c15c5-102">Medir el rendimiento máximo sostenible del motor</span><span class="sxs-lookup"><span data-stu-id="c15c5-102">Measuring Maximum Sustainable Engine Throughput</span></span>
<span data-ttu-id="c15c5-103">Una de las consideraciones principales al planear un sistema de BizTalk Server debería consistir en determinar el rendimiento máximo sostenible del sistema.</span><span class="sxs-lookup"><span data-stu-id="c15c5-103">One of the primary considerations when planning a BizTalk Server system should be to determine the maximum sustainable throughput (MST) of the system.</span></span> <span data-ttu-id="c15c5-104">El rendimiento máximo sostenible de un sistema de BizTalk Server representa la carga más elevada del tráfico de mensajes que el sistema de BizTalk puede controlar sin límites en la producción.</span><span class="sxs-lookup"><span data-stu-id="c15c5-104">The MST of a BizTalk Server system is measured as the highest load of message traffic that the BizTalk system can handle indefinitely in production.</span></span> <span data-ttu-id="c15c5-105">La importancia de este rendimiento radica en el hecho de que si la carga supera el rendimiento máximo sostenible, los mensajes se acumulan en la base de datos de cuadro de mensajes y es posible que se retrase la entrega del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c15c5-105">This is important because as load exceeds MST, messages are backlogged in the MessageBox database and message delivery may be delayed.</span></span> <span data-ttu-id="c15c5-106">Si realiza el cálculo del rendimiento máximo sostenible del sistema de BizTalk Server durante la comprobación habitual, puede escalar el sistema para evitar que se produzcan escenarios extendidos de sobrecarga en la producción.</span><span class="sxs-lookup"><span data-stu-id="c15c5-106">If you calculate the MST of your BizTalk Server system as part of normal testing then you can scale your system to avoid extended overload scenarios in production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c15c5-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c15c5-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c15c5-108">Factores que afectan al rendimiento sostenible máximo</span><span class="sxs-lookup"><span data-stu-id="c15c5-108">Factors that Affect Maximum Sustainable Performance</span></span>](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [<span data-ttu-id="c15c5-109">Escenarios de prueba para medir MST del motor de</span><span class="sxs-lookup"><span data-stu-id="c15c5-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [<span data-ttu-id="c15c5-110">Recomendaciones al probar el rendimiento del motor</span><span class="sxs-lookup"><span data-stu-id="c15c5-110">Recommendations When Testing Engine Performance</span></span>](../core/recommendations-when-testing-engine-performance.md)