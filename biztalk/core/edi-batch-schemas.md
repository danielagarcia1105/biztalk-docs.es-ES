---
title: Esquemas EDI por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a25391fbc42b8e368a44f652ae691ff8bc2722dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999229"
---
# <a name="edi-batch-schemas"></a><span data-ttu-id="60cb9-102">Esquemas por lotes de EDI</span><span class="sxs-lookup"><span data-stu-id="60cb9-102">EDI Batch Schemas</span></span>
<span data-ttu-id="60cb9-103">Cuando BizTalk Server procesa un intercambio conservado, usa al menos tres esquemas:</span><span class="sxs-lookup"><span data-stu-id="60cb9-103">When BizTalk Server processes a preserved interchange, it uses at least three schemas:</span></span>  

- <span data-ttu-id="60cb9-104">Los esquemas por lotes (esquemas XML de intercambio), para validar el nodo raíz del intercambio por lotes conservado (X12_BatchSchema o Edifact_BatchSchema implementados en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="60cb9-104">The batch schemas (Interchange XML schemas) to validate the root node of the preserved batched interchange (X12_BatchSchema or Edifact_BatchSchema deployed in BaseArtifacts.dll)</span></span>  

- <span data-ttu-id="60cb9-105">Los esquemas de servicio de sobres, para validar los finalizadores y los encabezados de conjuntos de transacciones, grupos e intercambios (X12ServiceSchema o EdifactServiceSchema implementados en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="60cb9-105">The envelope service schemas to validate the interchange, gorup, and transaction set headers and trailers (X12ServiceSchema or EdifactServiceSchema deployed in BaseArtifacts.dll).</span></span> <span data-ttu-id="60cb9-106">Para obtener más información, consulte [esquemas de Control y servicio EDI](../core/edi-service-and-control-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="60cb9-106">For more information, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  

- <span data-ttu-id="60cb9-107">Esquemas de documentos, para cada tipo de documento del intercambio por lotes (implementados en su proyecto).</span><span class="sxs-lookup"><span data-stu-id="60cb9-107">Document schemas for each document type in the batched interchange (deployed in your project).</span></span> <span data-ttu-id="60cb9-108">Para obtener más información, consulte [esquemas de documentos EDI](../core/edi-document-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="60cb9-108">For more information, see [EDI Document Schemas](../core/edi-document-schemas.md).</span></span>  

  <span data-ttu-id="60cb9-109">Los esquemas por lotes se usan en tiempo de ejecución para validar los intercambios por lotes de entrada y de salida que se están conservando.</span><span class="sxs-lookup"><span data-stu-id="60cb9-109">Batch schemas are used at runtime to validate inbound and outbound batched interchanges that are being preserved.</span></span> <span data-ttu-id="60cb9-110">Los esquemas por lotes también se usan en tiempo de diseño para validar y generar instancias de mensajes.</span><span class="sxs-lookup"><span data-stu-id="60cb9-110">Batch schemas are also used at design time to validate and generate message instances.</span></span>  

## <a name="batch-schemas-used-at-runtime"></a><span data-ttu-id="60cb9-111">Esquemas por lotes usados en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="60cb9-111">Batch Schemas Used at Runtime</span></span>  
 <span data-ttu-id="60cb9-112">Existen dos versiones canónicas de los esquemas por lotes: X12_BatchSchema.xsd para X12 codificación y EDIFACT_BatchSchema.xsd para la codificación EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="60cb9-112">Two canonical versions of the batch schemas exist: X12_BatchSchema.xsd for X12 encoding and EDIFACT_BatchSchema.xsd for EDIFACT encoding.</span></span> <span data-ttu-id="60cb9-113">Estos esquemas son plantillas que incluyen el segmento de control.</span><span class="sxs-lookup"><span data-stu-id="60cb9-113">These schemas are templates that include the control segment.</span></span> <span data-ttu-id="60cb9-114">Estos esquemas tienen los siguientes nombres de raíz y espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="60cb9-114">These schemas have the following root names and namespaces:</span></span>  


|       <span data-ttu-id="60cb9-115">esquema</span><span class="sxs-lookup"><span data-stu-id="60cb9-115">Schema</span></span>        |       <span data-ttu-id="60cb9-116">Nodo raíz</span><span class="sxs-lookup"><span data-stu-id="60cb9-116">Root Node</span></span>       |                    <span data-ttu-id="60cb9-117">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="60cb9-117">Namespace</span></span>                     |
|---------------------|-----------------------|--------------------------------------------------|
|   <span data-ttu-id="60cb9-118">X12_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="60cb9-118">X12_BatchSchema</span></span>   |   <span data-ttu-id="60cb9-119">X12InterchangeXML</span><span class="sxs-lookup"><span data-stu-id="60cb9-119">X12InterchangeXML</span></span>   | http://schemas.microsoft.com/Edi/X12_BatchSchema |
| <span data-ttu-id="60cb9-120">Edifact_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="60cb9-120">Edifact_BatchSchema</span></span> | <span data-ttu-id="60cb9-121">EdifactInterchangeXML</span><span class="sxs-lookup"><span data-stu-id="60cb9-121">EdifactInterchangeXML</span></span> |     http://schemas.microsoft.com/Edi/Edifact     |

 <span data-ttu-id="60cb9-122">El tipo de documento en la instancia XML generada por la canalización de recepción será una constante (\<Encoding\>_BatchSchema.xml) y hará referencia a este esquema canónico.</span><span class="sxs-lookup"><span data-stu-id="60cb9-122">The document type on the XML instance generated by the receive pipeline will be a constant (\<Encoding\>_BatchSchema.xml) and will reference this canonical schema.</span></span> <span data-ttu-id="60cb9-123">Puede usar esta instancia en una asignación de una orquestación; no obstante, antes de hacerlo, tiene que modificar el tipo de documento y el espacio de nombres para realizar la asignación al esquema real necesario.</span><span class="sxs-lookup"><span data-stu-id="60cb9-123">You can use this instance in a map in an orchestration; however, before doing so you have to change the document type and namespace to map to the actual schema required.</span></span>  

 <span data-ttu-id="60cb9-124">No tiene que especificar el esquema por lotes en tiempo de diseño en el proceso, ya que éste se implementa en BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="60cb9-124">You do not need to specify the batch schema at design time in the project, because it is deployed in BaseArtifacts.dll.</span></span>  

## <a name="batch-schemas-in-the-schema-store"></a><span data-ttu-id="60cb9-125">Esquemas por lotes en el almacenamiento de esquema</span><span class="sxs-lookup"><span data-stu-id="60cb9-125">Batch Schemas in the Schema Store</span></span>  
 <span data-ttu-id="60cb9-126">Los esquemas por lotes que usa BizTalk Server en tiempo de ejecución para procesar lotes conservados se implementan en el ensamblado BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="60cb9-126">The batch schemas that BizTalk Server uses at runtime to process preserved batches are deployed in the BaseArtifacts.dll assembly.</span></span> <span data-ttu-id="60cb9-127">Éstos están disponibles de forma automática para el procesamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60cb9-127">These are automatically available for run-time processing.</span></span> <span data-ttu-id="60cb9-128">Edifact_BatchSchema y X12_BatchSchema también están disponibles en el almacén de esquemas de BizTalk en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span><span class="sxs-lookup"><span data-stu-id="60cb9-128">Edifact_BatchSchema and X12_BatchSchema are also available in the BizTalk schema store at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="60cb9-129">Estos esquemas se usan sólo en tiempo de diseño para validar o generar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="60cb9-129">Each of these schemas is only used at design time to validate or generate the interchange.</span></span> <span data-ttu-id="60cb9-130">No se necesita ningún esquema para la validación en la canalización de recepción o de envío en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60cb9-130">Neither schema is required for validation in the receive pipeline or send pipeline at runtime.</span></span>  

## <a name="see-also"></a><span data-ttu-id="60cb9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="60cb9-131">See Also</span></span>  
 <span data-ttu-id="60cb9-132">[Esquemas EDI](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="60cb9-132">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="60cb9-133">Procesamiento de lotes de entrada</span><span class="sxs-lookup"><span data-stu-id="60cb9-133">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)