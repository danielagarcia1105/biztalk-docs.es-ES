---
title: Validación del mensaje EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21439969bc8e23b5b9901077c14a98128aa64c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238828"
---
# <a name="edi-message-validation"></a><span data-ttu-id="ad9a0-102">Validación de mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="ad9a0-102">EDI Message Validation</span></span>
<span data-ttu-id="ad9a0-103">Los datos EDI se transmiten como archivos delimitados (sin etiquetas de autodescripción) y, por tanto, las reglas de codificación fuerzan las reglas de formato estrictas para garantizar que la aplicación de destino puede analizar de forma correcta y consumir la información para el procesamiento descendente.</span><span class="sxs-lookup"><span data-stu-id="ad9a0-103">EDI data is transmitted as delimited files (without self describing tags) and therefore the encoding rules enforce strict formatting rules to ensure the destination application is able to successfully parse and consume the information for downstream processing.</span></span>  
  
 <span data-ttu-id="ad9a0-104">La canalización de recepción EDI y la canalización de envío EDI en las funcionalidades EDI y AS2 de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizan una serie de validaciones.</span><span class="sxs-lookup"><span data-stu-id="ad9a0-104">The EDI receive pipeline and EDI send pipeline in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 perform a series of validations.</span></span> <span data-ttu-id="ad9a0-105">Siempre se llevan a cabo algunos de estos procesos. Otros se realizan si se habilitan en las propiedades de acuerdo o en el esquema.</span><span class="sxs-lookup"><span data-stu-id="ad9a0-105">Some are always performed; others are performed if enabled in agreement properties or in the schema.</span></span> <span data-ttu-id="ad9a0-106">Para obtener más información acerca de cómo configurar la validación, consulte [cómo validar un EDI del intercambio está configurado](../core/how-validation-of-an-edi-interchange-is-configured.md).</span><span class="sxs-lookup"><span data-stu-id="ad9a0-106">For more information about how validation is configured, see [How Validation of an EDI Interchange Is Configured](../core/how-validation-of-an-edi-interchange-is-configured.md).</span></span>  
  
 <span data-ttu-id="ad9a0-107">La validación de un intercambio EDI implica diferentes tipos de validaciones, como se describe en los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="ad9a0-107">Validation of an EDI interchange involves several different kinds of validation, as described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad9a0-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ad9a0-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ad9a0-109">Cómo configurar la validación de un intercambio EDI</span><span class="sxs-lookup"><span data-stu-id="ad9a0-109">How Validation of an EDI Interchange Is Configured</span></span>](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [<span data-ttu-id="ad9a0-110">Validación estructural de EDI</span><span class="sxs-lookup"><span data-stu-id="ad9a0-110">EDI Structural Validation</span></span>](../core/edi-structural-validation.md)  
  
-   [<span data-ttu-id="ad9a0-111">Validación de propiedades de acuerdo</span><span class="sxs-lookup"><span data-stu-id="ad9a0-111">Agreement Properties Validation</span></span>](../core/agreement-properties-validation.md)  
  
-   [<span data-ttu-id="ad9a0-112">Validación de tipo (elemento de datos) de EDI</span><span class="sxs-lookup"><span data-stu-id="ad9a0-112">EDI Type (Data Element) Validation</span></span>](../core/edi-type-data-element-validation.md)  
  
-   [<span data-ttu-id="ad9a0-113">Validación extendida (BTS-XSD)</span><span class="sxs-lookup"><span data-stu-id="ad9a0-113">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)  
  
-   [<span data-ttu-id="ad9a0-114">Validación de esquemas</span><span class="sxs-lookup"><span data-stu-id="ad9a0-114">Schema Validation</span></span>](../core/schema-validation2.md)  
  
-   [<span data-ttu-id="ad9a0-115">Campo de segmento validación cruzada</span><span class="sxs-lookup"><span data-stu-id="ad9a0-115">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)