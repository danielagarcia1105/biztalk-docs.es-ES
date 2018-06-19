---
title: Utilizar contadores de rendimiento con el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2a9f345745c18ca03086833fffe3553e96cece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216076"
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="74747-102">Utilizar contadores de rendimiento con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="74747-102">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="74747-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] los clientes pueden usar los contadores de rendimiento para medir el rendimiento de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="74747-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="74747-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento **BizTalk Adapter de .NET para Oracle E-Business Suite** junto con la instalación del [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74747-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle E-Business Suite** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="74747-105">Contador de rendimiento de tiempo (acumulado) de LOB</span><span class="sxs-lookup"><span data-stu-id="74747-105">LOB Time (Cumulative) performance counter</span></span>  
 <span data-ttu-id="74747-106">El **BizTalk Adapter de .NET para Oracle E-Business Suite** categoría tiene un contador de rendimiento denominado el "LOB tiempo (acumulado)".</span><span class="sxs-lookup"><span data-stu-id="74747-106">The **BizTalk .NET Adapter for Oracle E-Business Suite** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="74747-107">Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente LOB que se tarda en completar una acción que inicia el adaptador.</span><span class="sxs-lookup"><span data-stu-id="74747-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="74747-108">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] crea una instancia del contador de rendimiento en cualquiera de los siguientes modelos:</span><span class="sxs-lookup"><span data-stu-id="74747-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="74747-109">Donde "cadena" podría ser:</span><span class="sxs-lookup"><span data-stu-id="74747-109">Where "string" could be:</span></span>  
  
-   <span data-ttu-id="74747-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="74747-110">Connection.Open</span></span>  
  
-   <span data-ttu-id="74747-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="74747-111">Connection.Close</span></span>  
  
-   <span data-ttu-id="74747-112">Metadatos</span><span class="sxs-lookup"><span data-stu-id="74747-112">Metadata</span></span>  
  
-   <span data-ttu-id="74747-113">Acción de mensaje.</span><span class="sxs-lookup"><span data-stu-id="74747-113">Message action.</span></span> <span data-ttu-id="74747-114">Por ejemplo, si la acción es `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` , a continuación, la cadena será InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="74747-114">For example, if the action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` then the string will be InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="74747-115">El origen de datos de Oracle es el mismo que el especificado en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="74747-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
 <span data-ttu-id="74747-116">El contador de rendimiento se inicializa solo una vez que el adaptador realiza la primera llamada a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="74747-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="74747-117">Además, la propiedad InstanceLifetime del contador de rendimiento se establece en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador.</span><span class="sxs-lookup"><span data-stu-id="74747-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="74747-118">La precisión del contador de rendimiento de tiempo de LOB (acumulado) es 16 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="74747-118">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="74747-119">Habilitar los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="74747-119">Enabling Performance Counters</span></span>  
 <span data-ttu-id="74747-120">Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace **EnablePerformanceCounters**.</span><span class="sxs-lookup"><span data-stu-id="74747-120">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="74747-121">Para habilitar los contadores de rendimiento, establezca la **EnablePerformanceCounters** enlazar la propiedad a **True**.</span><span class="sxs-lookup"><span data-stu-id="74747-121">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="74747-122">Para deshabilitar los contadores de rendimiento, establezca **EnablePerformanceCounters** a **False**.</span><span class="sxs-lookup"><span data-stu-id="74747-122">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="74747-123">De forma predeterminada, **EnablePerformanceCounters** está establecido en **False**.</span><span class="sxs-lookup"><span data-stu-id="74747-123">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="74747-124">Contadores de rendimiento y el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="74747-124">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="74747-125">Cambiar el valor de la **EnablePerformanceCounters** enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74747-125">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="74747-126">Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico.</span><span class="sxs-lookup"><span data-stu-id="74747-126">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="74747-127">Por lo tanto, si hay dos instancias de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace en el AppDomain y **EnablePerformanceCounters** enlaza la propiedad se establece en **True** en uno y **False** en el otro, el contador de rendimiento específicas del adaptador estará habilitado en una y deshabilitado en el otro.</span><span class="sxs-lookup"><span data-stu-id="74747-127">Therefore, if there are two instances of the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="74747-128">Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establece como **True** o **False** dependiendo de qué valor se especifica en último lugar.</span><span class="sxs-lookup"><span data-stu-id="74747-128">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74747-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="74747-129">See Also</span></span>  
[<span data-ttu-id="74747-130">Solucionar problemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="74747-130">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)