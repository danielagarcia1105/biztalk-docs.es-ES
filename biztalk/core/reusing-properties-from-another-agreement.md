---
title: Volver a usar propiedades de otro acuerdo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2a4e1efbfb7a86c18fb3643a789312a3707a72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reusing-properties-from-another-agreement"></a><span data-ttu-id="e5b35-102">Volver a usar propiedades de otro acuerdo</span><span class="sxs-lookup"><span data-stu-id="e5b35-102">Reusing Properties from Another Agreement</span></span>
<span data-ttu-id="e5b35-103">Se pueden reusar propiedades entre acuerdos.</span><span class="sxs-lookup"><span data-stu-id="e5b35-103">You can reuse properties between agreements.</span></span> <span data-ttu-id="e5b35-104">De este modo, ahorrará tiempo cuando la mayoría o todas las propiedades de un acuerdo nuevo son las mismas que las de un acuerdo que ya existe.</span><span class="sxs-lookup"><span data-stu-id="e5b35-104">This can save a significant amount of time when either most or all of the properties of a new agreement are the same as those of an existing agreement.</span></span> <span data-ttu-id="e5b35-105">La interfaz de usuario [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] en [!INCLUDE[prague](../includes/prague-md.md)] permite exportar un acuerdo a un archivo de plantilla XML.</span><span class="sxs-lookup"><span data-stu-id="e5b35-105">The [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] user interface in [!INCLUDE[prague](../includes/prague-md.md)] enables you to export an agreement into an XML template file.</span></span> <span data-ttu-id="e5b35-106">A continuación, puede importar la plantilla XML para reusar las mismas propiedades de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e5b35-106">You can then import the XML template to reuse the same agreement properties.</span></span>  
  
 <span data-ttu-id="e5b35-107">La exportación de un acuerdo a una plantilla XML captura la mayoría de propiedades del acuerdo, pero no todas.</span><span class="sxs-lookup"><span data-stu-id="e5b35-107">Exporting the agreement to an XML template captures most, but not all, properties from the agreement.</span></span> <span data-ttu-id="e5b35-108">Las siguientes propiedades *no* exportarán al archivo de plantilla XML:</span><span class="sxs-lookup"><span data-stu-id="e5b35-108">The following properties will *not* be exported to the XML template file:</span></span>  
  
-   <span data-ttu-id="e5b35-109">Todas las propiedades de la **propiedades generales** página en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="e5b35-109">All the properties from the **General Properties** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="e5b35-110">Todas las propiedades de la **contactos** página en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="e5b35-110">All the properties from the **Contacts** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="e5b35-111">Todas las propiedades de la **propiedades adicionales** página en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="e5b35-111">All the properties from the **Additional Properties** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="e5b35-112">Configuración relacionada con el identificador de la **identificadores** página de la ficha de acuerdo unidireccional. Los enfoques son:</span><span class="sxs-lookup"><span data-stu-id="e5b35-112">Identifier-related settings from the **Identifiers** page in the one-way agreement tab. These are:</span></span>  
  
    -   <span data-ttu-id="e5b35-113">**Para X12**: ISA5, ISA6, ISA7, ISA8 y la configuración de resolución de acuerdo adicional</span><span class="sxs-lookup"><span data-stu-id="e5b35-113">**For X12**: ISA5, ISA6, ISA7, ISA8, and additional agreement resolver settings</span></span>  
  
    -   <span data-ttu-id="e5b35-114">**Para EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2 y configuración de resolución de acuerdo adicional</span><span class="sxs-lookup"><span data-stu-id="e5b35-114">**For EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2, and additional agreement resolver settings</span></span>  
  
    -   <span data-ttu-id="e5b35-115">**Para AS2**: AS2-To, AS2-From y la configuración de resolución de acuerdo adicional</span><span class="sxs-lookup"><span data-stu-id="e5b35-115">**For AS2**: AS2-To, AS2-From, and additional agreement resolver settings</span></span>  
  
-   <span data-ttu-id="e5b35-116">La asociación de puerto de envío el **puertos de envío** página en la ficha de acuerdo unidireccional para X12, EDIFACT y AS2 contratos.</span><span class="sxs-lookup"><span data-stu-id="e5b35-116">Send port association from the **Send Ports** page in the one-way agreement tab for X12, EDIFACT, and AS2 agreements.</span></span>  
  
 <span data-ttu-id="e5b35-117">Aparte de las propiedades enumeradas arriba, las siguientes propiedades se exportarán al archivo de plantilla XML:</span><span class="sxs-lookup"><span data-stu-id="e5b35-117">Other than the properties listed above, the following properties will be exported to the XML template file:</span></span>  
  
-   <span data-ttu-id="e5b35-118">Toda la configuración relacionada con el protocolo de codificación (X12, EDIFACT o AS2).</span><span class="sxs-lookup"><span data-stu-id="e5b35-118">All settings related to the encoding protocol (X12, EDIFACT, or AS2).</span></span>  
  
-   <span data-ttu-id="e5b35-119">Toda la configuración relacionada con el proceso por lotes (excepto el ID de lote).</span><span class="sxs-lookup"><span data-stu-id="e5b35-119">All the batch-related settings (other than the batch ID).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5b35-120">Se sobrescribirán todas las propiedades aplicables al copiar propiedades en el acuerdo de destino.</span><span class="sxs-lookup"><span data-stu-id="e5b35-120">All the applicable properties will be overwritten when you copy properties to the destination agreement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5b35-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e5b35-121">In This Section</span></span>  
  
-   [<span data-ttu-id="e5b35-122">Exportar las propiedades de acuerdo a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="e5b35-122">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [<span data-ttu-id="e5b35-123">Propiedades del acuerdo de importación de un archivo XML</span><span class="sxs-lookup"><span data-stu-id="e5b35-123">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="e5b35-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5b35-124">See Also</span></span>  
 [<span data-ttu-id="e5b35-125">Configurar propiedades de EDI</span><span class="sxs-lookup"><span data-stu-id="e5b35-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)