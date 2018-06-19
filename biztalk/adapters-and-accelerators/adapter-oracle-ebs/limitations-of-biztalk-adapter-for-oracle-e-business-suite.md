---
title: Limitaciones del adaptador de BizTalk para Oracle E-Business Suite | Documentos de Microsoft
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
ms.openlocfilehash: e7611c56fbd24c7c7cf09d38d376df585b72b284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216276"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="3b4c4-102">Limitaciones del adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="3b4c4-102">Limitations of BizTalk Adapter for Oracle E-Business Suite</span></span>
## <a name="general-limitations"></a><span data-ttu-id="3b4c4-103">Limitaciones generales</span><span class="sxs-lookup"><span data-stu-id="3b4c4-103">General Limitations</span></span>  
 <span data-ttu-id="3b4c4-104">Los siguientes son limitaciones para conocidas [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3b4c4-104">The following are known limitations for [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
-   <span data-ttu-id="3b4c4-105">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no es compatible con puerta de enlace de XML, la cola de mensajes avanzada y eventos empresariales.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Gateway, Advanced Queuing, and Business Events.</span></span>  
  
     <span data-ttu-id="3b4c4-106">Sin embargo, puede sortear la limitación de eventos empresariales de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b4c4-106">However, you can get around the Business Events limitation in the following way:</span></span>  
  
    1.  <span data-ttu-id="3b4c4-107">En el sistema de eventos de negocio de Oracle, cree una suscripción para invocar un procedimiento de PL/SQL personalizado cuando se produce un evento de negocio.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-107">In Oracle Business Events System, create a subscription to invoke a custom PL/SQL procedure when a business event occurs.</span></span>  
  
    2.  <span data-ttu-id="3b4c4-108">Escribir un procedimiento personalizado de PL/SQL que recibe el evento de negocio.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-108">Write a custom PL/SQL procedure that receives the business event.</span></span>  
  
    3.  <span data-ttu-id="3b4c4-109">Utilice el procedimiento personalizado de PL/SQL para almacenar los datos resultantes (evento y carga del evento) en una tabla.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-109">Use the custom PL/SQL procedure to store the resultant data (event and event payload) in a table.</span></span>  
  
    4.  <span data-ttu-id="3b4c4-110">Use la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear y/o recibir notificaciones de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-110">Use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll or receive notifications from the table.</span></span>  
  
-   <span data-ttu-id="3b4c4-111">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite los tipos de XML.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Types.</span></span>  
  
-   <span data-ttu-id="3b4c4-112">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no permiten a los clientes establecer el valor del primer elemento en un VARRAY en NULL.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
-   <span data-ttu-id="3b4c4-113">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no no los registros de soporte técnico que contienen campos de tipo de tablas de PL/SQL del tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
-   <span data-ttu-id="3b4c4-114">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos definidos por el usuario (UDT) que se haya referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
-   <span data-ttu-id="3b4c4-115">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite el tipo de datos BFILE dentro de los tipos complejos (por ejemplo, registro tipo, tabla tipo, UDT y VARRAY).</span><span class="sxs-lookup"><span data-stu-id="3b4c4-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
-   <span data-ttu-id="3b4c4-116">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite UDT hasta dos niveles de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
-   <span data-ttu-id="3b4c4-117">Excepto para tablas de PL/SQL, la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que se definen dentro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-117">Except for PL/SQL tables, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
-   <span data-ttu-id="3b4c4-118">Al usar los adaptadores con BizTalk Server, si el puerto de envío de las credenciales de WCF-custom son incorrectas, no se procesan los mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-118">When using the adapters with BizTalk Server, if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="3b4c4-119">Después de especificar las credenciales correctas, el mensaje se envía a Oracle E-Business Suite y se recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-119">After you specify the correct credentials, the message is sent to Oracle E-Business Suite and a response is received.</span></span> <span data-ttu-id="3b4c4-120">Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-120">However, the response message is not available to the out port.</span></span> <span data-ttu-id="3b4c4-121">En estos escenarios, debe reiniciar la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-121">In such scenarios, you may need to restart the host instance.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="3b4c4-122">Limitaciones debido a ODP.NET</span><span class="sxs-lookup"><span data-stu-id="3b4c4-122">Limitations Due to ODP.NET</span></span>  
 <span data-ttu-id="3b4c4-123">Los siguientes son limitaciones para conocidas [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] debido a la limitación de ODP.NET:</span><span class="sxs-lookup"><span data-stu-id="3b4c4-123">The following are known limitations for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] due to the limitation of ODP.NET:</span></span>  
  
-   <span data-ttu-id="3b4c4-124">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tablas de PL/SQL que no están indizadas por un campo numérico.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-124">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
-   <span data-ttu-id="3b4c4-125">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite matrices asociativas que no contiene ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-125">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
-   <span data-ttu-id="3b4c4-126">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que contienen el tipo de datos de marca de tiempo con atributos de zona horaria local (TimeStampLTZ).</span><span class="sxs-lookup"><span data-stu-id="3b4c4-126">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
-   <span data-ttu-id="3b4c4-127">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que contengan un "."</span><span class="sxs-lookup"><span data-stu-id="3b4c4-127">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="3b4c4-128">(punto) en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-128">(period) in their names.</span></span>  
  
-   <span data-ttu-id="3b4c4-129">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que contienen tipos de datos BLOB, CLOB y NCLOB como un parámetro IN OUT.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
-   <span data-ttu-id="3b4c4-130">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite Varray de Varray de los siguientes tipos simples: BFILE, IntervalDS, IntervalYM, TimeStampLTZ y TimeStampTZ.</span><span class="sxs-lookup"><span data-stu-id="3b4c4-130">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
-   <span data-ttu-id="3b4c4-131">Debido a la limitación de las matrices asociativas, tablas de PL/SQL de registros que contienen cualquiera de los siguientes tipos de datos o tablas de PL/SQL no se admiten en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3b4c4-131">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
    -   <span data-ttu-id="3b4c4-132">BFILE</span><span class="sxs-lookup"><span data-stu-id="3b4c4-132">BFILE</span></span>  
  
    -   <span data-ttu-id="3b4c4-133">BLOB</span><span class="sxs-lookup"><span data-stu-id="3b4c4-133">BLOB</span></span>  
  
    -   <span data-ttu-id="3b4c4-134">CLOB</span><span class="sxs-lookup"><span data-stu-id="3b4c4-134">CLOB</span></span>  
  
    -   <span data-ttu-id="3b4c4-135">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="3b4c4-135">IntervalDS</span></span>  
  
    -   <span data-ttu-id="3b4c4-136">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="3b4c4-136">IntervalYM</span></span>  
  
    -   <span data-ttu-id="3b4c4-137">Long</span><span class="sxs-lookup"><span data-stu-id="3b4c4-137">Long</span></span>  
  
    -   <span data-ttu-id="3b4c4-138">NCLOB</span><span class="sxs-lookup"><span data-stu-id="3b4c4-138">NCLOB</span></span>  
  
    -   <span data-ttu-id="3b4c4-139">RowID</span><span class="sxs-lookup"><span data-stu-id="3b4c4-139">RowID</span></span>  
  
    -   <span data-ttu-id="3b4c4-140">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="3b4c4-140">TimeStamp</span></span>  
  
    -   <span data-ttu-id="3b4c4-141">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="3b4c4-141">TimeStampLTZ</span></span>  
  
    -   <span data-ttu-id="3b4c4-142">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="3b4c4-142">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4c4-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b4c4-143">See Also</span></span>  
 [<span data-ttu-id="3b4c4-144">Comprender el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="3b4c4-144">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)