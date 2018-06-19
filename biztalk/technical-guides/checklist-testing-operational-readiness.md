---
title: 'Lista de comprobación: Probar la preparación operativa | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecdf2609-ba77-4756-a949-ab4e10c54313
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bc8ff5b2b3ca8d629c30b1cb37f83cb7847b2f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299276"
---
# <a name="checklist-testing-operational-readiness"></a><span data-ttu-id="0c4b3-102">Lista de comprobación: Probar la preparación operativa</span><span class="sxs-lookup"><span data-stu-id="0c4b3-102">Checklist: Testing Operational Readiness</span></span>
<span data-ttu-id="0c4b3-103">Pruebas de preparación operativa son un procedimiento vital que a menudo se pasa por alto o se lleva a cabo mínimamente.</span><span class="sxs-lookup"><span data-stu-id="0c4b3-103">Testing for operational readiness is a vital procedure that is often overlooked or is performed only minimally.</span></span> <span data-ttu-id="0c4b3-104">Realizar pruebas minuciosas son un requisito fundamental de cualquier aplicación de nivel empresarial, y una solución desarrollada con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no es ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="0c4b3-104">Thorough testing is a critical requirement of any enterprise-level application, and a solution developed using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is no exception.</span></span> <span data-ttu-id="0c4b3-105">Como mínimo, debe realizar las siguientes pruebas antes de mover una solución de BizTalk en producción:</span><span class="sxs-lookup"><span data-stu-id="0c4b3-105">At a minimum, you should perform the following testing before moving a BizTalk solution into production:</span></span>  
  
|<span data-ttu-id="0c4b3-106">Pasos</span><span class="sxs-lookup"><span data-stu-id="0c4b3-106">Steps</span></span>|<span data-ttu-id="0c4b3-107">Referencia</span><span class="sxs-lookup"><span data-stu-id="0c4b3-107">Reference</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="0c4b3-108">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="0c4b3-108">Unit testing</span></span>|[<span data-ttu-id="0c4b3-109">Realizando pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="0c4b3-109">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)|  
|<span data-ttu-id="0c4b3-110">Pruebas funcionales</span><span class="sxs-lookup"><span data-stu-id="0c4b3-110">Functional testing</span></span>|[<span data-ttu-id="0c4b3-111">Realización de las pruebas funcionales</span><span class="sxs-lookup"><span data-stu-id="0c4b3-111">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)|  
|<span data-ttu-id="0c4b3-112">Pruebas de cuello de botella y para la optimización</span><span class="sxs-lookup"><span data-stu-id="0c4b3-112">Bottleneck testing and tuning</span></span>|[<span data-ttu-id="0c4b3-113">Realización de pruebas y ajustes de cuello de botella</span><span class="sxs-lookup"><span data-stu-id="0c4b3-113">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)|  
|<span data-ttu-id="0c4b3-114">Carga y las pruebas de rendimiento máximo sostenible (MST)</span><span class="sxs-lookup"><span data-stu-id="0c4b3-114">Load and maximum sustainable throughput (MST) testing</span></span>|[<span data-ttu-id="0c4b3-115">Realizar la carga y las pruebas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0c4b3-115">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)|  
|<span data-ttu-id="0c4b3-116">Disponibilidad de las pruebas:</span><span class="sxs-lookup"><span data-stu-id="0c4b3-116">Availability testing:</span></span><br /><br /> <span data-ttu-id="0c4b3-117">-Error de componente de hardware individual de la prueba.</span><span class="sxs-lookup"><span data-stu-id="0c4b3-117">-   Test individual hardware component failure.</span></span><br /><span data-ttu-id="0c4b3-118">-Probar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] error.</span><span class="sxs-lookup"><span data-stu-id="0c4b3-118">-   Test [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] failure.</span></span><br /><span data-ttu-id="0c4b3-119">-Probar la conmutación por error de nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="0c4b3-119">-   Test cluster node failover.</span></span><br /><span data-ttu-id="0c4b3-120">-Probar la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros de bases de datos mediante SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c4b3-120">-   Test recovery of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases using SQL Server log shipping.</span></span>|[<span data-ttu-id="0c4b3-121">Realización de las pruebas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="0c4b3-121">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)|  
  
## <a name="in-this-section"></a><span data-ttu-id="0c4b3-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0c4b3-122">In This Section</span></span>  
  
-   [<span data-ttu-id="0c4b3-123">Realizando pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="0c4b3-123">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)  
  
-   [<span data-ttu-id="0c4b3-124">Realización de las pruebas funcionales</span><span class="sxs-lookup"><span data-stu-id="0c4b3-124">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)  
  
-   [<span data-ttu-id="0c4b3-125">Realización de pruebas y ajustes de cuello de botella</span><span class="sxs-lookup"><span data-stu-id="0c4b3-125">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)  
  
-   [<span data-ttu-id="0c4b3-126">Realizar la carga y las pruebas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0c4b3-126">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)  
  
-   [<span data-ttu-id="0c4b3-127">Realización de las pruebas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="0c4b3-127">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)  
  
-   [<span data-ttu-id="0c4b3-128">Herramientas de prueba</span><span class="sxs-lookup"><span data-stu-id="0c4b3-128">Tools for Testing</span></span>](~/technical-guides/tools-for-testing.md)