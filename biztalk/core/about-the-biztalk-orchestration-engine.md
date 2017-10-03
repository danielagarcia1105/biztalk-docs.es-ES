---
title: "Acerca del motor de orquestación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4e686f066c2fcde921e45d08b60d6386e86640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-biztalk-orchestration-engine"></a><span data-ttu-id="03c69-102">Motor de orquestaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="03c69-102">About the BizTalk Orchestration Engine</span></span>
<span data-ttu-id="03c69-103">En tiempo de ejecución, el motor de orquestaciones de BizTalk ejecuta archivos XLANG/s que produce el Diseñador de orquestaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="03c69-103">At run time, the BizTalk Orchestration Engine executes XLANG/s files that are produced by BizTalk Orchestration Designer.</span></span> <span data-ttu-id="03c69-104">El Diseñador de orquestaciones es una completa herramienta gráfica para diseñar visualmente procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="03c69-104">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="03c69-105">Genera archivos XLANG/s con una extensión .odx que contienen información adicional de visualización en los encabezados, e información de atributos personalizados en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="03c69-105">It generates XLANG/s files that have an .odx extension and contain additional visualization information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03c69-106">XLANG/s se puede ver como un lenguaje de mensajería con algunas de las capacidades de expresión de C#.</span><span class="sxs-lookup"><span data-stu-id="03c69-106">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span>  
  
 <span data-ttu-id="03c69-107">Las funciones principales del motor de orquestaciones son:</span><span class="sxs-lookup"><span data-stu-id="03c69-107">The primary functions of the orchestration engine are:</span></span>  
  
-   <span data-ttu-id="03c69-108">Persistencia</span><span class="sxs-lookup"><span data-stu-id="03c69-108">Persistence</span></span>  
  
-   <span data-ttu-id="03c69-109">Alojar los componentes .NET</span><span class="sxs-lookup"><span data-stu-id="03c69-109">Hosting the .NET components</span></span>  
  
-   <span data-ttu-id="03c69-110">Transactions</span><span class="sxs-lookup"><span data-stu-id="03c69-110">Transactions</span></span>  
  
-   <span data-ttu-id="03c69-111">Compatibilidad con mensajes grandes</span><span class="sxs-lookup"><span data-stu-id="03c69-111">Large message support</span></span>  
  
-   <span data-ttu-id="03c69-112">Validación en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="03c69-112">Runtime validation</span></span>  
  
-   <span data-ttu-id="03c69-113">Limitación de carga</span><span class="sxs-lookup"><span data-stu-id="03c69-113">Load throttling</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03c69-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="03c69-114">In This Section</span></span>  
  
-   [<span data-ttu-id="03c69-115">Persistencia y el motor de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="03c69-115">Persistence and the Orchestration Engine</span></span>](../core/persistence-and-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="03c69-116">Orquestación deshidratación y rehidratación</span><span class="sxs-lookup"><span data-stu-id="03c69-116">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [<span data-ttu-id="03c69-117">Validación en tiempo de ejecución para el motor de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="03c69-117">Runtime Validation for the Orchestration Engine</span></span>](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="03c69-118">Configuración del motor de orquestación</span><span class="sxs-lookup"><span data-stu-id="03c69-118">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="03c69-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="03c69-119">See Also</span></span>  
 <span data-ttu-id="03c69-120">[Arquitectura de BizTalk Server](../core/biztalk-server-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="03c69-120">[BizTalk Server Architecture](../core/biztalk-server-architecture.md) </span></span>  
 <span data-ttu-id="03c69-121">[Lenguaje XLANG-s.](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="03c69-121">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="03c69-122">[Optimizar el uso de recursos mediante la limitación de Host](../core/optimizing-resource-usage-through-host-throttling.md) </span><span class="sxs-lookup"><span data-stu-id="03c69-122">[Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) </span></span>  
 [<span data-ttu-id="03c69-123">Cómo BizTalk Server procesa los mensajes de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="03c69-123">How BizTalk Server Processes Large Messages</span></span>](../core/how-biztalk-server-processes-large-messages.md)