---
title: Solucionar problemas de rendimiento con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba487bcd5d6d245c979dec903613465ae54f8d9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962354"
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="14632-102">Solucionar problemas de rendimiento con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="14632-102">Troubleshoot performance issues with the Oracle Database adapter</span></span>
<span data-ttu-id="14632-103">Esta sección describe el uso de técnicas de solución de problemas para resolver los problemas de rendimiento que pueden surgir al usar [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14632-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="14632-104">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="14632-104">Known Issue</span></span>  
 <span data-ttu-id="14632-105">Éste es el problema de rendimiento más comunes que pueden surgir al usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], junto con su causa y resolución.</span><span class="sxs-lookup"><span data-stu-id="14632-105">The following is the most common performance issue you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with its probable cause and resolution.</span></span>  
  
##  <a name="BKMK_Slowdown"></a><span data-ttu-id="14632-106">Degradación o pausa en el rendimiento al usar el adaptador con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="14632-106">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="14632-107">**Problema**</span><span class="sxs-lookup"><span data-stu-id="14632-107">**Problem**</span></span>  
  
 <span data-ttu-id="14632-108">Cuando se usa el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el número de mensajes enviados o recibidos por el adaptador se ralentiza o se trata de una pausa.</span><span class="sxs-lookup"><span data-stu-id="14632-108">When using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="14632-109">**Causa**</span><span class="sxs-lookup"><span data-stu-id="14632-109">**Cause**</span></span>  
  
 <span data-ttu-id="14632-110">El **EnableBizTalkCompatibilityMode** no está establecida la propiedad de enlace en WCF-Custom enviar o puerto de recepción en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="14632-110">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="14632-111">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="14632-111">**Resolution**</span></span>  
  
 <span data-ttu-id="14632-112">Establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en True.</span><span class="sxs-lookup"><span data-stu-id="14632-112">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="14632-113">Para obtener más información acerca de esta propiedad, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="14632-113">For more information about this property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="14632-114">Para obtener instrucciones sobre cómo establecer una propiedad de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="14632-114">For instructions on how to set a binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a><span data-ttu-id="14632-115">Posible pérdida de memoria en un equipo de 64 bits cuando se usa el adaptador de la base de datos de Oracle para realizar operaciones relacionadas con el tipo de datos FLOAT</span><span class="sxs-lookup"><span data-stu-id="14632-115">Possible memory leak on a 64-bit computer when using the Oracle database adapter to perform operations involving FLOAT data type</span></span>  
 <span data-ttu-id="14632-116">**Problema**</span><span class="sxs-lookup"><span data-stu-id="14632-116">**Problem**</span></span>  
  
 <span data-ttu-id="14632-117">Puede experimentar una pérdida de memoria cuando se usa el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en un equipo de 64 bits para realizar las operaciones que implican tipos de datos FLOAT.</span><span class="sxs-lookup"><span data-stu-id="14632-117">You may experience a memory leak when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on a 64-bit computer to perform operations that involve FLOAT data types.</span></span>  
  
 <span data-ttu-id="14632-118">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="14632-118">**Resolution**</span></span>  
  
 <span data-ttu-id="14632-119">Instale .NET \< *versión* \> (x64) en el equipo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="14632-119">Install .NET \<*version*\> (x64) on the 64-bit computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14632-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="14632-120">See Also</span></span>  
[<span data-ttu-id="14632-121">Solucionar problemas del Oracle adapter.md la base de datos</span><span class="sxs-lookup"><span data-stu-id="14632-121">Troubleshoot the Oracle Database adapter.md</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)