---
title: "Detalles de implementación del adaptador OPS | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3172759541f46ec6c3c8c2b3e684086747036f37
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="ops-adapter-implementation-details"></a><span data-ttu-id="8cadf-102">Detalles de implementación de adaptadores de OPS</span><span class="sxs-lookup"><span data-stu-id="8cadf-102">Ops Adapter Implementation Details</span></span>
<span data-ttu-id="8cadf-103">Puede que le resulte de utilidad conocer los siguientes aspectos del adaptador OPS al modificar el adaptador o configurarlo mediante programación.</span><span class="sxs-lookup"><span data-stu-id="8cadf-103">You may find it useful to understand the following aspects of the Ops adapter when modifying the adapter or configuring it programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cadf-104">El adaptador OPS se integra mediante el marco de trabajo de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="8cadf-104">The Ops Adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="8cadf-105">Para obtener información sobre la creación de adaptadores con el marco de trabajo, consulte [desarrollar adaptadores Custom](../core/developing-custom-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="8cadf-105">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="batch-processing"></a><span data-ttu-id="8cadf-106">Procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="8cadf-106">Batch Processing</span></span>  
 <span data-ttu-id="8cadf-107">El adaptador realiza el procesamiento de los mensajes uno por uno, para llevarlo a cabo de forma independiente, y las reversiones se llevan a cabo en un sólo pedido cada vez.</span><span class="sxs-lookup"><span data-stu-id="8cadf-107">The adapter processes one message at a time so that each message is processed separately, and rollback operations are done on only one order at a time.</span></span> <span data-ttu-id="8cadf-108">Pese a que el adaptador procese uno por uno los mensajes, lo hace mediante el procesamiento por lotes con un tamaño de lote de mensaje.</span><span class="sxs-lookup"><span data-stu-id="8cadf-108">Although the adapter processes one message at a time, it does so using batching with a batch size of one.</span></span> <span data-ttu-id="8cadf-109">Esto facilita la modificación del adaptador para controlar los mensajes de los lotes.</span><span class="sxs-lookup"><span data-stu-id="8cadf-109">This makes it easier to modify the adapter to handle messages in batches.</span></span>  
  
## <a name="transaction-handling"></a><span data-ttu-id="8cadf-110">Control de transacciones</span><span class="sxs-lookup"><span data-stu-id="8cadf-110">Transaction Handling</span></span>  
 <span data-ttu-id="8cadf-111">El adaptador utiliza los servicios de transacción proporcionados por Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions** instalaciones.</span><span class="sxs-lookup"><span data-stu-id="8cadf-111">The adapter uses the transaction facilities provided by the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]**System.Transactions** facilities.</span></span> <span data-ttu-id="8cadf-112">El adaptador crea un nuevo **CommittableTransaction** y se utiliza con un **TransactionScope**.</span><span class="sxs-lookup"><span data-stu-id="8cadf-112">The adapter creates a new **CommittableTransaction** and uses it with a **TransactionScope**.</span></span> <span data-ttu-id="8cadf-113">El adaptador llama el **inicializar** y **Execute** métodos dentro del contexto de esta transacción.</span><span class="sxs-lookup"><span data-stu-id="8cadf-113">The adapter calls the **Initialize** and **Execute** methods within the context of this transaction.</span></span> <span data-ttu-id="8cadf-114">Código del ensamblado llamado puede participar en la transacción mediante el uso de **Transaction.Current** método estático para obtener el contexto de transacción.</span><span class="sxs-lookup"><span data-stu-id="8cadf-114">Code in the called assembly can participate in the transaction by using **Transaction.Current** static method to get the transaction context.</span></span> <span data-ttu-id="8cadf-115">El controlador de errores de ejemplo no emplea este servicio.</span><span class="sxs-lookup"><span data-stu-id="8cadf-115">The sample error handler does not make use of this facility.</span></span> <span data-ttu-id="8cadf-116">Para obtener más información acerca de **System.Transactions**, vea "Namespace System.Transactions" en la versión de biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8cadf-116">For more information about **System.Transactions**, see "System.Transactions Namespace" in the .NET Framework Class Library version.</span></span>  
  
## <a name="handling-data-other-than-error-reports"></a><span data-ttu-id="8cadf-117">Controlar datos distintos de los informes de errores</span><span class="sxs-lookup"><span data-stu-id="8cadf-117">Handling Data Other Than Error Reports</span></span>  
 <span data-ttu-id="8cadf-118">En la solución, el adaptador controla los mensajes de informes de errores a partir de la nueva característica de informes de errores.</span><span class="sxs-lookup"><span data-stu-id="8cadf-118">In the solution, the adapter handles error report messages from the new error reporting feature.</span></span> <span data-ttu-id="8cadf-119">Sin embargo, dado que la **Execute** método toma una matriz de bytes como su único argumento, no hay nada que limite de forma específica lo que puede pasarse a la **Execute** método.</span><span class="sxs-lookup"><span data-stu-id="8cadf-119">However, because the **Execute** method takes a byte array as its only argument, there is nothing that specifically limits what can be passed to the **Execute** method.</span></span>  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a><span data-ttu-id="8cadf-120">Uso del adaptador al crear puertos mediante programación</span><span class="sxs-lookup"><span data-stu-id="8cadf-120">Using the Adapter When Creating Ports Programmatically</span></span>  
 <span data-ttu-id="8cadf-121">Puede especificar el adaptador cuando cree puertos a partir de código.</span><span class="sxs-lookup"><span data-stu-id="8cadf-121">You can specify the adapter when creating ports from code.</span></span> <span data-ttu-id="8cadf-122">La siguiente tabla recoge los nombres de las propiedades personalizadas, así como la forma en la que se corresponden con los nombres para mostrar.</span><span class="sxs-lookup"><span data-stu-id="8cadf-122">The following table shows the custom property names and how they correspond to the display names.</span></span>  
  
|<span data-ttu-id="8cadf-123">Nombre de propiedad personalizada de envío</span><span class="sxs-lookup"><span data-stu-id="8cadf-123">Send Custom Property Name</span></span>|<span data-ttu-id="8cadf-124">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="8cadf-124">Display Name</span></span>|  
|-------------------------------|------------------|  
|<span data-ttu-id="8cadf-125">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="8cadf-125">**DotNetAssemblyStrongName**</span></span>|<span data-ttu-id="8cadf-126">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="8cadf-126">**DotNetAssemblyStrongName**</span></span>|  
|<span data-ttu-id="8cadf-127">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="8cadf-127">**DotNetClassName**</span></span>|<span data-ttu-id="8cadf-128">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="8cadf-128">**DotNetClassName**</span></span>|  
|<span data-ttu-id="8cadf-129">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="8cadf-129">**InitializationData**</span></span>|<span data-ttu-id="8cadf-130">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="8cadf-130">**InitializationData**</span></span>|  
|<span data-ttu-id="8cadf-131">**Transportlocationuri se construye a**</span><span class="sxs-lookup"><span data-stu-id="8cadf-131">**TransportLocationUri**</span></span>|<span data-ttu-id="8cadf-132">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="8cadf-132">Not applicable.</span></span>|  
  
 <span data-ttu-id="8cadf-133">Todas las propiedades son valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="8cadf-133">All of the properties are string values.</span></span> <span data-ttu-id="8cadf-134">El valor de la propiedad TransportLocationUri se construye a partir del nombre de ensamblado y del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="8cadf-134">You construct the value of the TransportLocationUri property from the assembly name and the class name.</span></span> <span data-ttu-id="8cadf-135">El identificador URI tiene el valor OPS: / /\<DotNetAssemblyStrongName\>/\<DotNetClassName\> donde los marcadores de posición se reemplazan por los valores de la propiedad personalizada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8cadf-135">The URI has the value OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\> where the placeholders are replaced by the values of the corresponding custom property.</span></span>  
  
 <span data-ttu-id="8cadf-136">Para obtener información sobre la creación de puertos desde el código, vea [cómo crear ubicaciones de recepción de MSMQ y puertos de envío desde el código](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span><span class="sxs-lookup"><span data-stu-id="8cadf-136">For information about creating ports from code, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cadf-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cadf-137">See Also</span></span>  
 [<span data-ttu-id="8cadf-138">El adaptador de Ops</span><span class="sxs-lookup"><span data-stu-id="8cadf-138">The Ops Adapter</span></span>](../core/the-ops-adapter.md)