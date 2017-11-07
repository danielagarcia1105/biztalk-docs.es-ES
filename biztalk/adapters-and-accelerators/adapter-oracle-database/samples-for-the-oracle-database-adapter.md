---
title: Ejemplos de adaptadores de base de datos de Oracle | Documentos de Microsoft
description: Ejemplos de adaptadores de WCF de la base de datos de Oracle que pueden usarse con BizTalk Server, el modelo de servicio WCF y el modelo del canal WCF
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bfef9fcfce65d8aede1cd905a53469c565977f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a><span data-ttu-id="96496-103">Ejemplos para el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="96496-103">Samples for the Oracle Database adapter</span></span>
<span data-ttu-id="96496-104">Ejemplos de [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] se clasifican en categorías:</span><span class="sxs-lookup"><span data-stu-id="96496-104">Samples for [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] are categorized into:</span></span>  
  
-   <span data-ttu-id="96496-105">Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96496-105">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] samples</span></span>  
  
-   <span data-ttu-id="96496-106">Ejemplos de modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="96496-106">WCF service model samples</span></span>  
  
-   <span data-ttu-id="96496-107">Ejemplos de modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="96496-107">WCF channel model samples</span></span>  

  
<span data-ttu-id="96496-108">Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores de base de datos de Oracle](https://www.microsoft.com/download/details.aspx?id=4675).</span><span class="sxs-lookup"><span data-stu-id="96496-108">The samples are available at [BizTalk Adapter Pack 2010: Oracle Database adapter samples](https://www.microsoft.com/download/details.aspx?id=4675).</span></span> <span data-ttu-id="96496-109">Las secuencias de comandos SQL para crear las tablas y los paquetes utilizados en los ejemplos se incluyen.</span><span class="sxs-lookup"><span data-stu-id="96496-109">The SQL scripts for creating the tables and packages used in the samples are included.</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
<span data-ttu-id="96496-110">En la lista siguiente describe los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="96496-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="96496-111">Ejemplos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="96496-111">BizTalk Server samples</span></span>
  
|<span data-ttu-id="96496-112">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="96496-112">Sample Directory Name</span></span>|<span data-ttu-id="96496-113">Description</span><span class="sxs-lookup"><span data-stu-id="96496-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="96496-114">Func_RecordTypes</span><span class="sxs-lookup"><span data-stu-id="96496-114">Func_RecordTypes</span></span>|<span data-ttu-id="96496-115">Muestra cómo usar parámetros de tipo de registro y valores devueltos en funciones y procedimientos con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-115">Demonstrates how to use RECORD type parameters and return values in functions and procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-116">Func_RefCursor</span><span class="sxs-lookup"><span data-stu-id="96496-116">Func_RefCursor</span></span>|<span data-ttu-id="96496-117">Muestra cómo utilizar los parámetros REF CURSOR en funciones y procedimientos con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-117">Demonstrates how to use REF CURSOR parameters in functions and procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-118">InvokeFunction</span><span class="sxs-lookup"><span data-stu-id="96496-118">InvokeFunction</span></span>|<span data-ttu-id="96496-119">Muestra cómo invocar una función de base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-119">Demonstrates how to invoke a function in Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-120">InvokeOverloadedProc</span><span class="sxs-lookup"><span data-stu-id="96496-120">InvokeOverloadedProc</span></span>|<span data-ttu-id="96496-121">Muestra cómo invocar con las funciones sobrecargadas y los procedimientos de la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-121">Demonstrates how to invoke with overloaded functions and procedures in Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-122">Operate_BFILE</span><span class="sxs-lookup"><span data-stu-id="96496-122">Operate_BFILE</span></span>|<span data-ttu-id="96496-123">Muestra cómo utilizar tipos BFILE de Oracle en los procedimientos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-123">Demonstrates how to use Oracle BFILE types in Oracle procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-124">Operate_LOB</span><span class="sxs-lookup"><span data-stu-id="96496-124">Operate_LOB</span></span>|<span data-ttu-id="96496-125">Muestra cómo realizar operaciones de ReadLOB y UpdateLOB en tablas con tipos de datos LOB mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-125">Demonstrates how to perform ReadLOB and UpdateLOB operations on tables with LOB data types using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-126">PollingQuery</span><span class="sxs-lookup"><span data-stu-id="96496-126">PollingQuery</span></span>|<span data-ttu-id="96496-127">Muestra cómo configurar una consulta de sondeo y recibir los resultados utilizando la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-127">Demonstrates how to configure a polling query and receive the results using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-128">SelectAccTable</span><span class="sxs-lookup"><span data-stu-id="96496-128">SelectAccTable</span></span>|<span data-ttu-id="96496-129">Muestra cómo realizar una consulta select en una tabla de base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-129">Demonstrates how to perform a select query on an Oracle database table using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="96496-130">SqlExec</span><span class="sxs-lookup"><span data-stu-id="96496-130">SqlExec</span></span>|<span data-ttu-id="96496-131">Muestra cómo realizar consultas con parámetros mediante la operación SQLEXECUTE en una base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96496-131">Demonstrates how to perform parameterized queries using the SQLEXECUTE operation on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="96496-132">Ejemplos de modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="96496-132">WCF service model samples</span></span>  
  
|<span data-ttu-id="96496-133">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="96496-133">Sample Directory Name</span></span>|<span data-ttu-id="96496-134">Description</span><span class="sxs-lookup"><span data-stu-id="96496-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="96496-135">OracleBfileTypeSM</span><span class="sxs-lookup"><span data-stu-id="96496-135">OracleBfileTypeSM</span></span>|<span data-ttu-id="96496-136">Muestra cómo utilizar tipos BFILE de Oracle en las operaciones básicas de SQL que aparecen para las tablas de Oracle y como parámetros a procedimientos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="96496-136">Demonstrates how to use Oracle BFILE types in basic SQL operations surfaced for Oracle tables and as parameters to Oracle procedures.</span></span>|  
|<span data-ttu-id="96496-137">OracleOverloadsSM</span><span class="sxs-lookup"><span data-stu-id="96496-137">OracleOverloadsSM</span></span>|<span data-ttu-id="96496-138">Muestra cómo invocar las funciones sobrecargadas y los procedimientos de un paquete.</span><span class="sxs-lookup"><span data-stu-id="96496-138">Demonstrates how to invoke overloaded functions and procedures in a package.</span></span>|  
|<span data-ttu-id="96496-139">OraclePollingSM</span><span class="sxs-lookup"><span data-stu-id="96496-139">OraclePollingSM</span></span>|<span data-ttu-id="96496-140">Muestra cómo configurar una consulta de sondeo y recibir los resultados.</span><span class="sxs-lookup"><span data-stu-id="96496-140">Demonstrates how to configure a polling query and receive the results.</span></span>|  
|<span data-ttu-id="96496-141">OracleRecordTypesSM</span><span class="sxs-lookup"><span data-stu-id="96496-141">OracleRecordTypesSM</span></span>|<span data-ttu-id="96496-142">Muestra cómo usar parámetros de tipo de registro y valores devueltos en funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="96496-142">Demonstrates how to use RECORD type parameters and return values in functions and procedures.</span></span>|  
|<span data-ttu-id="96496-143">OracleRefCursorsSM</span><span class="sxs-lookup"><span data-stu-id="96496-143">OracleRefCursorsSM</span></span>|<span data-ttu-id="96496-144">Muestra cómo utilizar los parámetros REF CURSOR en funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="96496-144">Demonstrates how to use REF CURSOR parameters in functions and procedures</span></span>|  
|<span data-ttu-id="96496-145">OracleTransactedDmlSM</span><span class="sxs-lookup"><span data-stu-id="96496-145">OracleTransactedDmlSM</span></span>|<span data-ttu-id="96496-146">Muestra cómo realizar operaciones en la base de datos de Oracle en una transacción utilizando el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="96496-146">Demonstrates how to perform operations on the Oracle database in a transaction using the WCF service model.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="96496-147">Ejemplos de modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="96496-147">WCF channel model samples</span></span>  
  
|<span data-ttu-id="96496-148">Nombre del directorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="96496-148">Sample Directory Name</span></span>|<span data-ttu-id="96496-149">Description</span><span class="sxs-lookup"><span data-stu-id="96496-149">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="96496-150">OraclePollingCM</span><span class="sxs-lookup"><span data-stu-id="96496-150">OraclePollingCM</span></span>|<span data-ttu-id="96496-151">Muestra cómo configurar una consulta de sondeo y recibir los resultados.</span><span class="sxs-lookup"><span data-stu-id="96496-151">Demonstrates how to configure a polling query and receive the results.</span></span>|  
|<span data-ttu-id="96496-152">OracleStreamingDemo</span><span class="sxs-lookup"><span data-stu-id="96496-152">OracleStreamingDemo</span></span>|<span data-ttu-id="96496-153">Muestra cómo realizar-to-end de transmisión por secuencias de datos LOB mediante las operaciones Select UpdateLOB y tabla</span><span class="sxs-lookup"><span data-stu-id="96496-153">Demonstrates how to perform end-to-end streaming of LOB data using the UpdateLOB and table Select operations</span></span>|  
|<span data-ttu-id="96496-154">OracleTransactedDmlCM</span><span class="sxs-lookup"><span data-stu-id="96496-154">OracleTransactedDmlCM</span></span>|<span data-ttu-id="96496-155">Muestra cómo realizar operaciones en la base de datos de Oracle en una transacción mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="96496-155">Demonstrates how to perform operations on the Oracle database in a transaction using the WCF channel model.</span></span>|  
  

## <a name="see-also"></a><span data-ttu-id="96496-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="96496-156">See Also</span></span>  
[<span data-ttu-id="96496-157">Desarrollar aplicaciones de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="96496-157">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)