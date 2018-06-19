---
title: Validación extendida (BTS-XSD) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed147515b48a23c55e552710d6a76d6df981edd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245956"
---
# <a name="extended-bts-xsd-validation"></a><span data-ttu-id="50d98-102">Validación extendida (BTS-XSD)</span><span class="sxs-lookup"><span data-stu-id="50d98-102">Extended (BTS-XSD) Validation</span></span>
<span data-ttu-id="50d98-103">La canalización de recepción EDI y la canalización de envío EDI realizan la validación extendida solo si el esquema se ha personalizado con elementos cuyos tipos de datos no sean EDI.</span><span class="sxs-lookup"><span data-stu-id="50d98-103">The EDI receive pipeline and EDI send pipeline perform extended validation only if the schema has been customized with elements whose data type is not an EDI data type.</span></span> <span data-ttu-id="50d98-104">No se validaría estos elementos agregados por la validación de EDI, por lo que se cubrirán mediante la validación extendida.</span><span class="sxs-lookup"><span data-stu-id="50d98-104">These added elements would not be validated by EDI validation, so will be covered by extended validation.</span></span> <span data-ttu-id="50d98-105">La validación extendida usa `System.Xml.XmlValidatingReader` e incluye todas las comprobaciones que se pueden definir en un XSD estándar.</span><span class="sxs-lookup"><span data-stu-id="50d98-105">Extended validation uses `System.Xml.XmlValidatingReader` and includes all checks that can be defined in a standard XSD.</span></span>  
  
 <span data-ttu-id="50d98-106">La validación extendida se configura para todos los mensajes que se envían a una entidad o que esta recibe.</span><span class="sxs-lookup"><span data-stu-id="50d98-106">You configure extended validation for all messages to or from a party.</span></span> <span data-ttu-id="50d98-107">Para ello, seleccione la **validación extendida** checkbox en el **validación** página (en el **configuración del conjunto de transacciones** sección para X12 o EDIFACT), en el ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="50d98-107">You do so by selecting the **Extended Validation** checkbox in the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT), on the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="50d98-108">Puede habilitar la validación extendida sin habilitar la validación EDI, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="50d98-108">You can enable extension validation without enabling EDI validation, or vice versa.</span></span>  
  
 <span data-ttu-id="50d98-109">La validación extendida consta de las siguientes comprobaciones:</span><span class="sxs-lookup"><span data-stu-id="50d98-109">Extended validation consists of the following checks:</span></span>  
  
-   <span data-ttu-id="50d98-110">Requisito del elemento de datos y repeticiones permitidas</span><span class="sxs-lookup"><span data-stu-id="50d98-110">Data element requirement and allowed repetition</span></span>  
  
-   <span data-ttu-id="50d98-111">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="50d98-111">Enumerations</span></span>  
  
-   <span data-ttu-id="50d98-112">Validación de la longitud del elemento de datos (mín./máx.)</span><span class="sxs-lookup"><span data-stu-id="50d98-112">Data element length validation (min/max).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="50d98-113">No se admite la validación ampliada para mensajes procesados por lotes en el lado de envío de EDI.</span><span class="sxs-lookup"><span data-stu-id="50d98-113">Extended Validation for batched messages on the EDI send side is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d98-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="50d98-114">See Also</span></span>  
 [<span data-ttu-id="50d98-115">Validación del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="50d98-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)