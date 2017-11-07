---
title: Ejemplos de adaptadores SAP | Documentos de Microsoft
description: ejemplos de adaptadores WCF mySAP que pueden usarse con BizTalk Server, modelo de servicio WCF, el modelo del canal WCF y el proveedor de datos para SAP
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d163c573003f40b2049f7e921e5edc4997b4e115
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-sap-adapter"></a><span data-ttu-id="308ed-103">Ejemplos para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="308ed-103">Samples for the SAP adapter</span></span>
<span data-ttu-id="308ed-104">Ejemplos de [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] se clasifican en categorías:</span><span class="sxs-lookup"><span data-stu-id="308ed-104">Samples for [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] are categorized into:</span></span>  
  
-   <span data-ttu-id="308ed-105">Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="308ed-105">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] samples</span></span>  
  
-   <span data-ttu-id="308ed-106">Ejemplos de modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="308ed-106">WCF service model samples</span></span>  
  
-   <span data-ttu-id="308ed-107">Ejemplos de modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="308ed-107">WCF channel model samples</span></span>  
  
-   <span data-ttu-id="308ed-108">Ejemplos de [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="308ed-108">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] samples</span></span>  

  
 <span data-ttu-id="308ed-109">Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores SAP](https://www.microsoft.com/download/details.aspx?id=1314).</span><span class="sxs-lookup"><span data-stu-id="308ed-109">The samples are available at [BizTalk Adapter Pack 2010: SAP adapter samples](https://www.microsoft.com/download/details.aspx?id=1314).</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 <span data-ttu-id="308ed-110">En la lista siguiente describe los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="308ed-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="308ed-111">Ejemplos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="308ed-111">BizTalk Server samples</span></span>  
  
|<span data-ttu-id="308ed-112">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="308ed-112">Sample Directory Name</span></span>|<span data-ttu-id="308ed-113">Description</span><span class="sxs-lookup"><span data-stu-id="308ed-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="308ed-114">IDOCSend</span><span class="sxs-lookup"><span data-stu-id="308ed-114">IDOCSend</span></span>|<span data-ttu-id="308ed-115">Muestra cómo enviar un IDOC a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-115">Demonstrates how to send an IDOC to an SAP system.</span></span>|  
|<span data-ttu-id="308ed-116">ReceiveIDOC</span><span class="sxs-lookup"><span data-stu-id="308ed-116">ReceiveIDOC</span></span>|<span data-ttu-id="308ed-117">Muestra cómo recibir un IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-117">Demonstrates how to receive an IDOC from an SAP system.</span></span>|  
|<span data-ttu-id="308ed-118">ReceiveIDOC_SYSREL</span><span class="sxs-lookup"><span data-stu-id="308ed-118">ReceiveIDOC_SYSREL</span></span>|<span data-ttu-id="308ed-119">Muestra cómo recibir un IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-119">Demonstrates how to receive an IDOC from an SAP system.</span></span> <span data-ttu-id="308ed-120">El IDOC recibido tiene el número de versión menor que el SYSREL de SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-120">The IDOC being received has the version number less than the SAP SYSREL.</span></span>|  
|<span data-ttu-id="308ed-121">RFCServer</span><span class="sxs-lookup"><span data-stu-id="308ed-121">RFCServer</span></span>|<span data-ttu-id="308ed-122">Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-122">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
|<span data-ttu-id="308ed-123">SAPTransaction</span><span class="sxs-lookup"><span data-stu-id="308ed-123">SAPTransaction</span></span>|<span data-ttu-id="308ed-124">Muestra cómo realizar transacciones en un sistema SAP mediante.</span><span class="sxs-lookup"><span data-stu-id="308ed-124">Demonstrates how to perform transactions in an SAP system using.</span></span>|  
|<span data-ttu-id="308ed-125">tRFCClient</span><span class="sxs-lookup"><span data-stu-id="308ed-125">tRFCClient</span></span>|<span data-ttu-id="308ed-126">Se muestra cómo realizar llamadas de cliente tRFC en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-126">Demonstrates how to make tRFC client calls on an SAP system.</span></span>|  
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="308ed-127">Ejemplos de modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="308ed-127">WCF service model samples</span></span>   
  
|<span data-ttu-id="308ed-128">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="308ed-128">Sample Directory Name</span></span>|<span data-ttu-id="308ed-129">Description</span><span class="sxs-lookup"><span data-stu-id="308ed-129">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="308ed-130">SapIdocStringClientSM</span><span class="sxs-lookup"><span data-stu-id="308ed-130">SapIdocStringClientSM</span></span>|<span data-ttu-id="308ed-131">Muestra cómo enviar un IDOC a un sistema SAP mediante la invocación de la operación de SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="308ed-131">Demonstrates how to send an IDOC to an SAP system by invoking the SendIdoc operation.</span></span>|  
|<span data-ttu-id="308ed-132">SapRfcServerSM</span><span class="sxs-lookup"><span data-stu-id="308ed-132">SapRfcServerSM</span></span>|<span data-ttu-id="308ed-133">Muestra cómo recibir una llamada de servidor RFC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-133">Demonstrates how to receive an RFC server call from an SAP system.</span></span>|  
|<span data-ttu-id="308ed-134">SapBapiTxClientSM</span><span class="sxs-lookup"><span data-stu-id="308ed-134">SapBapiTxClientSM</span></span>|<span data-ttu-id="308ed-135">Muestra cómo invocar BAPI dentro de una transacción en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-135">Demonstrates how to invoke BAPIs inside a transaction on an SAP system.</span></span>|  
|<span data-ttu-id="308ed-136">SapTrfcClientSM</span><span class="sxs-lookup"><span data-stu-id="308ed-136">SapTrfcClientSM</span></span>|<span data-ttu-id="308ed-137">Muestra cómo invocar las llamadas de cliente tRFC en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-137">Demonstrates how to invoke tRFC client calls on an SAP system.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="308ed-138">Ejemplos de modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="308ed-138">WCF channel model samples</span></span>  
  
|<span data-ttu-id="308ed-139">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="308ed-139">Sample Directory Name</span></span>|<span data-ttu-id="308ed-140">Description</span><span class="sxs-lookup"><span data-stu-id="308ed-140">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="308ed-141">SapIdocReceiveCM</span><span class="sxs-lookup"><span data-stu-id="308ed-141">SapIdocReceiveCM</span></span>|<span data-ttu-id="308ed-142">Muestra cómo recibir IDOC desde un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="308ed-142">Demonstrates how to receive IDOCs from an SAP system</span></span>|  
|<span data-ttu-id="308ed-143">SapRfcServerCM</span><span class="sxs-lookup"><span data-stu-id="308ed-143">SapRfcServerCM</span></span>|<span data-ttu-id="308ed-144">Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="308ed-144">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
  
## <a name="data-provider-for-sap-samples"></a><span data-ttu-id="308ed-145">Proveedor de datos para obtener ejemplos SAP</span><span class="sxs-lookup"><span data-stu-id="308ed-145">Data Provider for SAP samples</span></span>  
  
|<span data-ttu-id="308ed-146">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="308ed-146">Sample Directory Name</span></span>|<span data-ttu-id="308ed-147">Description</span><span class="sxs-lookup"><span data-stu-id="308ed-147">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="308ed-148">ado de SAP</span><span class="sxs-lookup"><span data-stu-id="308ed-148">sap ado</span></span>|<span data-ttu-id="308ed-149">Muestra cómo utilizar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="308ed-149">Demonstrates how to use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>|  
  
 
## <a name="see-also"></a><span data-ttu-id="308ed-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="308ed-150">See Also</span></span>  
[<span data-ttu-id="308ed-151">Desarrollar aplicaciones SAP</span><span class="sxs-lookup"><span data-stu-id="308ed-151">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)