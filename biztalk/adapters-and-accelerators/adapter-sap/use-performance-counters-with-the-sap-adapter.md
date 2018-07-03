---
title: Utilice los contadores de rendimiento con el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7818f5f5cf24bd1d4e58da2c24691813fc2b761f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991461"
---
# <a name="use-performance-counters-with-the-sap-adapter"></a><span data-ttu-id="e409c-102">Utilice los contadores de rendimiento con el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="e409c-102">Use Performance Counters with the SAP adapter</span></span>
<span data-ttu-id="e409c-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] los clientes pueden usar los contadores de rendimiento para medir el rendimiento de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="e409c-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="e409c-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento "[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]" a lo largo de instalar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e409c-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]" along installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="e409c-105">Contador de rendimiento de tiempo (acumulativo) de LOB</span><span class="sxs-lookup"><span data-stu-id="e409c-105">LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="e409c-106">El **.NET adaptador de BizTalk para SAP** categoría tiene un contador de rendimiento denominado el "tiempo LOB (acumulativo)".</span><span class="sxs-lookup"><span data-stu-id="e409c-106">The **BizTalk .NET Adapter for SAP** category has one performance counter called the "LOB Time (Cumulative)".</span></span> <span data-ttu-id="e409c-107">Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente de línea de negocio que se tarda en completar una acción que inicia el adaptador.</span><span class="sxs-lookup"><span data-stu-id="e409c-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="e409c-108">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] crea una instancia del contador de rendimiento en el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="e409c-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates an instance of the performance counter in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="e409c-109">El identificador de punto de conexión podría ser:</span><span class="sxs-lookup"><span data-stu-id="e409c-109">The endpoint ID could be:</span></span>  
  
- <span data-ttu-id="e409c-110">Para las llamadas desde el adaptador al sistema SAP (saliente)</span><span class="sxs-lookup"><span data-stu-id="e409c-110">For calls from the adapter to the SAP system (outbound)</span></span>  
  
  -   <span data-ttu-id="e409c-111">A,\<host del servidor de aplicación\>,\<número del sistema\></span><span class="sxs-lookup"><span data-stu-id="e409c-111">A,\<application server host\>,\<system number\></span></span>  
  
  -   <span data-ttu-id="e409c-112">B,\<host del servidor de mensaje\>,\<R3NAME\></span><span class="sxs-lookup"><span data-stu-id="e409c-112">B,\<message server host\>,\<R3NAME\></span></span>  
  
  -   <span data-ttu-id="e409c-113">D.,\<destino\></span><span class="sxs-lookup"><span data-stu-id="e409c-113">D,\<destination\></span></span>  
  
- <span data-ttu-id="e409c-114">Para las llamadas desde el sistema SAP para el adaptador (entrante)</span><span class="sxs-lookup"><span data-stu-id="e409c-114">For calls from the SAP system to the adapter (inbound)</span></span>  
  
  -   <span data-ttu-id="e409c-115">I,\<host de puerta de enlace\>,\<servidor de puerta de enlace\></span><span class="sxs-lookup"><span data-stu-id="e409c-115">I,\<gateway host\>,\<gateway server\></span></span>  
  
  -   <span data-ttu-id="e409c-116">Id.,\<destino\></span><span class="sxs-lookup"><span data-stu-id="e409c-116">ID,\<destination\></span></span>  
  
  <span data-ttu-id="e409c-117">El identificador de acción podría ser:</span><span class="sxs-lookup"><span data-stu-id="e409c-117">The action ID could be:</span></span>  
  
- <span data-ttu-id="e409c-118">\<Nombre de la RFC\> (para una llamada de RFC)</span><span class="sxs-lookup"><span data-stu-id="e409c-118">\<RFC name\> (for an RFC call)</span></span>  
  
- <span data-ttu-id="e409c-119">T,\<nombre RFC\> (para una llamada tRFC)</span><span class="sxs-lookup"><span data-stu-id="e409c-119">T,\<RFC name\> (for a tRFC call)</span></span>  
  
  <span data-ttu-id="e409c-120">Se ha inicializado el contador de rendimiento solo una vez que el adaptador realiza la primera llamada al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="e409c-120">The performance counter is initialized only after the adapter makes the first call to the SAP system.</span></span> <span data-ttu-id="e409c-121">Además, el [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) propiedad del contador de rendimiento se establece en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador.</span><span class="sxs-lookup"><span data-stu-id="e409c-121">Also, the [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e409c-122">La precisión del contador de rendimiento de tiempo de LOB (acumulativo) es 16 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="e409c-122">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="e409c-123">Habilitar los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="e409c-123">Enabling Performance Counters</span></span>  
 <span data-ttu-id="e409c-124">Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace *EnablePerformanceCounters*.</span><span class="sxs-lookup"><span data-stu-id="e409c-124">The performance counters can be enabled or disabled by setting the binding property *EnablePerformanceCounters*.</span></span> <span data-ttu-id="e409c-125">Para habilitar los contadores de rendimiento, establezca el *EnablePerformanceCounters* enlazar la propiedad a **True**.</span><span class="sxs-lookup"><span data-stu-id="e409c-125">To enable performance counters, set the *EnablePerformanceCounters* binding property to **True**.</span></span> <span data-ttu-id="e409c-126">Para deshabilitar los contadores de rendimiento, establezca *EnablePerformanceCounters* a **False**.</span><span class="sxs-lookup"><span data-stu-id="e409c-126">To disable performance counters, set *EnablePerformanceCounters* to **False**.</span></span> <span data-ttu-id="e409c-127">De forma predeterminada, *EnablePerformanceCounters* está establecido en **False**.</span><span class="sxs-lookup"><span data-stu-id="e409c-127">By default, *EnablePerformanceCounters* is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="e409c-128">Contadores de rendimiento y el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e409c-128">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="e409c-129">Cambiar el valor de la *EnablePerformanceCounters* enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e409c-129">Changing the value of the *EnablePerformanceCounters* binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="e409c-130">Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico.</span><span class="sxs-lookup"><span data-stu-id="e409c-130">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="e409c-131">Por lo tanto, si hay dos instancias de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace en el AppDomain y el *EnablePerformanceCounters* enlaza la propiedad se establece en **True** en uno y **False**en el otro, el contador de rendimiento específicas del adaptador estará habilitado en uno y deshabilitado en el otro.</span><span class="sxs-lookup"><span data-stu-id="e409c-131">Hence, if there are two instances of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding in the AppDomain, and the *EnablePerformanceCounters* binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="e409c-132">Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establecerá en **True** o **False** dependiendo de qué valor se especifica en último lugar.</span><span class="sxs-lookup"><span data-stu-id="e409c-132">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e409c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e409c-133">See Also</span></span>  

[<span data-ttu-id="e409c-134">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="e409c-134">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)