---
title: "Solución de problemas no - línea de negocio adaptadores de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba36ed8a8efb62e2eb8e885791c3c28012dcc49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a><span data-ttu-id="1fab3-102">Solución de problemas de adaptadores de línea de negocio distintos de WCF</span><span class="sxs-lookup"><span data-stu-id="1fab3-102">Troubleshooting non-WCF Line of Business Adapters</span></span>
## <a name="failed-to-retrieve-error"></a><span data-ttu-id="1fab3-103">Error al recuperar</span><span class="sxs-lookup"><span data-stu-id="1fab3-103">“Failed to retrieve” error</span></span>  
 <span data-ttu-id="1fab3-104">Si se usa un adaptador de línea de negocio (LOB) distinto de WCF, se pueden producir los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="1fab3-104">When using a non-WCF Line of Business (LOB) adapter, the following errors may occur:</span></span>  
  
-   <span data-ttu-id="1fab3-105">Error al recuperar el sistema</span><span class="sxs-lookup"><span data-stu-id="1fab3-105">Failed to retrieve system</span></span>  
  
-   <span data-ttu-id="1fab3-106">Agente de exploración: ha registrado un Error en el constructor.</span><span class="sxs-lookup"><span data-stu-id="1fab3-106">Browsing agent: Error trapped in constructor.</span></span> <span data-ttu-id="1fab3-107">El equipo de destino rechazó la conexión.</span><span class="sxs-lookup"><span data-stu-id="1fab3-107">Target machine Actively refused connection.</span></span>  
  
-   <span data-ttu-id="1fab3-108">Agente de tiempo de ejecución: ha registrado un Error en el constructor.</span><span class="sxs-lookup"><span data-stu-id="1fab3-108">Runtime agent: Error trapped in constructor.</span></span> <span data-ttu-id="1fab3-109">El equipo de destino rechazó la conexión.</span><span class="sxs-lookup"><span data-stu-id="1fab3-109">Target machine Actively refused connection.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="1fab3-110">Causa</span><span class="sxs-lookup"><span data-stu-id="1fab3-110">Cause</span></span>  
 <span data-ttu-id="1fab3-111">Los adaptadores de LOB usan las características remotas de .Net.</span><span class="sxs-lookup"><span data-stu-id="1fab3-111">The LOB adapters use .Net Remoting.</span></span> <span data-ttu-id="1fab3-112">Si la activación de las características remotas de .Net tarda más de lo previsto, puede que el adaptador devuelva estos errores.</span><span class="sxs-lookup"><span data-stu-id="1fab3-112">If the .Net Remoting activation takes longer than expected, the adapter may return these errors.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="1fab3-113">Solución</span><span class="sxs-lookup"><span data-stu-id="1fab3-113">Resolution</span></span>  
 <span data-ttu-id="1fab3-114">Crear el **StartAgentSleep** clave del registro y aumente el valor de tiempo de espera:</span><span class="sxs-lookup"><span data-stu-id="1fab3-114">Create the **StartAgentSleep** registry key and increase the timeout value:</span></span>  
  
1.  <span data-ttu-id="1fab3-115">Abra el registro y vaya a *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.</span><span class="sxs-lookup"><span data-stu-id="1fab3-115">Open the registry and go to *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.</span></span>  
  
2.  <span data-ttu-id="1fab3-116">Cree un valor de DWORD nuevo con las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1fab3-116">Create a new DWORD value with the following properties:</span></span>  
  
     <span data-ttu-id="1fab3-117">Nombre: StartAgentSleep</span><span class="sxs-lookup"><span data-stu-id="1fab3-117">Name: StartAgentSleep</span></span>  
  
     <span data-ttu-id="1fab3-118">Base: Decimal</span><span class="sxs-lookup"><span data-stu-id="1fab3-118">Base: Decimal</span></span>  
  
     <span data-ttu-id="1fab3-119">Datos del valor: 1000</span><span class="sxs-lookup"><span data-stu-id="1fab3-119">Value data: 1000</span></span>  
  
 <span data-ttu-id="1fab3-120">El valor de datos se mide en milisegundos (ms).</span><span class="sxs-lookup"><span data-stu-id="1fab3-120">Value data is measured in milliseconds (ms).</span></span> <span data-ttu-id="1fab3-121">1000 ms equivalen a 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="1fab3-121">1000ms equals 1 second.</span></span>  
  
 <span data-ttu-id="1fab3-122">En algunos sistemas, puede que un segundo no sea suficiente.</span><span class="sxs-lookup"><span data-stu-id="1fab3-122">In some systems, one second may not be enough.</span></span> <span data-ttu-id="1fab3-123">Aumente el valor y haga pruebas para determinar el tiempo de espera necesario.</span><span class="sxs-lookup"><span data-stu-id="1fab3-123">Increase the value and test to help determine the appropriate timeout needed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1fab3-124">Agregar el **StartAgentSleep** impactos de clave del registro **todos los** los adaptadores de LOB distintos de WCF.</span><span class="sxs-lookup"><span data-stu-id="1fab3-124">Adding the **StartAgentSleep** registry key impacts **all** the non-WCF LOB adapters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fab3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fab3-125">See Also</span></span>  
 [<span data-ttu-id="1fab3-126">Solución de problemas de adaptadores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1fab3-126">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)