---
title: Crear esquemas de encabezado personalizado para la detección del tipo de mensaje dinámico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c87ba83961b9daac07028a994d7c01add0c11a73
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004333"
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a><span data-ttu-id="23a67-102">Crear esquemas de encabezado personalizado para la detección del tipo de mensaje dinámico</span><span class="sxs-lookup"><span data-stu-id="23a67-102">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>
<span data-ttu-id="23a67-103">En la mayoría de los escenarios, debe especificar el esquema de encabezado SWIFT predeterminado (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) para la propiedad de configuración de esquema de encabezado de SWIFT del desensamblador SWIFT.</span><span class="sxs-lookup"><span data-stu-id="23a67-103">In most scenarios, you should specify the default SWIFT header schema (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) for the SWIFT Header Schema configuration property of the SWIFT disassembler.</span></span> <span data-ttu-id="23a67-104">El Desensamblador SWIFT usa el esquema de encabezado SWIFT predeterminado para analizar los encabezados del mensaje que se ajustan a la especificación estándar de SWIFT, y se las necesarias las propiedades promocionadas para facilitar la resolución de esquema dinámico (y subtipo de "tipo dual" Los mensajes de SWIFT como MT574_IRSLST y MT574_W8BENO).</span><span class="sxs-lookup"><span data-stu-id="23a67-104">The SWIFT disassembler uses the default SWIFT header schema to parse message headers that conform to the SWIFT standard specification, and has the necessary promoted properties to facilitate dynamic schema resolution (and sub-type resolution for "dual type" SWIFT messages like MT574_IRSLST and MT574_W8BENO).</span></span> <span data-ttu-id="23a67-105">Para obtener más información sobre el esquema de encabezado SWIFT predeterminado y para comprender cómo el Desensamblador SWIFT realiza la resolución de esquemas, consulte [detección dinámica de tipo de mensaje y la resolución de esquema](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="23a67-105">For more information about the default SWIFT header schema and to understand how the SWIFT disassembler performs schema resolution, see [Dynamic Message Type Discovery and Schema Resolution](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).</span></span>  
  
 <span data-ttu-id="23a67-106">Para otros escenarios donde los mensajes contienen datos de encabezado de SWIFT no estándar, puede usar un esquema de encabezado personalizado para su análisis de encabezado y detección de tipo de mensaje dinámico.</span><span class="sxs-lookup"><span data-stu-id="23a67-106">For other scenarios where messages contain non-SWIFT standard header data, you can use a custom header schema for header parsing and dynamic message type discovery.</span></span> <span data-ttu-id="23a67-107">Para crear y utilizar un esquema de encabezado personalizado para la resolución de esquema dinámico, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23a67-107">To create and use a custom header schema for dynamic schema resolution, do the following:</span></span>  
  
1.  <span data-ttu-id="23a67-108">Crear un esquema personalizado que puede utilizar el Desensamblador SWIFT estructuralmente analizar el formato de datos de encabezado esperado.</span><span class="sxs-lookup"><span data-stu-id="23a67-108">Create a custom schema that the SWIFT disassembler can use to structurally parse the expected header data format.</span></span>  
  
2.  <span data-ttu-id="23a67-109">Identificar los campos en el esquema contendrán los valores que indica el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="23a67-109">Identify which fields in the schema will hold the value(s) indicating message type.</span></span>  
  
3.  <span data-ttu-id="23a67-110">Agregue el esquema de propiedades de A4SWIFT (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) a la "lista de esquemas de propiedad" del esquema de encabezado personalizado y promocionar los campos correspondientes que indican el tipo de mensaje con los siguientes [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] propiedades:</span><span class="sxs-lookup"><span data-stu-id="23a67-110">Add the A4SWIFT Property Schema (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) to the "Property schemas list" of the custom header schema and promote the appropriate fields that indicate message type using the following [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] properties:</span></span>  
  
    -   <span data-ttu-id="23a67-111">**A4SWIFT_MessageType**</span><span class="sxs-lookup"><span data-stu-id="23a67-111">**A4SWIFT_MessageType**</span></span>  
  
    -   <span data-ttu-id="23a67-112">**A4SWIFT_MessageType2** (opcional si **A4SWIFT_MessageTypes** se utiliza)</span><span class="sxs-lookup"><span data-stu-id="23a67-112">**A4SWIFT_MessageType2** (optional if **A4SWIFT_MessageTypes** is used)</span></span>  
  
    -   <span data-ttu-id="23a67-113">**A4SWIFT_SecondaryMessageType** (opcional)</span><span class="sxs-lookup"><span data-stu-id="23a67-113">**A4SWIFT_SecondaryMessageType** (optional)</span></span>  
  
4.  <span data-ttu-id="23a67-114">Compile e implemente el esquema de encabezado personalizado.</span><span class="sxs-lookup"><span data-stu-id="23a67-114">Build and deploy the custom header schema.</span></span>  
  
5.  <span data-ttu-id="23a67-115">Establezca la propiedad de configuración de esquema de encabezado de SWIFT del desensamblador SWIFT (en el proyecto de canalización de recepción) en el esquema de encabezado personalizado.</span><span class="sxs-lookup"><span data-stu-id="23a67-115">Set the SWIFT Header Schema configuration property of the SWIFT disassembler (in your receive pipeline project) to the custom header schema.</span></span>  
  
 <span data-ttu-id="23a67-116">Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ \* las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span><span class="sxs-lookup"><span data-stu-id="23a67-116">For more information about these and other promoted properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span> <span data-ttu-id="23a67-117">Para obtener más información sobre cómo usar el Editor de BizTalk para crear y editar esquemas, promocionar propiedades mediante un esquema de propiedades y generar e implementar proyectos de esquema, vea la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="23a67-117">For more information about using BizTalk Editor to create and edit schemas, promote properties using a property schema, and build and deploy schema projects, see BizTalk Server Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a67-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="23a67-118">See Also</span></span>  
 [<span data-ttu-id="23a67-119">Trabajar con el desensamblador y el ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="23a67-119">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)