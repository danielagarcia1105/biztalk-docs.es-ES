---
title: Problemas comunes con los interceptores de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32145e2-1367-4576-9103-86c9182c11a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e6217a96bfbbe0a9dfddef6e8cec5a82cb93254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004077"
---
# <a name="common-issues-with-the-bam-interceptors"></a><span data-ttu-id="3f87e-102">Problemas comunes de los interceptores de BAM</span><span class="sxs-lookup"><span data-stu-id="3f87e-102">Common Issues with the BAM Interceptors</span></span>
<span data-ttu-id="3f87e-103">En este tema se explican los siguientes problemas comunes que pueden surgir al usar interceptores de BAM:</span><span class="sxs-lookup"><span data-stu-id="3f87e-103">This topic discusses the following common problems that can arise when using BAM interceptors:</span></span>  
  
-   <span data-ttu-id="3f87e-104">Excepción de SQL relacionada con una transacción distribuida</span><span class="sxs-lookup"><span data-stu-id="3f87e-104">SQL Exception relating to a distributed transaction</span></span>  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a><span data-ttu-id="3f87e-105">Se recibe una excepción de SQL relacionada con una transacción distribuida completada o con un descriptor de la transacción</span><span class="sxs-lookup"><span data-stu-id="3f87e-105">You Receive a SQL Exception Concerning a Completed Distributed Transaction or a Transaction Descriptor</span></span>  
 <span data-ttu-id="3f87e-106">Al ejecutar el interceptor de Windows Communication Framework (WCF) de BAM, se puede ver alguna de las excepciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f87e-106">You may see one of the following exceptions when running the BAM Windows Communication Framework (WCF) interceptor:</span></span>  
  
- <span data-ttu-id="3f87e-107">Se completó la transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="3f87e-107">Distributed transaction completed.</span></span> <span data-ttu-id="3f87e-108">Dé de alta esta sesión en una nueva transacción o en la transacción NULL.</span><span class="sxs-lookup"><span data-stu-id="3f87e-108">Either enlist this session in a new transaction or the NULL transaction.</span></span>  
  
- <span data-ttu-id="3f87e-109">No se permite el inicio de la nueva solicitud porque debe llegar con un descriptor válido de la transacción.</span><span class="sxs-lookup"><span data-stu-id="3f87e-109">New request is not allowed to start because it should come with a valid transaction descriptor.</span></span>  
  
  <span data-ttu-id="3f87e-110">Algunas sugerencias para solucionar este problema son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f87e-110">Some suggestions for troubleshooting this problem are:</span></span>  
  
- <span data-ttu-id="3f87e-111">Habilitar el seguimiento de BAM.</span><span class="sxs-lookup"><span data-stu-id="3f87e-111">Enable BAM tracing.</span></span> <span data-ttu-id="3f87e-112">Este seguimiento incluirá todos los mensajes relevantes, incluida la causa raíz del error.</span><span class="sxs-lookup"><span data-stu-id="3f87e-112">This trace will include all relevant messages including the root cause of the error.</span></span> <span data-ttu-id="3f87e-113">Para obtener más información acerca del seguimiento de BAM, consulte [cómo habilitar el seguimiento en BAM](../core/how-to-enable-tracing-in-bam.md).</span><span class="sxs-lookup"><span data-stu-id="3f87e-113">For more information about BAM tracing, see [How to Enable Tracing in BAM](../core/how-to-enable-tracing-in-bam.md).</span></span>  
  
- <span data-ttu-id="3f87e-114">Al ver la excepción del coordinador de transacciones distribuidas (DTC), intentar volver a ejecutar exactamente el mismo escenario sin transacciones.</span><span class="sxs-lookup"><span data-stu-id="3f87e-114">When you see this distributed transaction coordinator (DTC) exception, try to rerun exactly the same scenario without transactions.</span></span>  
  
- <span data-ttu-id="3f87e-115">Usar el Analizador de SQL Server y buscar errores en el seguimiento que originen la anulación de la transacción.</span><span class="sxs-lookup"><span data-stu-id="3f87e-115">Use SQL Server Profiler and look for errors in the trace that will cause the transaction to be aborted.</span></span>  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a><span data-ttu-id="3f87e-116">Se recibe un error parecido a "El intervalo de sondeo '0' de la configuración del interceptor debe ser de '5' segundos" al usar el interceptor de WCF</span><span class="sxs-lookup"><span data-stu-id="3f87e-116">You receive an error similar to "interceptor configuration polling interval '0' must be at least '5' seconds" when using the WCF Interceptor</span></span>  
 <span data-ttu-id="3f87e-117">Este error puede aparecer si no se proporciona de forma explícita un valor de intervalo de la configuración del interceptor en el archivo de configuración de la aplicación, o si se especifica un valor pero es inferior a 5 segundos, que es el valor mínimo necesario.</span><span class="sxs-lookup"><span data-stu-id="3f87e-117">You may encounter this error when you do not explicitly provide an interceptor configuration polling interval value in the application configuration file, or when you provide a value but it is less than 5 seconds, the required minimum.</span></span>  
  
 <span data-ttu-id="3f87e-118">Para solucionar el problema, se debe especificar un valor válido para PollingIntervalSec como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3f87e-118">To fix the problem, provide a valid value for PollingIntervalSec as shown:</span></span>  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f87e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f87e-119">See Also</span></span>  
 [<span data-ttu-id="3f87e-120">Solución de problemas de interceptores de BAM</span><span class="sxs-lookup"><span data-stu-id="3f87e-120">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)