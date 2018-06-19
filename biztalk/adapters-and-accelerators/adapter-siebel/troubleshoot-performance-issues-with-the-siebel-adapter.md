---
title: Solucionar problemas de rendimiento con el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6443dd8b96b19b3cf42f6444ba1ae6c16f2b4ee6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221996"
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a><span data-ttu-id="f4dd0-102">Solucionar problemas de rendimiento con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="f4dd0-102">Troubleshoot Performance Issues with the Siebel adapter</span></span>
<span data-ttu-id="f4dd0-103">Esta sección describe el uso de técnicas de solución de problemas para resolver los problemas de rendimiento que pueden surgir al usar [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4dd0-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="f4dd0-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="f4dd0-104">Known Issues</span></span>  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="f4dd0-105">Degradación o pausa en el rendimiento al usar el adaptador con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f4dd0-105">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="f4dd0-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="f4dd0-106">**Problem**</span></span>  
  
 <span data-ttu-id="f4dd0-107">Cuando se usa el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el número de mensajes enviados o recibidos por el adaptador se ralentiza o se trata de una pausa.</span><span class="sxs-lookup"><span data-stu-id="f4dd0-107">When using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="f4dd0-108">**Causa**</span><span class="sxs-lookup"><span data-stu-id="f4dd0-108">**Cause**</span></span>  
  
 <span data-ttu-id="f4dd0-109">El **EnableBizTalkCompatibilityMode** no está establecida la propiedad de enlace en WCF-Custom enviar o puerto de recepción en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f4dd0-109">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="f4dd0-110">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="f4dd0-110">**Resolution**</span></span>  
  
 <span data-ttu-id="f4dd0-111">Establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en True.</span><span class="sxs-lookup"><span data-stu-id="f4dd0-111">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="f4dd0-112">Para obtener más información acerca de esta propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f4dd0-112">For more information about this property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span> <span data-ttu-id="f4dd0-113">Para obtener instrucciones sobre cómo establecer una propiedad de enlace, consulte [configurar las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="f4dd0-113">For instructions on how to set a binding property, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dd0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4dd0-114">See Also</span></span>  
[<span data-ttu-id="f4dd0-115">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="f4dd0-115">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)