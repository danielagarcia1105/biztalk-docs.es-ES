---
title: Solución de problemas no - línea de negocio de adaptadores de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c5e9b2ffe7e74fc7bf14c3d14a22a93e288b30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997056"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a><span data-ttu-id="48a42-102">Solución de problemas de adaptadores de línea de negocio distintos de WCF</span><span class="sxs-lookup"><span data-stu-id="48a42-102">Troubleshooting non-WCF Line of Business Adapters</span></span>
## <a name="failed-to-retrieve-error"></a><span data-ttu-id="48a42-103">Error al recuperar</span><span class="sxs-lookup"><span data-stu-id="48a42-103">“Failed to retrieve” error</span></span>  
 <span data-ttu-id="48a42-104">Si se usa un adaptador de línea de negocio (LOB) distinto de WCF, se pueden producir los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="48a42-104">When using a non-WCF Line of Business (LOB) adapter, the following errors may occur:</span></span>  
  
-   <span data-ttu-id="48a42-105">Error al recuperar el sistema</span><span class="sxs-lookup"><span data-stu-id="48a42-105">Failed to retrieve system</span></span>  
  
-   <span data-ttu-id="48a42-106">Agente de exploración: ha registrado un Error en el constructor.</span><span class="sxs-lookup"><span data-stu-id="48a42-106">Browsing agent: Error trapped in constructor.</span></span> <span data-ttu-id="48a42-107">El equipo de destino rechazó la conexión.</span><span class="sxs-lookup"><span data-stu-id="48a42-107">Target machine Actively refused connection.</span></span>  
  
-   <span data-ttu-id="48a42-108">Agente de tiempo de ejecución: ha registrado un Error en el constructor.</span><span class="sxs-lookup"><span data-stu-id="48a42-108">Runtime agent: Error trapped in constructor.</span></span> <span data-ttu-id="48a42-109">El equipo de destino rechazó la conexión.</span><span class="sxs-lookup"><span data-stu-id="48a42-109">Target machine Actively refused connection.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="48a42-110">Causa</span><span class="sxs-lookup"><span data-stu-id="48a42-110">Cause</span></span>  
 <span data-ttu-id="48a42-111">Los adaptadores de LOB usan las características remotas de .Net.</span><span class="sxs-lookup"><span data-stu-id="48a42-111">The LOB adapters use .Net Remoting.</span></span> <span data-ttu-id="48a42-112">Si la activación de las características remotas de .Net tarda más de lo previsto, puede que el adaptador devuelva estos errores.</span><span class="sxs-lookup"><span data-stu-id="48a42-112">If the .Net Remoting activation takes longer than expected, the adapter may return these errors.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="48a42-113">Solución</span><span class="sxs-lookup"><span data-stu-id="48a42-113">Resolution</span></span>  
 <span data-ttu-id="48a42-114">Crear el **StartAgentSleep** clave del registro y aumente el valor de tiempo de espera:</span><span class="sxs-lookup"><span data-stu-id="48a42-114">Create the **StartAgentSleep** registry key and increase the timeout value:</span></span>  
  
1. <span data-ttu-id="48a42-115">Abra el registro y vaya a *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.</span><span class="sxs-lookup"><span data-stu-id="48a42-115">Open the registry and go to *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.</span></span>  
  
2. <span data-ttu-id="48a42-116">Cree un valor de DWORD nuevo con las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="48a42-116">Create a new DWORD value with the following properties:</span></span>  
  
    <span data-ttu-id="48a42-117">Nombre: StartAgentSleep</span><span class="sxs-lookup"><span data-stu-id="48a42-117">Name: StartAgentSleep</span></span>  
  
    <span data-ttu-id="48a42-118">Base: Decimal</span><span class="sxs-lookup"><span data-stu-id="48a42-118">Base: Decimal</span></span>  
  
    <span data-ttu-id="48a42-119">Datos del valor: 1000</span><span class="sxs-lookup"><span data-stu-id="48a42-119">Value data: 1000</span></span>  
  
   <span data-ttu-id="48a42-120">El valor de datos se mide en milisegundos (ms).</span><span class="sxs-lookup"><span data-stu-id="48a42-120">Value data is measured in milliseconds (ms).</span></span> <span data-ttu-id="48a42-121">1000 ms equivalen a 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="48a42-121">1000ms equals 1 second.</span></span>  
  
   <span data-ttu-id="48a42-122">En algunos sistemas, puede que un segundo no sea suficiente.</span><span class="sxs-lookup"><span data-stu-id="48a42-122">In some systems, one second may not be enough.</span></span> <span data-ttu-id="48a42-123">Aumente el valor y haga pruebas para determinar el tiempo de espera necesario.</span><span class="sxs-lookup"><span data-stu-id="48a42-123">Increase the value and test to help determine the appropriate timeout needed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48a42-124">Agregar el **StartAgentSleep** impactos de clave del registro **todas** los adaptadores de LOB distintos de WCF.</span><span class="sxs-lookup"><span data-stu-id="48a42-124">Adding the **StartAgentSleep** registry key impacts **all** the non-WCF LOB adapters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a42-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="48a42-125">See Also</span></span>  
 [<span data-ttu-id="48a42-126">Solución de problemas de adaptadores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="48a42-126">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)