---
title: "Getservicecontractcallpoint (operación) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e291bcf733129991f6d3b5000ca8e9bc1353057
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getservicecontractcallpoint"></a><span data-ttu-id="e45b7-102">GetServiceContractCallPoint (operación)</span><span class="sxs-lookup"><span data-stu-id="e45b7-102">GetServiceContractCallPoint</span></span>
<span data-ttu-id="e45b7-103">Inserta el nombre del punto de llamada de contrato de servicio actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="e45b7-103">Pushes the name of the current service contract call point onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e45b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e45b7-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e45b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e45b7-105">Parameters</span></span>  
 <span data-ttu-id="e45b7-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e45b7-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="e45b7-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="e45b7-107">Pushed Value</span></span>  
 <span data-ttu-id="e45b7-108">Cadena que contiene el punto de llamada de contrato actual.</span><span class="sxs-lookup"><span data-stu-id="e45b7-108">String containing the current contract call point.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e45b7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e45b7-109">Remarks</span></span>  
 <span data-ttu-id="e45b7-110">Se puede interceptar un servicio de Windows Communication Framework en distintos puntos de la duración del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="e45b7-110">A Windows Communication Framework service can be intercepted at different points in the lifetime of the service contract.</span></span> <span data-ttu-id="e45b7-111">Estas ubicaciones se definen mediante la enumeración `System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint`:</span><span class="sxs-lookup"><span data-stu-id="e45b7-111">These locations are defined by the `System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint` enumeration:</span></span>  
  
|<span data-ttu-id="e45b7-112">Punto de llamada de contrato</span><span class="sxs-lookup"><span data-stu-id="e45b7-112">Contract call point</span></span>|<span data-ttu-id="e45b7-113">Description</span><span class="sxs-lookup"><span data-stu-id="e45b7-113">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="e45b7-114">ClientReply</span><span class="sxs-lookup"><span data-stu-id="e45b7-114">ClientReply</span></span>|<span data-ttu-id="e45b7-115">Punto de llamada de respuesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="e45b7-115">Client reply call point.</span></span>|  
|<span data-ttu-id="e45b7-116">ClientRequest</span><span class="sxs-lookup"><span data-stu-id="e45b7-116">ClientRequest</span></span>|<span data-ttu-id="e45b7-117">Punto de llamada de solicitud del cliente.</span><span class="sxs-lookup"><span data-stu-id="e45b7-117">Client request call point.</span></span>|  
|<span data-ttu-id="e45b7-118">ClientFault</span><span class="sxs-lookup"><span data-stu-id="e45b7-118">ClientFault</span></span>|<span data-ttu-id="e45b7-119">Punto de error del cliente.</span><span class="sxs-lookup"><span data-stu-id="e45b7-119">Client fault point.</span></span>|  
|<span data-ttu-id="e45b7-120">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="e45b7-120">ServiceReply</span></span>|<span data-ttu-id="e45b7-121">Punto de llamada de respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="e45b7-121">Service reply call point.</span></span>|  
|<span data-ttu-id="e45b7-122">ServiceRequest</span><span class="sxs-lookup"><span data-stu-id="e45b7-122">ServiceRequest</span></span>|<span data-ttu-id="e45b7-123">Punto de llamada de solicitud del servicio.</span><span class="sxs-lookup"><span data-stu-id="e45b7-123">Service request call point.</span></span>|  
|<span data-ttu-id="e45b7-124">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="e45b7-124">ServiceFault</span></span>|<span data-ttu-id="e45b7-125">Punto de error del servicio.</span><span class="sxs-lookup"><span data-stu-id="e45b7-125">Service fault point.</span></span>|  
|<span data-ttu-id="e45b7-126">CallbackRequest</span><span class="sxs-lookup"><span data-stu-id="e45b7-126">CallbackRequest</span></span>|<span data-ttu-id="e45b7-127">Punto de llamada de solicitud de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e45b7-127">Callback request call point.</span></span>|  
|<span data-ttu-id="e45b7-128">CallbackReply</span><span class="sxs-lookup"><span data-stu-id="e45b7-128">CallbackReply</span></span>|<span data-ttu-id="e45b7-129">Punto de llamada de respuesta de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e45b7-129">Callback reply call point.</span></span>|  
|<span data-ttu-id="e45b7-130">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="e45b7-130">CallbackFault</span></span>|<span data-ttu-id="e45b7-131">Punto de error de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e45b7-131">Callback fault point.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e45b7-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e45b7-132">Example</span></span>  
 <span data-ttu-id="e45b7-133">El siguiente ejemplo contiene una expresión de filtro de eventos configurada para buscar una operación específica ("Receive") en el estado de respuesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="e45b7-133">The following sample contains an event filter expression configured to find a specific operation ("Receive") in the client reply state.</span></span> <span data-ttu-id="e45b7-134">Para ello, se usa una combinación de operaciones, incluidas `GetOperationName`, `GetServiceContractCallPoint` y operaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="e45b7-134">This is done by using a combination of operations including `GetOperationName`, `GetServiceContractCallPoint`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ClientReply</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e45b7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e45b7-135">See Also</span></span>  
 [<span data-ttu-id="e45b7-136">Operaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e45b7-136">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)