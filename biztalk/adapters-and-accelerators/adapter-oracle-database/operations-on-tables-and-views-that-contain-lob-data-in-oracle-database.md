---
title: Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data type
- binary file
- UpdateLOB
- ReadLOB
- LOB data types
- NCLOB
- large object
- binary large object
- CLOB
- national character large object
- BFILE
- BLOB
- character large object
ms.assetid: 25afd8c7-8ca3-4855-a231-2bec28c9a5cb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a35be7008c47e46ca65962d113c4604c1cfad42b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984301"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a><span data-ttu-id="afb47-102">Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="afb47-102">Operations on tables and views that contain LOB data in Oracle Database</span></span>
<span data-ttu-id="afb47-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona compatibilidad para los tipos de datos de objetos grandes (LOB) de Oracle:</span><span class="sxs-lookup"><span data-stu-id="afb47-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
- <span data-ttu-id="afb47-104">Objeto binario grande (BLOB)</span><span class="sxs-lookup"><span data-stu-id="afb47-104">Binary large object (BLOB)</span></span>  
  
- <span data-ttu-id="afb47-105">Objeto grande de caracteres (CLOB)</span><span class="sxs-lookup"><span data-stu-id="afb47-105">Character large object (CLOB)</span></span>  
  
- <span data-ttu-id="afb47-106">Objetos grandes de carácter nacional (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="afb47-106">National character large object (NCLOB)</span></span>  
  
- <span data-ttu-id="afb47-107">Archivo binario (BFILE).</span><span class="sxs-lookup"><span data-stu-id="afb47-107">Binary file (BFILE).</span></span> <span data-ttu-id="afb47-108">Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="afb47-108">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
  <span data-ttu-id="afb47-109">En la base de datos de Oracle, los tipos de datos LOB se usan para almacenar grandes cantidades de datos (hasta 4 GB).</span><span class="sxs-lookup"><span data-stu-id="afb47-109">On the Oracle database, LOB data types are used to store large amounts of data (up to 4 GB).</span></span> <span data-ttu-id="afb47-110">Tipos LOB admiten entrada y salida de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="afb47-110">LOB types support both input and output streaming.</span></span>  
  
  <span data-ttu-id="afb47-111">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] presenta las siguientes operaciones en tablas y vistas que contienen columnas LOB:</span><span class="sxs-lookup"><span data-stu-id="afb47-111">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the following operations for tables and views that contain LOB columns:</span></span>  
  
- <span data-ttu-id="afb47-112">**ReadLOB**.</span><span class="sxs-lookup"><span data-stu-id="afb47-112">**ReadLOB**.</span></span> <span data-ttu-id="afb47-113">La operación ReadLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB, NCLOB y BFILE.</span><span class="sxs-lookup"><span data-stu-id="afb47-113">The ReadLOB operation is surfaced for tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns.</span></span> <span data-ttu-id="afb47-114">Mediante el uso de la operación ReadLOB, los clientes del adaptador pueden leer valores de una columna LOB como un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="afb47-114">By using the ReadLOB operation, adapter clients can read values in a LOB column as a data stream.</span></span> <span data-ttu-id="afb47-115">Esta operación toma como parámetros el nombre de columna de tipo de datos LOB y una cadena de filtro.</span><span class="sxs-lookup"><span data-stu-id="afb47-115">This operation takes the LOB data type column name and a filter string as parameters.</span></span> <span data-ttu-id="afb47-116">Los clientes del adaptador deben asegurarse de que la cadena de filtro recopila exactamente una fila coincidente.</span><span class="sxs-lookup"><span data-stu-id="afb47-116">Adapter clients must ensure that the filter string fetches exactly one matching row.</span></span> <span data-ttu-id="afb47-117">Si hay más de una fila coincidente, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] solo devuelve la columna LOB para la primera fila (coincidencia).</span><span class="sxs-lookup"><span data-stu-id="afb47-117">If there is more than one matching row, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only returns the LOB column for the first (matching) row.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="afb47-118">La operación ReadLOB está diseñada para admitir la entrada de transmisión por secuencias de datos LOB en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="afb47-118">The ReadLOB operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="afb47-119">Debe usar una operación de selección de tabla para leer datos LOB de un modelo de canal de WCF o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="afb47-119">You should use a table Select operation to read LOB data from a WCF Channel Model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span> <span data-ttu-id="afb47-120">Para obtener más información sobre el streaming, consulte [compatibilidad con Streaming para tipos de datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="afb47-120">For more information about streaming, see [Streaming Support for LOB Data Types in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span></span>  
  
- <span data-ttu-id="afb47-121">**UpdateLOB**.</span><span class="sxs-lookup"><span data-stu-id="afb47-121">**UpdateLOB**.</span></span> <span data-ttu-id="afb47-122">La operación UpdateLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB y NCLOB.</span><span class="sxs-lookup"><span data-stu-id="afb47-122">The UpdateLOB operation is surfaced for tables and views that contain BLOB, CLOB, and NCLOB columns.</span></span> <span data-ttu-id="afb47-123">Mediante el uso de la operación UpdateLOB, los clientes del adaptador pueden actualizar valores en una columna LOB.</span><span class="sxs-lookup"><span data-stu-id="afb47-123">By using the UpdateLOB operation, adapter clients can update values in a LOB column.</span></span> <span data-ttu-id="afb47-124">Esta operación toma el nombre de columna de tipo de datos LOB, una cadena de filtro y datos como parámetros codificados de base64binary.</span><span class="sxs-lookup"><span data-stu-id="afb47-124">This operation takes the LOB data type column name, a filter string, and base64binary encoded data as parameters.</span></span> <span data-ttu-id="afb47-125">Los clientes del adaptador deben asegurarse de que la cadena de filtro recopila exactamente una fila coincidente; de lo contrario el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una XmlReaderParsingException.</span><span class="sxs-lookup"><span data-stu-id="afb47-125">Adapter clients must ensure that the filter string fetches exactly one matching row; otherwise the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws an XmlReaderParsingException.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="afb47-126">La operación UpdateLOB:</span><span class="sxs-lookup"><span data-stu-id="afb47-126">The UpdateLOB operation:</span></span>  
  > 
  > - <span data-ttu-id="afb47-127">No se admite para el tipo de datos BFILE.</span><span class="sxs-lookup"><span data-stu-id="afb47-127">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="afb47-128">Los clientes del adaptador o bien pueden usar la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="afb47-128">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="afb47-129">Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="afb47-129">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  >   -   <span data-ttu-id="afb47-130">Debe realizarse como parte de una transacción.</span><span class="sxs-lookup"><span data-stu-id="afb47-130">Must be performed as part of a transaction.</span></span> <span data-ttu-id="afb47-131">Para asegurarse de esto, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**.</span><span class="sxs-lookup"><span data-stu-id="afb47-131">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="afb47-132">Para obtener información sobre la **UseAmbientTransaction** enlaza la propiedad, vea [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="afb47-132">For information about the **UseAmbientTransaction** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afb47-133">ReadLOB y UpdateLOB operan en una sola columna LOB en una sola fila de tabla.</span><span class="sxs-lookup"><span data-stu-id="afb47-133">ReadLOB and UpdateLOB operate on a single LOB column in a single table row.</span></span> <span data-ttu-id="afb47-134">Para que funcione en las columnas LOB en varias filas o en varias columnas LOB de una sola fila, debe invocar ReadLOB o UpdateLOB para cada columna de destino dentro de cada fila de destino.</span><span class="sxs-lookup"><span data-stu-id="afb47-134">To operate on LOB columns in multiple rows or on multiple LOB columns within a single row, you must invoke ReadLOB or UpdateLOB for each target column within each target row.</span></span>  
  
 <span data-ttu-id="afb47-135">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="afb47-135">For more information about:</span></span>  
  
- <span data-ttu-id="afb47-136">Invocar la operación UpdateLOB en una tabla de base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [realizar operaciones en tablas con datos de tipos de objeto grande por mediante BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span><span class="sxs-lookup"><span data-stu-id="afb47-136">Invoking the UpdateLOB operation on an Oracle database table using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Performing Operations on Tables with Large Object Types Data by Using BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span></span> <span data-ttu-id="afb47-137">(Debe usar una operación de selección de tabla para leer los tipos de datos LOB en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="afb47-137">(You should use a table Select operation to read LOB data types in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
- <span data-ttu-id="afb47-138">Invocar operaciones ReadLOB y UpdateLOB en una tabla de base de datos de Oracle mediante el modelo de servicio WCF, vea [ejecutar operaciones en tablas con tipos de objeto grande mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="afb47-138">Invoking ReadLOB and UpdateLOB operations on an Oracle database table using WCF service model, see [Run Operations on Tables with Large Object Types by Using the WCF Service Model](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span></span>  
  
- <span data-ttu-id="afb47-139">Estructura de mensajes de acciones SOAP para realizar operaciones de ReadLOB y UpdateLOB, vea [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span><span class="sxs-lookup"><span data-stu-id="afb47-139">Message structure and SOAP actions for performing ReadLOB and UpdateLOB operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb47-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb47-140">See Also</span></span>  
 <span data-ttu-id="afb47-141">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="afb47-141">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>