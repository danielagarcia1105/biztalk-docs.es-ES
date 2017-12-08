---
title: Solucionar problemas de rendimiento con el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9e18a2f26af993da36a13d389f2aff2ad2f60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a><span data-ttu-id="c4a66-102">Solucionar problemas de rendimiento con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="c4a66-102">Troubleshoot Performance Issues with the SAP adapter</span></span>
<span data-ttu-id="c4a66-103">Esta sección describe el uso de técnicas de solución de problemas para resolver los problemas de rendimiento que pueden surgir al usar [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4a66-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
##  <a name="BKMK_SAPSlowdown"></a><span data-ttu-id="c4a66-104">Degradación o pausa en el rendimiento al usar el adaptador con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c4a66-104">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="c4a66-105">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c4a66-105">**Problem**</span></span>  
  
 <span data-ttu-id="c4a66-106">Cuando se usa el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el número de mensajes enviados o recibidos por el adaptador se ralentiza o se trata de una pausa.</span><span class="sxs-lookup"><span data-stu-id="c4a66-106">When using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="c4a66-107">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c4a66-107">**Cause**</span></span>  
  
 <span data-ttu-id="c4a66-108">El **EnableBizTalkCompatibilityMode** no está establecida la propiedad de enlace en WCF-Custom enviar o puerto de recepción en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c4a66-108">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="c4a66-109">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c4a66-109">**Resolution**</span></span>  
  
 <span data-ttu-id="c4a66-110">Establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en True.</span><span class="sxs-lookup"><span data-stu-id="c4a66-110">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="c4a66-111">Para obtener más información acerca de esta propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c4a66-111">For more information about this property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span> <span data-ttu-id="c4a66-112">Para obtener instrucciones sobre cómo establecer una propiedad de enlace, consulte [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c4a66-112">For instructions on how to set a binding property, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
##  <a name="BKMK_SAPMemLeak"></a><span data-ttu-id="c4a66-113">Posible pérdida de memoria al usar valores NULL para los parámetros</span><span class="sxs-lookup"><span data-stu-id="c4a66-113">Possible memory leak when using NULL values for parameters</span></span>  
 <span data-ttu-id="c4a66-114">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c4a66-114">**Problem**</span></span>  
  
 <span data-ttu-id="c4a66-115">Puede observar memoria perder en caso de no especificar valores para parámetros de entrada o una tabla al invocar artefactos en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="c4a66-115">You may observe memory leak if you do not specify values for input or table parameters while invoking artifacts in the SAP system.</span></span>  
  
 <span data-ttu-id="c4a66-116">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c4a66-116">**Resolution**</span></span>  
  
 <span data-ttu-id="c4a66-117">Asegúrese de que se especifican valores para todos los parámetros de entrada y la tabla al invocar un artefacto en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="c4a66-117">Make sure you specify values for all the input and table parameters while invoking an artifact in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a66-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4a66-118">See Also</span></span>  
[<span data-ttu-id="c4a66-119">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="c4a66-119">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)