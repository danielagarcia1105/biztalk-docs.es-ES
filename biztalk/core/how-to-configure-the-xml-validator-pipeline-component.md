---
title: Cómo configurar el componente de canalización de validador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- send pipelines, validating
- pipeline components, XML Validator
- receive pipelines, validating
ms.assetid: 3b3becaf-703c-4399-a5ed-e7082e31e6e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 821ad6a1353c0aa29866fd36fe84a7ea6317690b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248388"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a><span data-ttu-id="61635-102">Cómo configurar el componente de canalización de validador XML</span><span class="sxs-lookup"><span data-stu-id="61635-102">How to Configure the XML Validator Pipeline Component</span></span>
<span data-ttu-id="61635-103">El componente de canalización de validador XML puede utilizarse en cualquier fase (excepto en desensamblar o ensamblar) tanto en una canalización de envío como de recepción.</span><span class="sxs-lookup"><span data-stu-id="61635-103">The XML Validator pipeline component can be used in any stage (except Disassemble or Assemble) in a send or receive pipeline.</span></span>  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a><span data-ttu-id="61635-104">Para configurar las propiedades del componente de canalización de validador XML</span><span class="sxs-lookup"><span data-stu-id="61635-104">To configure the properties for the XML Validator pipeline component</span></span>  
  
1.  <span data-ttu-id="61635-105">Arrastre el componente de canalización de validador XML a la fase de validación de una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="61635-105">Drag the XML Validator pipeline component into the Validate stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="61635-106">En la ventana Propiedades, en la **propiedades de componente de canalización** sección, configure lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="61635-106">In the Properties window, in the **Pipeline Component Properties** section, set the following.</span></span>  
  
    |<span data-ttu-id="61635-107">Use</span><span class="sxs-lookup"><span data-stu-id="61635-107">Use this</span></span>|<span data-ttu-id="61635-108">Para</span><span class="sxs-lookup"><span data-stu-id="61635-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="61635-109">**Esquemas de documentos**</span><span class="sxs-lookup"><span data-stu-id="61635-109">**Document schemas**</span></span>|<span data-ttu-id="61635-110">Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al documento.</span><span class="sxs-lookup"><span data-stu-id="61635-110">Indicates the namespace and typename of the schema or schemas to be applied to the document.</span></span> <span data-ttu-id="61635-111">Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md).</span><span class="sxs-lookup"><span data-stu-id="61635-111">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span> <span data-ttu-id="61635-112">Si no se hubiera especificado ningún esquema, la detección de esquemas en tiempo de ejecución se hará utilizando el espacio de nombres de destino del mensaje y la información de nombre del elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="61635-112">If no schemas are specified, the run-time schema discovery will be done by using the message's target namespace and root element name information.</span></span> <span data-ttu-id="61635-113">**Nota:** recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de documentos** propiedad.</span><span class="sxs-lookup"><span data-stu-id="61635-113">**Note:**  You may receive a "Two or more of the selected schema share the same target namespace" error if you specify two or more schemas for the **Document schemas** property.</span></span> <br /><br /> <span data-ttu-id="61635-114">Valor predeterminado: colección vacía</span><span class="sxs-lookup"><span data-stu-id="61635-114">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="61635-115">Procesamiento de intercambio recuperable</span><span class="sxs-lookup"><span data-stu-id="61635-115">Recoverable Interchange Processing</span></span>|<span data-ttu-id="61635-116">Cuando es "false" - indica que todo el intercambio se valida como una unidad (si se suspende los mensajes que contiene se produce un error, todo el intercambio).</span><span class="sxs-lookup"><span data-stu-id="61635-116">When "false" - indicates that entire interchange is validated as a unit (if any contained message fails, entire interchange is suspended).</span></span><br /><br /> <span data-ttu-id="61635-117">Cuando es "true" - indica que los mensajes dentro de intercambio se extraen individualmente validador con posibilidad de que algunos se propaguen mediante la ruta de mensajería y otros se suspendan.</span><span class="sxs-lookup"><span data-stu-id="61635-117">When "true" - indicates that messages within interchange are extracted individually by validator with possibility of some propagating through messaging pathway and others being suspended.</span></span><br /><br /> <span data-ttu-id="61635-118">Para obtener más información sobre el procesamiento de intercambio recuperable, consulte [el procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md).</span><span class="sxs-lookup"><span data-stu-id="61635-118">For more information on recoverable interchange processing, see [Recoverable Interchange Processing](../core/recoverable-interchange-processing.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61635-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="61635-119">See Also</span></span>  
 <span data-ttu-id="61635-120">[Componente de canalización de validador XML](../core/xml-validator-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="61635-120">[XML Validator Pipeline Component](../core/xml-validator-pipeline-component.md) </span></span>  
 [<span data-ttu-id="61635-121">Configurar componentes de canalización nativos</span><span class="sxs-lookup"><span data-stu-id="61635-121">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)