---
title: Esquemas de mensajes de ExecuteNonQuery, ExecuteReader y ExecuteScalar Operations1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b42ed9075ad16708f835786fd1fd09b414d06ebb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="ee762-102">Esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="ee762-102">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="ee762-103">La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones de salida ExecuteNonQuery y ExecuteReader, ExecuteScalar en el nivel de raíz para ejecutar las instrucciones SQL arbitrarias o bloques de PL/SQL de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ee762-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the ExecuteNonQuery, ExecuteReader, and ExecuteScalar outbound operations at the root level to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="ee762-104">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="ee762-104">For more information about:</span></span>  
  
-   <span data-ttu-id="ee762-105">Estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ee762-105">These operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
-   <span data-ttu-id="ee762-106">Realizar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="ee762-106">Performing these operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="ee762-107">Estructura de los mensajes de ExecuteNonQuery, ExecuteReader y operaciones ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="ee762-107">Message Structure for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="ee762-108">Los mensajes en estas operaciones siguen un patrón de intercambio de mensajes de solicitud y respuesta, y en la tabla siguiente muestra la estructura de estos mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="ee762-108">The messages in these operations follow a request-response message exchange pattern, and the following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee762-109">Ver una descripción de la entidad después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ee762-109">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="ee762-110">Operación</span><span class="sxs-lookup"><span data-stu-id="ee762-110">Operation</span></span>|<span data-ttu-id="ee762-111">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="ee762-111">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee762-112">ExecuteNonQuery solicitud</span><span class="sxs-lookup"><span data-stu-id="ee762-112">ExecuteNonQuery Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|<span data-ttu-id="ee762-113">ExecuteNonQuery respuesta</span><span class="sxs-lookup"><span data-stu-id="ee762-113">ExecuteNonQuery Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|<span data-ttu-id="ee762-114">Solicitud de ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="ee762-114">ExecuteReader Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|<span data-ttu-id="ee762-115">Respuesta de ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="ee762-115">ExecuteReader Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|<span data-ttu-id="ee762-116">Solicitud de ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="ee762-116">ExecuteScalar Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|<span data-ttu-id="ee762-117">Respuesta de ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="ee762-117">ExecuteScalar Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 <span data-ttu-id="ee762-118">Descripciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="ee762-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="ee762-119">[Bloque PL/SQL] = todo el bloque de PL/SQL que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="ee762-119">[PL/SQL block] = The entire PL/SQL block to be executed.</span></span>  
  
 <span data-ttu-id="ee762-120">[stringvalue1] = un valor de la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="ee762-120">[stringvalue1] = A value in the array of strings.</span></span>  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="ee762-121">Acción de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="ee762-121">Message Action for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="ee762-122">La siguiente tabla muestra las acciones de mensaje que se utilizan en las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar.</span><span class="sxs-lookup"><span data-stu-id="ee762-122">The following table shows the message actions that are used by the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations.</span></span>  
  
|<span data-ttu-id="ee762-123">Operación</span><span class="sxs-lookup"><span data-stu-id="ee762-123">Operation</span></span>|<span data-ttu-id="ee762-124">Acción</span><span class="sxs-lookup"><span data-stu-id="ee762-124">Action</span></span>|  
|---------------|------------|  
|<span data-ttu-id="ee762-125">ExecuteNonQuery solicitud</span><span class="sxs-lookup"><span data-stu-id="ee762-125">ExecuteNonQuery Request</span></span>|<span data-ttu-id="ee762-126">GenericOp/ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="ee762-126">GenericOp/ExecuteNonQuery</span></span>|  
|<span data-ttu-id="ee762-127">ExecuteNonQuery respuesta</span><span class="sxs-lookup"><span data-stu-id="ee762-127">ExecuteNonQuery Response</span></span>|<span data-ttu-id="ee762-128">GenericOp/ExecuteNonQuery/respuesta</span><span class="sxs-lookup"><span data-stu-id="ee762-128">GenericOp/ExecuteNonQuery/response</span></span>|  
|<span data-ttu-id="ee762-129">Solicitud de ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="ee762-129">ExecuteReader Request</span></span>|<span data-ttu-id="ee762-130">GenericOp/ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="ee762-130">GenericOp/ExecuteReader</span></span>|  
|<span data-ttu-id="ee762-131">Respuesta de ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="ee762-131">ExecuteReader Response</span></span>|<span data-ttu-id="ee762-132">GenericOp/ExecuteReader/respuesta</span><span class="sxs-lookup"><span data-stu-id="ee762-132">GenericOp/ExecuteReader/response</span></span>|  
|<span data-ttu-id="ee762-133">Solicitud de ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="ee762-133">ExecuteScalar Request</span></span>|<span data-ttu-id="ee762-134">GenericOp/ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="ee762-134">GenericOp/ExecuteScalar</span></span>|  
|<span data-ttu-id="ee762-135">Respuesta de ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="ee762-135">ExecuteScalar Response</span></span>|<span data-ttu-id="ee762-136">GenericOp/ExecuteScalar/respuesta</span><span class="sxs-lookup"><span data-stu-id="ee762-136">GenericOp/ExecuteScalar/response</span></span>|