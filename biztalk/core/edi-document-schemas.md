---
title: Esquemas de documentos EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac5830f12351bd5441411fe54598e55894216fa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998629"
---
# <a name="edi-document-schemas"></a><span data-ttu-id="fbebc-102">Esquemas de documentos EDI</span><span class="sxs-lookup"><span data-stu-id="fbebc-102">EDI Document Schemas</span></span>
<span data-ttu-id="fbebc-103">Los esquemas de documento definen el cuerpo de un tipo de documento de transacción EDI.</span><span class="sxs-lookup"><span data-stu-id="fbebc-103">Document schemas define the body of an EDI transaction document type.</span></span>  
  
## <a name="schema-delivery-and-setup"></a><span data-ttu-id="fbebc-104">Entrega y configuración de esquemas</span><span class="sxs-lookup"><span data-stu-id="fbebc-104">Schema Delivery and Setup</span></span>  
 <span data-ttu-id="fbebc-105">Esquemas de documentos EDI se entregan en estado comprimido en un archivo ejecutable autoextraíble, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe.</span><span class="sxs-lookup"><span data-stu-id="fbebc-105">EDI document schemas are delivered in a compressed state in a self-extracting executable, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe.</span></span> <span data-ttu-id="fbebc-106">El archivo ejecutable autoextraíble garantiza que se ha creado una estructura de carpetas adecuada (según el tipo de codificación y los subtipos de versión y lanzamiento).</span><span class="sxs-lookup"><span data-stu-id="fbebc-106">The self-extracting executable ensures that an appropriate folder structure is created (per the encoding type and version/release sub types).</span></span> <span data-ttu-id="fbebc-107">Cuando se ejecuta, el ejecutable deposita esquemas EANCOM, EDIFACT, HIPAA y X12 en subcarpetas del mismo directorio que el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="fbebc-107">When executed, the executable deposits EANCOM, EDIFACT, HIPAA, and X12 schemas into subfolders in the same directory as the executable.</span></span>  
  
 <span data-ttu-id="fbebc-108">Los espacios de nombres de esquema predeterminados son:</span><span class="sxs-lookup"><span data-stu-id="fbebc-108">The default schema namespaces are:</span></span>  
  
-   <span data-ttu-id="fbebc-109">Para X12: `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span><span class="sxs-lookup"><span data-stu-id="fbebc-109">For X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span></span>  
  
-   <span data-ttu-id="fbebc-110">Para EDIFACT: `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span><span class="sxs-lookup"><span data-stu-id="fbebc-110">For EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span></span>  
  
## <a name="schema-naming-convention"></a><span data-ttu-id="fbebc-111">Convención de nomenclatura de esquemas</span><span class="sxs-lookup"><span data-stu-id="fbebc-111">Schema Naming Convention</span></span>  
 <span data-ttu-id="fbebc-112">Es la convención de nomenclatura para el X12 y tipo de codificación de EDIFACT \<Encoding\>*\<versión\>\<versión\> \\*  \<Doctype\>.</span><span class="sxs-lookup"><span data-stu-id="fbebc-112">The naming convention for the X12 and EDIFACT encoding type is \<Encoding\>*\<Version\>\<Release\>\\*\<Doctype\>.</span></span> <span data-ttu-id="fbebc-113">El esquema X12_00401_864.xsd es un ejemplo para el tipo de documento X12 864 (versión 004, lanzamiento 01) y el esquema EDIFACT_D01C_AUTHOR.xsd es un ejemplo del tipo de documento EDIFACT AUTHOR (versión D01, lanzamiento C).</span><span class="sxs-lookup"><span data-stu-id="fbebc-113">Examples are the X12_00401_864.xsd schema for the X12 864 document type (version 004, release 01) and the EDIFACT_D01C_AUTHOR.xsd schema for the EDIFACT AUTHOR document type (version D01, release C).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbebc-114">El nombre los esquemas EDIFACT distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fbebc-114">The schema name of an EDIFACT schema is case-sensitive.</span></span> <span data-ttu-id="fbebc-115">Por ejemplo, EFACT_D98B_ORDERS y EFACT_d98B_Orders serían dos esquemas diferentes.</span><span class="sxs-lookup"><span data-stu-id="fbebc-115">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="schema-contents"></a><span data-ttu-id="fbebc-116">Contenido de esquema</span><span class="sxs-lookup"><span data-stu-id="fbebc-116">Schema Contents</span></span>  
 <span data-ttu-id="fbebc-117">Un esquema de documento comienza con el encabezado de conjunto de transacciones ST y termina con el finalizador de conjunto de transacciones SE para un documento con codificación X12.</span><span class="sxs-lookup"><span data-stu-id="fbebc-117">A document schema starts with the ST transaction set header and ends with the SE transaction set trailer for an X12-encoded document.</span></span> <span data-ttu-id="fbebc-118">Comienza con el encabezado de mensaje UNH y termina con el finalizador de mensaje UNT para un documento con codificación EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="fbebc-118">It starts with the UNH message header and ends with the UNT message trailer for an EDIFACT-encoded document.</span></span> <span data-ttu-id="fbebc-119">El esquema define cada elemento de datos de estos encabezados y finalizadores.</span><span class="sxs-lookup"><span data-stu-id="fbebc-119">The schema defines each data element of these headers and trailers.</span></span>  
  
 <span data-ttu-id="fbebc-120">Después, un esquema de documento define cada segmento en el conjunto de transacciones/mensaje y los elementos de datos en esos segmentos.</span><span class="sxs-lookup"><span data-stu-id="fbebc-120">A document schema then defines each segment within the transaction set/message and the data elements within those segments.</span></span> <span data-ttu-id="fbebc-121">Por ejemplo, el esquema X12_00401_864.xsd define los elementos BMG01, BMG02 y BMG03 de los segmentos BMG.</span><span class="sxs-lookup"><span data-stu-id="fbebc-121">For example, the X12_00401_864.xsd schema defines the BMG01, BMG02, and BMG03 elements of the BMG segments.</span></span> <span data-ttu-id="fbebc-122">El esquema especifica las características del tipo de datos complejos del segmento, por ejemplo el orden de campos, el tipo de delimitador y el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="fbebc-122">The schema specifies the characteristics of the segment's complex data type, such as the field order, delimiter type, and namespace.</span></span> <span data-ttu-id="fbebc-123">Si hay reglas de validación de campos cruzados para el segmento, el esquema define las reglas.</span><span class="sxs-lookup"><span data-stu-id="fbebc-123">If there are cross-field validation rules for the segment, the schema defines the rules.</span></span> <span data-ttu-id="fbebc-124">Para obtener más información, consulte [validación cruzada de segmentos / campos](../core/cross-field-segment-validation.md).</span><span class="sxs-lookup"><span data-stu-id="fbebc-124">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
 <span data-ttu-id="fbebc-125">El esquema especifica las características de cada elemento de datos en el segmento, por ejemplo el tipo de datos simples, número mínimo de apariciones, longitud mínima y máxima.</span><span class="sxs-lookup"><span data-stu-id="fbebc-125">The schema specifies the characteristics of each data element within the segment, such as the simple data type, minimum occurrences, minimum length, and maximum length.</span></span>  
  
 <span data-ttu-id="fbebc-126">Si hay un bucle en el tipo de mensaje, el esquema define los elementos de datos en cada bucle, el número mínimo y máximo de apariciones y si el bucle está enlazado o no.</span><span class="sxs-lookup"><span data-stu-id="fbebc-126">If there is a loop in the message type, the schema defines the data elements within each loop, the minimum and maximum occurrences of the loop, and whether the loop is bounded or unbounded.</span></span> <span data-ttu-id="fbebc-127">El esquema también define el anidamiento de un mensaje y si el bucle es explícito o implícito.</span><span class="sxs-lookup"><span data-stu-id="fbebc-127">The schema also defines nesting of a segment, and whether the loop is explicit or implicit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbebc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbebc-128">See Also</span></span>  
 <span data-ttu-id="fbebc-129">[Estructura de los mensajes EDI](../core/edi-message-structure.md) </span><span class="sxs-lookup"><span data-stu-id="fbebc-129">[EDI Message Structure](../core/edi-message-structure.md) </span></span>  
 [<span data-ttu-id="fbebc-130">Validación de mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="fbebc-130">EDI Message Validation</span></span>](../core/edi-message-validation.md)