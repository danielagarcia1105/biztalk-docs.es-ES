---
title: Ejemplos de adaptadores de SAP | Microsoft Docs
description: ejemplos de adaptadores WCF mySAP que pueden utilizarse con el proveedor de datos, modelo de servicio WCF, el modelo del canal WCF y BizTalk Server para SAP
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1926c9899d1c1198998c25845d5d6b4189884f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012069"
---
# <a name="samples-for-the-sap-adapter"></a><span data-ttu-id="a8843-103">Ejemplos para el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="a8843-103">Samples for the SAP adapter</span></span>
<span data-ttu-id="a8843-104">Ejemplos para [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] se clasifican en categorías:</span><span class="sxs-lookup"><span data-stu-id="a8843-104">Samples for [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] are categorized into:</span></span>  

- <span data-ttu-id="a8843-105">Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8843-105">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] samples</span></span>  

- <span data-ttu-id="a8843-106">Ejemplos de modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a8843-106">WCF service model samples</span></span>  

- <span data-ttu-id="a8843-107">Ejemplos de modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="a8843-107">WCF channel model samples</span></span>  

- <span data-ttu-id="a8843-108">Ejemplos de [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8843-108">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] samples</span></span>  


 <span data-ttu-id="a8843-109">Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores SAP](https://www.microsoft.com/download/details.aspx?id=1314).</span><span class="sxs-lookup"><span data-stu-id="a8843-109">The samples are available at [BizTalk Adapter Pack 2010: SAP adapter samples](https://www.microsoft.com/download/details.aspx?id=1314).</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

 <span data-ttu-id="a8843-110">En la lista siguiente describe los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a8843-110">The following list describes the samples.</span></span>

## <a name="biztalk-server-samples"></a><span data-ttu-id="a8843-111">Ejemplos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a8843-111">BizTalk Server samples</span></span>  

|<span data-ttu-id="a8843-112">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8843-112">Sample Directory Name</span></span>|<span data-ttu-id="a8843-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8843-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a8843-114">IDOCSend</span><span class="sxs-lookup"><span data-stu-id="a8843-114">IDOCSend</span></span>|<span data-ttu-id="a8843-115">Muestra cómo enviar un IDOC a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-115">Demonstrates how to send an IDOC to an SAP system.</span></span>|  
|<span data-ttu-id="a8843-116">ReceiveIDOC</span><span class="sxs-lookup"><span data-stu-id="a8843-116">ReceiveIDOC</span></span>|<span data-ttu-id="a8843-117">Muestra cómo recibir un IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-117">Demonstrates how to receive an IDOC from an SAP system.</span></span>|  
|<span data-ttu-id="a8843-118">ReceiveIDOC_SYSREL</span><span class="sxs-lookup"><span data-stu-id="a8843-118">ReceiveIDOC_SYSREL</span></span>|<span data-ttu-id="a8843-119">Muestra cómo recibir un IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-119">Demonstrates how to receive an IDOC from an SAP system.</span></span> <span data-ttu-id="a8843-120">El IDOC recibido tiene el número de versión menor que el SYSREL de SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-120">The IDOC being received has the version number less than the SAP SYSREL.</span></span>|  
|<span data-ttu-id="a8843-121">RFCServer</span><span class="sxs-lookup"><span data-stu-id="a8843-121">RFCServer</span></span>|<span data-ttu-id="a8843-122">Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-122">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
|<span data-ttu-id="a8843-123">SAPTransaction</span><span class="sxs-lookup"><span data-stu-id="a8843-123">SAPTransaction</span></span>|<span data-ttu-id="a8843-124">Muestra cómo realizar transacciones en un sistema SAP mediante.</span><span class="sxs-lookup"><span data-stu-id="a8843-124">Demonstrates how to perform transactions in an SAP system using.</span></span>|  
|<span data-ttu-id="a8843-125">tRFCClient</span><span class="sxs-lookup"><span data-stu-id="a8843-125">tRFCClient</span></span>|<span data-ttu-id="a8843-126">Se muestra cómo realizar llamadas de tRFC de cliente en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-126">Demonstrates how to make tRFC client calls on an SAP system.</span></span>|  

## <a name="wcf-service-model-samples"></a><span data-ttu-id="a8843-127">Ejemplos de modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a8843-127">WCF service model samples</span></span>   

|<span data-ttu-id="a8843-128">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8843-128">Sample Directory Name</span></span>|<span data-ttu-id="a8843-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8843-129">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a8843-130">SapIdocStringClientSM</span><span class="sxs-lookup"><span data-stu-id="a8843-130">SapIdocStringClientSM</span></span>|<span data-ttu-id="a8843-131">Muestra cómo enviar un IDOC a un sistema SAP mediante la invocación de la operación SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="a8843-131">Demonstrates how to send an IDOC to an SAP system by invoking the SendIdoc operation.</span></span>|  
|<span data-ttu-id="a8843-132">SapRfcServerSM</span><span class="sxs-lookup"><span data-stu-id="a8843-132">SapRfcServerSM</span></span>|<span data-ttu-id="a8843-133">Muestra cómo recibir una llamada al servidor RFC de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-133">Demonstrates how to receive an RFC server call from an SAP system.</span></span>|  
|<span data-ttu-id="a8843-134">SapBapiTxClientSM</span><span class="sxs-lookup"><span data-stu-id="a8843-134">SapBapiTxClientSM</span></span>|<span data-ttu-id="a8843-135">Se muestra cómo invocar BAPI dentro de una transacción en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-135">Demonstrates how to invoke BAPIs inside a transaction on an SAP system.</span></span>|  
|<span data-ttu-id="a8843-136">SapTrfcClientSM</span><span class="sxs-lookup"><span data-stu-id="a8843-136">SapTrfcClientSM</span></span>|<span data-ttu-id="a8843-137">Muestra cómo invocar tRFC las llamadas del cliente en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-137">Demonstrates how to invoke tRFC client calls on an SAP system.</span></span>|  

## <a name="wcf-channel-model-samples"></a><span data-ttu-id="a8843-138">Ejemplos de modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="a8843-138">WCF channel model samples</span></span>  

|<span data-ttu-id="a8843-139">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8843-139">Sample Directory Name</span></span>|<span data-ttu-id="a8843-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8843-140">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a8843-141">SapIdocReceiveCM</span><span class="sxs-lookup"><span data-stu-id="a8843-141">SapIdocReceiveCM</span></span>|<span data-ttu-id="a8843-142">Muestra cómo recibir los IDOC desde un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="a8843-142">Demonstrates how to receive IDOCs from an SAP system</span></span>|  
|<span data-ttu-id="a8843-143">SapRfcServerCM</span><span class="sxs-lookup"><span data-stu-id="a8843-143">SapRfcServerCM</span></span>|<span data-ttu-id="a8843-144">Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a8843-144">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  

## <a name="data-provider-for-sap-samples"></a><span data-ttu-id="a8843-145">Proveedor de datos para obtener ejemplos SAP</span><span class="sxs-lookup"><span data-stu-id="a8843-145">Data Provider for SAP samples</span></span>  

| <span data-ttu-id="a8843-146">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8843-146">Sample Directory Name</span></span> |                                             <span data-ttu-id="a8843-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8843-147">Description</span></span>                                              |
|-----------------------|------------------------------------------------------------------------------------------------------|
|        <span data-ttu-id="a8843-148">ado de SAP</span><span class="sxs-lookup"><span data-stu-id="a8843-148">sap ado</span></span>        | <span data-ttu-id="a8843-149">Muestra cómo usar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8843-149">Demonstrates how to use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> |

## <a name="see-also"></a><span data-ttu-id="a8843-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8843-150">See Also</span></span>  
[<span data-ttu-id="a8843-151">Desarrollar aplicaciones SAP</span><span class="sxs-lookup"><span data-stu-id="a8843-151">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)