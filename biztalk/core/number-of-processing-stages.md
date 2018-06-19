---
title: Número de fases de procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f61c5c348e54ea096c921cb6fc63f0db339dbf4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263116"
---
# <a name="number-of-processing-stages"></a><span data-ttu-id="773da-102">Número de fases de procesamiento</span><span class="sxs-lookup"><span data-stu-id="773da-102">Number of Processing Stages</span></span>
<span data-ttu-id="773da-103">La solución separa el proceso de pedido en fases, de modo que se pueda modificar el proceso (al sustituir fases) sin interrumpir los pedidos de larga duración.</span><span class="sxs-lookup"><span data-stu-id="773da-103">The solution separates the order process into stages, so that it is possible to modify the process (by replacing stages) without disrupting long-running orders.</span></span> <span data-ttu-id="773da-104">Para obtener más información acerca de cómo se dividió el proceso en fases, vea "Dividir procesos empresariales" en [algunos principios de diseño de la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="773da-104">For more information about how the process was divided into stages, see "Dividing Business Processes" in [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="773da-105">La versión actual de la solución sólo contiene dos etapas de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="773da-105">The current version of the solution contains only two processing stages.</span></span> <span data-ttu-id="773da-106">No obstante, podría incluir muchas más.</span><span class="sxs-lookup"><span data-stu-id="773da-106">It could, however, contain many more.</span></span> <span data-ttu-id="773da-107">Un mayor número de fases proporciona más puntos en los que se pueden controlar las versiones del proceso y seguir trabajando en la versión más reciente de una fase de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="773da-107">More stages provide more points where you can version the process and continue working on the latest version of a processing stage.</span></span> <span data-ttu-id="773da-108">Sin embargo, cada fase agrega una sobrecarga de mensajes de coordinación adicionales que pasan por la base de datos de cuadro de mensajes, lo que aumenta el tiempo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="773da-108">However, each stage introduces the overhead of additional coordinating messages going through the MessageBox database, which increases processing time.</span></span> <span data-ttu-id="773da-109">Debe supervisar el rendimiento de la solución para determinar si el número de fases es excesivo.</span><span class="sxs-lookup"><span data-stu-id="773da-109">You must monitor the solution's performance to determine if the number of multiple stages is excessive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773da-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="773da-110">See Also</span></span>  
 <span data-ttu-id="773da-111">[Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="773da-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="773da-112">Lógica del Administrador de procesos</span><span class="sxs-lookup"><span data-stu-id="773da-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)