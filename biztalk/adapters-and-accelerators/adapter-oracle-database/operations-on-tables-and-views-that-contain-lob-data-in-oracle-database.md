---
title: Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle | Documentos de Microsoft
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
ms.openlocfilehash: ba5e110af598ac75ca9a8b6e7ebf2e5e8acc7aee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214396"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a><span data-ttu-id="504c1-102">Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="504c1-102">Operations on tables and views that contain LOB data in Oracle Database</span></span>
<span data-ttu-id="504c1-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona compatibilidad para los tipos de datos de objetos grandes (LOB) de Oracle:</span><span class="sxs-lookup"><span data-stu-id="504c1-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
-   <span data-ttu-id="504c1-104">Objeto binario grande (BLOB)</span><span class="sxs-lookup"><span data-stu-id="504c1-104">Binary large object (BLOB)</span></span>  
  
-   <span data-ttu-id="504c1-105">Objeto grande de caracteres (CLOB)</span><span class="sxs-lookup"><span data-stu-id="504c1-105">Character large object (CLOB)</span></span>  
  
-   <span data-ttu-id="504c1-106">Objeto grande de caracteres nacional (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="504c1-106">National character large object (NCLOB)</span></span>  
  
-   <span data-ttu-id="504c1-107">Archivo binario (BFILE).</span><span class="sxs-lookup"><span data-stu-id="504c1-107">Binary file (BFILE).</span></span> <span data-ttu-id="504c1-108">Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="504c1-108">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
 <span data-ttu-id="504c1-109">En la base de datos de Oracle, los tipos de datos LOB se utilizan para almacenar grandes cantidades de datos (hasta 4 GB).</span><span class="sxs-lookup"><span data-stu-id="504c1-109">On the Oracle database, LOB data types are used to store large amounts of data (up to 4 GB).</span></span> <span data-ttu-id="504c1-110">Tipos LOB admiten entrada y salida de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="504c1-110">LOB types support both input and output streaming.</span></span>  
  
 <span data-ttu-id="504c1-111">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] presenta las siguientes operaciones para tablas y vistas que contienen columnas LOB:</span><span class="sxs-lookup"><span data-stu-id="504c1-111">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the following operations for tables and views that contain LOB columns:</span></span>  
  
-   <span data-ttu-id="504c1-112">**ReadLOB**.</span><span class="sxs-lookup"><span data-stu-id="504c1-112">**ReadLOB**.</span></span> <span data-ttu-id="504c1-113">La operación de ReadLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB, NCLOB y BFILE.</span><span class="sxs-lookup"><span data-stu-id="504c1-113">The ReadLOB operation is surfaced for tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns.</span></span> <span data-ttu-id="504c1-114">Mediante el uso de la operación de ReadLOB, los clientes de adaptador pueden leer valores de una columna LOB como un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="504c1-114">By using the ReadLOB operation, adapter clients can read values in a LOB column as a data stream.</span></span> <span data-ttu-id="504c1-115">Esta operación toma como parámetros el nombre de columna de tipo de datos LOB y una cadena de filtro.</span><span class="sxs-lookup"><span data-stu-id="504c1-115">This operation takes the LOB data type column name and a filter string as parameters.</span></span> <span data-ttu-id="504c1-116">Los clientes de adaptador deben asegurarse de que la cadena de filtro captura exactamente una fila coincidente.</span><span class="sxs-lookup"><span data-stu-id="504c1-116">Adapter clients must ensure that the filter string fetches exactly one matching row.</span></span> <span data-ttu-id="504c1-117">Si hay más de una fila coincidente, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] solo devuelve la columna LOB para la primera fila (coincidencia).</span><span class="sxs-lookup"><span data-stu-id="504c1-117">If there is more than one matching row, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only returns the LOB column for the first (matching) row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="504c1-118">La operación ReadLOB está diseñada para admitir la transmisión de entrada de datos LOB en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="504c1-118">The ReadLOB operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="504c1-119">Debe usar una operación de selección de tabla para leer datos LOB de un modelo de canales de WCF o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="504c1-119">You should use a table Select operation to read LOB data from a WCF Channel Model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span> <span data-ttu-id="504c1-120">Para obtener más información sobre el streaming, vea [compatibilidad con el Streaming de tipos de datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="504c1-120">For more information about streaming, see [Streaming Support for LOB Data Types in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="504c1-121">**UpdateLOB**.</span><span class="sxs-lookup"><span data-stu-id="504c1-121">**UpdateLOB**.</span></span> <span data-ttu-id="504c1-122">La operación de UpdateLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB y NCLOB.</span><span class="sxs-lookup"><span data-stu-id="504c1-122">The UpdateLOB operation is surfaced for tables and views that contain BLOB, CLOB, and NCLOB columns.</span></span> <span data-ttu-id="504c1-123">Mediante el uso de la operación de UpdateLOB, los clientes de adaptador pueden actualizar valores en una columna LOB.</span><span class="sxs-lookup"><span data-stu-id="504c1-123">By using the UpdateLOB operation, adapter clients can update values in a LOB column.</span></span> <span data-ttu-id="504c1-124">Esta operación toma el nombre de columna de tipo de datos LOB, una cadena de filtro, y datos como parámetros codificados de base64binary.</span><span class="sxs-lookup"><span data-stu-id="504c1-124">This operation takes the LOB data type column name, a filter string, and base64binary encoded data as parameters.</span></span> <span data-ttu-id="504c1-125">Los clientes de adaptador deben asegurarse de que la cadena de filtro captura exactamente una fila coincidente; de lo contrario el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una XmlReaderParsingException.</span><span class="sxs-lookup"><span data-stu-id="504c1-125">Adapter clients must ensure that the filter string fetches exactly one matching row; otherwise the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws an XmlReaderParsingException.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="504c1-126">La operación UpdateLOB:</span><span class="sxs-lookup"><span data-stu-id="504c1-126">The UpdateLOB operation:</span></span>  
    >   
    >  -   <span data-ttu-id="504c1-127">No se admite para el tipo de datos BFILE.</span><span class="sxs-lookup"><span data-stu-id="504c1-127">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="504c1-128">Los clientes de adaptador o bien pueden usar la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="504c1-128">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="504c1-129">Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="504c1-129">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
    > -   <span data-ttu-id="504c1-130">Debe realizarse como parte de una transacción.</span><span class="sxs-lookup"><span data-stu-id="504c1-130">Must be performed as part of a transaction.</span></span> <span data-ttu-id="504c1-131">Para asegurarse de esto, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**.</span><span class="sxs-lookup"><span data-stu-id="504c1-131">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="504c1-132">Para obtener información sobre la **UseAmbientTransaction** enlace de propiedad, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="504c1-132">For information about the **UseAmbientTransaction** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="504c1-133">ReadLOB y UpdateLOB operan en una sola columna LOB en una sola fila de tabla.</span><span class="sxs-lookup"><span data-stu-id="504c1-133">ReadLOB and UpdateLOB operate on a single LOB column in a single table row.</span></span> <span data-ttu-id="504c1-134">Para que funcione en las columnas LOB en varias filas o en varias columnas LOB de una sola fila, debe invocar ReadLOB o UpdateLOB para cada columna de destino dentro de cada fila de destino.</span><span class="sxs-lookup"><span data-stu-id="504c1-134">To operate on LOB columns in multiple rows or on multiple LOB columns within a single row, you must invoke ReadLOB or UpdateLOB for each target column within each target row.</span></span>  
  
 <span data-ttu-id="504c1-135">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="504c1-135">For more information about:</span></span>  
  
-   <span data-ttu-id="504c1-136">Invocar la operación UpdateLOB en una tabla de base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [realizar operaciones en tablas con datos de tipos de objeto grandes por mediante BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span><span class="sxs-lookup"><span data-stu-id="504c1-136">Invoking the UpdateLOB operation on an Oracle database table using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Performing Operations on Tables with Large Object Types Data by Using BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span></span> <span data-ttu-id="504c1-137">(Debe utilizar una operación de selección de tabla para leer los tipos de datos LOB en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="504c1-137">(You should use a table Select operation to read LOB data types in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
-   <span data-ttu-id="504c1-138">Invocar operaciones ReadLOB y UpdateLOB en una tabla de base de datos de Oracle mediante el modelo de servicio WCF, vea [ejecutar operaciones en tablas con tipos de objeto grandes mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="504c1-138">Invoking ReadLOB and UpdateLOB operations on an Oracle database table using WCF service model, see [Run Operations on Tables with Large Object Types by Using the WCF Service Model](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span></span>  
  
-   <span data-ttu-id="504c1-139">Estructura y acciones SOAP para realizar operaciones de ReadLOB y UpdateLOB de mensajes, vea [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span><span class="sxs-lookup"><span data-stu-id="504c1-139">Message structure and SOAP actions for performing ReadLOB and UpdateLOB operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504c1-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="504c1-140">See Also</span></span>  
 <span data-ttu-id="504c1-141">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="504c1-141">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>