---
title: Los esquemas de mensajes para el ExecuteNonQuery, ExecuteReader y ExecuteScalar Operations1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7078fed7a007eca4dfb3eb5608eb6e688bb74a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011973"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="5adfd-102">Esquemas de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones</span><span class="sxs-lookup"><span data-stu-id="5adfd-102">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="5adfd-103">La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar de salida en el nivel raíz para ejecutar bloques de PL/SQL ni instrucciones SQL arbitrarias en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="5adfd-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the ExecuteNonQuery, ExecuteReader, and ExecuteScalar outbound operations at the root level to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="5adfd-104">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="5adfd-104">For more information about:</span></span>  
  
- <span data-ttu-id="5adfd-105">Estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5adfd-105">These operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
- <span data-ttu-id="5adfd-106">Realizar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="5adfd-106">Performing these operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="5adfd-107">Estructura de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones</span><span class="sxs-lookup"><span data-stu-id="5adfd-107">Message Structure for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="5adfd-108">Los mensajes en estas operaciones siguen un patrón de intercambio de mensajes de solicitud y respuesta, y en la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="5adfd-108">The messages in these operations follow a request-response message exchange pattern, and the following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5adfd-109">Después de la tabla, vea las descripciones de entidad.</span><span class="sxs-lookup"><span data-stu-id="5adfd-109">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="5adfd-110">Operación</span><span class="sxs-lookup"><span data-stu-id="5adfd-110">Operation</span></span>|<span data-ttu-id="5adfd-111">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="5adfd-111">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5adfd-112">Solicitud ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="5adfd-112">ExecuteNonQuery Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|<span data-ttu-id="5adfd-113">Respuesta ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="5adfd-113">ExecuteNonQuery Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|<span data-ttu-id="5adfd-114">Solicitud ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="5adfd-114">ExecuteReader Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|<span data-ttu-id="5adfd-115">Respuesta ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="5adfd-115">ExecuteReader Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|<span data-ttu-id="5adfd-116">Solicitud ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="5adfd-116">ExecuteScalar Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|<span data-ttu-id="5adfd-117">Respuesta ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="5adfd-117">ExecuteScalar Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 <span data-ttu-id="5adfd-118">Descripciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="5adfd-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="5adfd-119">[Bloque PL/SQL] = todo el bloque de PL/SQL que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="5adfd-119">[PL/SQL block] = The entire PL/SQL block to be executed.</span></span>  
  
 <span data-ttu-id="5adfd-120">[stringvalue1] = un valor de la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="5adfd-120">[stringvalue1] = A value in the array of strings.</span></span>  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="5adfd-121">Acción de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones</span><span class="sxs-lookup"><span data-stu-id="5adfd-121">Message Action for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="5adfd-122">La siguiente tabla muestra las acciones de mensaje usados por las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar.</span><span class="sxs-lookup"><span data-stu-id="5adfd-122">The following table shows the message actions that are used by the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations.</span></span>  
  
|<span data-ttu-id="5adfd-123">Operación</span><span class="sxs-lookup"><span data-stu-id="5adfd-123">Operation</span></span>|<span data-ttu-id="5adfd-124">Acción</span><span class="sxs-lookup"><span data-stu-id="5adfd-124">Action</span></span>|  
|---------------|------------|  
|<span data-ttu-id="5adfd-125">Solicitud ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="5adfd-125">ExecuteNonQuery Request</span></span>|<span data-ttu-id="5adfd-126">GenericOp/ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="5adfd-126">GenericOp/ExecuteNonQuery</span></span>|  
|<span data-ttu-id="5adfd-127">Respuesta ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="5adfd-127">ExecuteNonQuery Response</span></span>|<span data-ttu-id="5adfd-128">GenericOp/ExecuteNonQuery/respuesta</span><span class="sxs-lookup"><span data-stu-id="5adfd-128">GenericOp/ExecuteNonQuery/response</span></span>|  
|<span data-ttu-id="5adfd-129">Solicitud ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="5adfd-129">ExecuteReader Request</span></span>|<span data-ttu-id="5adfd-130">GenericOp/ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="5adfd-130">GenericOp/ExecuteReader</span></span>|  
|<span data-ttu-id="5adfd-131">Respuesta ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="5adfd-131">ExecuteReader Response</span></span>|<span data-ttu-id="5adfd-132">GenericOp/ExecuteReader/respuesta</span><span class="sxs-lookup"><span data-stu-id="5adfd-132">GenericOp/ExecuteReader/response</span></span>|  
|<span data-ttu-id="5adfd-133">Solicitud ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="5adfd-133">ExecuteScalar Request</span></span>|<span data-ttu-id="5adfd-134">GenericOp/ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="5adfd-134">GenericOp/ExecuteScalar</span></span>|  
|<span data-ttu-id="5adfd-135">Respuesta ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="5adfd-135">ExecuteScalar Response</span></span>|<span data-ttu-id="5adfd-136">GenericOp/ExecuteScalar/respuesta</span><span class="sxs-lookup"><span data-stu-id="5adfd-136">GenericOp/ExecuteScalar/response</span></span>|