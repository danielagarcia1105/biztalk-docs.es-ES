---
title: Limitaciones del adaptador de BizTalk para Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de75a2955632f4f8e0daae2a2035e90f1f2fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988397"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="666b6-102">Limitaciones del adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="666b6-102">Limitations of BizTalk Adapter for Oracle E-Business Suite</span></span>
## <a name="general-limitations"></a><span data-ttu-id="666b6-103">Limitaciones generales</span><span class="sxs-lookup"><span data-stu-id="666b6-103">General Limitations</span></span>  
 <span data-ttu-id="666b6-104">Lo siguiente es limitaciones para conocidas [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="666b6-104">The following are known limitations for [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
- <span data-ttu-id="666b6-105">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite la puerta de enlace XML, cola de mensajes avanzada y eventos empresariales.</span><span class="sxs-lookup"><span data-stu-id="666b6-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Gateway, Advanced Queuing, and Business Events.</span></span>  
  
   <span data-ttu-id="666b6-106">Sin embargo, puede sortear la limitación de eventos de negocio de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="666b6-106">However, you can get around the Business Events limitation in the following way:</span></span>  
  
  1. <span data-ttu-id="666b6-107">En el sistema de eventos de negocio de Oracle, cree una suscripción para invocar un procedimiento de PL/SQL personalizado cuando se produce un evento de negocio.</span><span class="sxs-lookup"><span data-stu-id="666b6-107">In Oracle Business Events System, create a subscription to invoke a custom PL/SQL procedure when a business event occurs.</span></span>  
  
  2. <span data-ttu-id="666b6-108">Escribir un procedimiento personalizado de PL/SQL que recibe el evento de negocio.</span><span class="sxs-lookup"><span data-stu-id="666b6-108">Write a custom PL/SQL procedure that receives the business event.</span></span>  
  
  3. <span data-ttu-id="666b6-109">Utilice el procedimiento personalizado de PL/SQL para almacenar los datos resultantes (evento y carga del evento) en una tabla.</span><span class="sxs-lookup"><span data-stu-id="666b6-109">Use the custom PL/SQL procedure to store the resultant data (event and event payload) in a table.</span></span>  
  
  4. <span data-ttu-id="666b6-110">Use el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear o recibir notificaciones de la tabla.</span><span class="sxs-lookup"><span data-stu-id="666b6-110">Use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll or receive notifications from the table.</span></span>  
  
- <span data-ttu-id="666b6-111">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos de XML.</span><span class="sxs-lookup"><span data-stu-id="666b6-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Types.</span></span>  
  
- <span data-ttu-id="666b6-112">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no permiten a los clientes establecer el valor del primer elemento en un VARRAY en NULL.</span><span class="sxs-lookup"><span data-stu-id="666b6-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
- <span data-ttu-id="666b6-113">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no los registros de soporte técnico que contienen campos de tipo de tablas de PL/SQL del tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="666b6-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
- <span data-ttu-id="666b6-114">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos definidos por el usuario (UDT) que tienen referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="666b6-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
- <span data-ttu-id="666b6-115">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite el tipo de datos BFILE dentro de los tipos complejos (como registro tipo tabla tipo, UDT y VARRAY).</span><span class="sxs-lookup"><span data-stu-id="666b6-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
- <span data-ttu-id="666b6-116">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite hasta dos niveles de anidamiento de UDT.</span><span class="sxs-lookup"><span data-stu-id="666b6-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
- <span data-ttu-id="666b6-117">Excepto para las tablas de PL/SQL, la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite los UDT se definen dentro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="666b6-117">Except for PL/SQL tables, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
- <span data-ttu-id="666b6-118">Al usar los adaptadores con BizTalk Server, si el puerto de envío de las credenciales en personalizada de WCF son incorrectas, no se procesan los mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="666b6-118">When using the adapters with BizTalk Server, if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="666b6-119">Después de especificar las credenciales correctas, el mensaje se envía a Oracle E-Business Suite y se recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="666b6-119">After you specify the correct credentials, the message is sent to Oracle E-Business Suite and a response is received.</span></span> <span data-ttu-id="666b6-120">Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida.</span><span class="sxs-lookup"><span data-stu-id="666b6-120">However, the response message is not available to the out port.</span></span> <span data-ttu-id="666b6-121">En estos escenarios, debe reiniciar la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="666b6-121">In such scenarios, you may need to restart the host instance.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="666b6-122">Limitaciones debido a ODP.NET</span><span class="sxs-lookup"><span data-stu-id="666b6-122">Limitations Due to ODP.NET</span></span>  
 <span data-ttu-id="666b6-123">Lo siguiente es limitaciones para conocidas [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] debido a la limitación de ODP.NET:</span><span class="sxs-lookup"><span data-stu-id="666b6-123">The following are known limitations for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] due to the limitation of ODP.NET:</span></span>  
  
- <span data-ttu-id="666b6-124">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tablas de PL/SQL que no están indizadas por un campo numérico.</span><span class="sxs-lookup"><span data-stu-id="666b6-124">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
- <span data-ttu-id="666b6-125">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite matrices asociativas que no contienen ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="666b6-125">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
- <span data-ttu-id="666b6-126">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite los UDT que contienen el tipo de datos de marca de tiempo con atributos de zona horaria local (TimeStampLTZ).</span><span class="sxs-lookup"><span data-stu-id="666b6-126">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
- <span data-ttu-id="666b6-127">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite los UDT que contienen un "."</span><span class="sxs-lookup"><span data-stu-id="666b6-127">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="666b6-128">(punto) en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="666b6-128">(period) in their names.</span></span>  
  
- <span data-ttu-id="666b6-129">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite los UDT que contienen los tipos de datos BLOB, CLOB y NCLOB como un parámetro IN OUT.</span><span class="sxs-lookup"><span data-stu-id="666b6-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
- <span data-ttu-id="666b6-130">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite Varray de Varray de los siguientes tipos simples: BFILE, IntervalDS, IntervalYM, TimeStampLTZ y TimeStampTZ.</span><span class="sxs-lookup"><span data-stu-id="666b6-130">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
- <span data-ttu-id="666b6-131">Debido a la limitación de matrices asociativas, tablas de PL/SQL de registros que contienen cualquiera de los siguientes tipos de datos o tablas de PL/SQL no se admiten en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="666b6-131">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
  -   <span data-ttu-id="666b6-132">BFILE</span><span class="sxs-lookup"><span data-stu-id="666b6-132">BFILE</span></span>  
  
  -   <span data-ttu-id="666b6-133">BLOB</span><span class="sxs-lookup"><span data-stu-id="666b6-133">BLOB</span></span>  
  
  -   <span data-ttu-id="666b6-134">CLOB</span><span class="sxs-lookup"><span data-stu-id="666b6-134">CLOB</span></span>  
  
  -   <span data-ttu-id="666b6-135">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="666b6-135">IntervalDS</span></span>  
  
  -   <span data-ttu-id="666b6-136">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="666b6-136">IntervalYM</span></span>  
  
  -   <span data-ttu-id="666b6-137">Long</span><span class="sxs-lookup"><span data-stu-id="666b6-137">Long</span></span>  
  
  -   <span data-ttu-id="666b6-138">NCLOB</span><span class="sxs-lookup"><span data-stu-id="666b6-138">NCLOB</span></span>  
  
  -   <span data-ttu-id="666b6-139">RowID</span><span class="sxs-lookup"><span data-stu-id="666b6-139">RowID</span></span>  
  
  -   <span data-ttu-id="666b6-140">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="666b6-140">TimeStamp</span></span>  
  
  -   <span data-ttu-id="666b6-141">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="666b6-141">TimeStampLTZ</span></span>  
  
  -   <span data-ttu-id="666b6-142">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="666b6-142">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666b6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="666b6-143">See Also</span></span>  
 [<span data-ttu-id="666b6-144">El adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="666b6-144">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)