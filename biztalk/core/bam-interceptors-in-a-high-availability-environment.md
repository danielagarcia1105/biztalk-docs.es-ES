---
title: Los interceptores de BAM en un entorno de alta disponibilidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 555c8200-949f-4c7d-8041-5ba4b6cbaed5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a697eb2a1a27ceeec1538ad8d46127413e7ed1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230740"
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a><span data-ttu-id="65d85-102">Interceptores de BAM en un entorno de alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="65d85-102">BAM Interceptors in a High Availability Environment</span></span>
<span data-ttu-id="65d85-103">En este tema se describen los procesos de conmutación por error para el interceptor de WF de BAM y el interceptor de WCF de BAM en un entorno de alta disponibilidad durante una conmutación por error de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65d85-103">This topic describes the failover processes for the BAM WF interceptor and the BAM WCF interceptor in a high availability environment during a SQL Server failover.</span></span>  
  
## <a name="bam-wf-interceptor"></a><span data-ttu-id="65d85-104">Interceptor de WF de BAM</span><span class="sxs-lookup"><span data-stu-id="65d85-104">BAM WF Interceptor</span></span>  
 <span data-ttu-id="65d85-105">Si se trabaja en un entorno de alta disponibilidad, el interceptor de WF de BAM volverá a intentar la recuperación del archivo de configuración del interceptor cuando haya un problema de conexión con SQL Server durante una conmutación por error de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65d85-105">When operating in a high availability environment, the BAM WF interceptor will retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="65d85-106">Sin embargo, el interceptor no realizará ningún reintento al escribir los datos en la base de datos de importación principal de BAM cuando una conmutación por error de SQL Server esté en proceso.</span><span class="sxs-lookup"><span data-stu-id="65d85-106">However, the interceptor will not retry when writing data to the BAM Primary Import database when a SQL Server failover is in process.</span></span> <span data-ttu-id="65d85-107">Esto es porque el interceptor se basa en el comportamiento de la **WorkflowCommitBatchService** clase al escribir datos en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="65d85-107">This is because the interceptor relies on the behavior of the **WorkflowCommitBatchService** class when writing data to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="65d85-108">En el ejemplo siguiente, **DefaultWorkflowCommitWorkBatchService** se agrega como un servicio de tiempo de ejecución con enableRetries = "true" para que el lote vuelve a intentar tal y como se muestra en un fragmento de código de un archivo App.config:</span><span class="sxs-lookup"><span data-stu-id="65d85-108">In the following example, **DefaultWorkflowCommitWorkBatchService** is added as a run-time service with enableRetries="true" so that it retries the batch as shown in a snippet from an App.config file:</span></span>  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 <span data-ttu-id="65d85-109">Sin embargo, si existen transacciones de ambiente cuando la **CommitWorkBatch** se llama al método, la instancia de flujo de trabajo se finaliza de forma inmediata cuando una conexión de SQL Server no está disponible.</span><span class="sxs-lookup"><span data-stu-id="65d85-109">However, if there are existing ambient transactions when the **CommitWorkBatch** method is called, the workflow instance is terminated immediately when a SQL Server connection is not available.</span></span>  
  
 <span data-ttu-id="65d85-110">Para obtener más información sobre el comportamiento de la **WorkflowCommitBatchService** de clases en un entorno de alta disponibilidad, vea la sección "Reliability and High Availability" en "Introducción a Hosting Windows Workflow Foundation" en [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).</span><span class="sxs-lookup"><span data-stu-id="65d85-110">For more information about the behavior of the **WorkflowCommitBatchService** class in a high availability environment, see the "Reliability and High Availability" section in "Introduction to Hosting Windows Workflow Foundation" at [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).</span></span>  
  
## <a name="bam-wcf-interceptor"></a><span data-ttu-id="65d85-111">Interceptor de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="65d85-111">BAM WCF Interceptor</span></span>  
 <span data-ttu-id="65d85-112">En un entorno de alta disponibilidad, el interceptor de WCF de BAM no vuelve a intentar la recuperación del archivo de configuración del interceptor cuando haya un problema de conexión con SQL Server durante una conmutación por error de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65d85-112">In a high availability environment, the BAM WCF interceptor does not retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="65d85-113">Por tanto, debe personalizar el código WCF para compensar la conmutación por error o usar mensajería confiable para reenviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="65d85-113">You should therefore customize the WCF code to compensate for failure or use reliable messaging to resubmit messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d85-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="65d85-114">See Also</span></span>  
 [<span data-ttu-id="65d85-115">Interceptor de WF de BAM</span><span class="sxs-lookup"><span data-stu-id="65d85-115">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)