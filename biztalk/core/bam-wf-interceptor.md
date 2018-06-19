---
title: Interceptor de WF de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e459084-cb72-4a75-9f5f-f1fd5fd80d17
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de770da5ee0f5d3270b0ee649b6bda61dc6d156e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231372"
---
# <a name="bam-wf-interceptor"></a><span data-ttu-id="dba75-102">Interceptor de WF de BAM</span><span class="sxs-lookup"><span data-stu-id="dba75-102">BAM WF Interceptor</span></span>
<span data-ttu-id="dba75-103">El interceptor de WF de BAM proporciona compatibilidad completa para los datos de seguimiento en su aplicación WF.</span><span class="sxs-lookup"><span data-stu-id="dba75-103">The BAM WF interceptor provides comprehensive support for tracking data within your WF application.</span></span>  
  
 <span data-ttu-id="dba75-104">Puede utilizar el interceptor de WF de BAM base para:</span><span class="sxs-lookup"><span data-stu-id="dba75-104">You can use the BAM WF interceptor to:</span></span>  
  
-   <span data-ttu-id="dba75-105">Enviar de forma transparente datos de aplicaciones de flujo de trabajo a BAM sin tener que volver a compilar su aplicación WF.</span><span class="sxs-lookup"><span data-stu-id="dba75-105">Transparently deliver workflow application data to BAM without having to recompile your WF application.</span></span>  
  
-   <span data-ttu-id="dba75-106">Dirigir actividades específicas dentro de un flujo de trabajo con el fin de enviar de forma selectiva datos de aplicaciones de flujo de trabajo a BAM.</span><span class="sxs-lookup"><span data-stu-id="dba75-106">Target specific activities within a workflow to selectively deliver workflow application data to BAM.</span></span>  
  
-   <span data-ttu-id="dba75-107">Cumplir con la semántica de transacciones del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dba75-107">Honor the transactional semantics of the workflow.</span></span> <span data-ttu-id="dba75-108">Los datos se enviarán a BAM sólo si se confirma la transacción a la que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="dba75-108">Data will be delivered to BAM only if the owning transaction commits.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dba75-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dba75-109">In This Section</span></span>  
  
-   [<span data-ttu-id="dba75-110">Cómo configurar una aplicación de Workflow Foundation de intercepción</span><span class="sxs-lookup"><span data-stu-id="dba75-110">How to Configure a Workflow Foundation Application for Interception</span></span>](../core/how-to-configure-a-workflow-foundation-application-for-interception.md)  
  
-   [<span data-ttu-id="dba75-111">Esquema de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="dba75-111">Windows Workflow Foundation Schema</span></span>](../core/windows-workflow-foundation-schema.md)  
  
-   [<span data-ttu-id="dba75-112">Patrones de filtro de evento comunes</span><span class="sxs-lookup"><span data-stu-id="dba75-112">Common Event Filter Patterns</span></span>](../core/common-event-filter-patterns.md)  
  
-   [<span data-ttu-id="dba75-113">Operaciones de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="dba75-113">Operations in Windows Workflow Foundation</span></span>](../core/operations-in-windows-workflow-foundation.md)