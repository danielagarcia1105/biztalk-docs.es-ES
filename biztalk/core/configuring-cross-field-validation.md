---
title: Configuración de la validación de campos cruzados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f0c6ae8-0b8a-4826-9dfb-bf27e5ff7fa6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bde88ac82d69cdaa0dec7513e294953b7164b56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233652"
---
# <a name="configuring-cross-field-validation"></a><span data-ttu-id="0e985-102">Configurar la validación de campos cruzados</span><span class="sxs-lookup"><span data-stu-id="0e985-102">Configuring Cross-Field Validation</span></span>
<span data-ttu-id="0e985-103">Este tema describe cómo habilitar la validación de campos cruzados o segmentos en elementos de datos del conjunto de transacciones en mensajes con codificación EDI</span><span class="sxs-lookup"><span data-stu-id="0e985-103">This topic describes how to enable cross field/segment validation on transaction-set data elements in EDI-encoded messages.</span></span> <span data-ttu-id="0e985-104">Para ello, necesita definir dos valores:</span><span class="sxs-lookup"><span data-stu-id="0e985-104">To do so, you need to make two settings:</span></span>  
  
-   <span data-ttu-id="0e985-105">Defina la marca de validación de campos cruzados en una anotación del esquema EDI.</span><span class="sxs-lookup"><span data-stu-id="0e985-105">Set the cross-field validation flag in an annotation of the EDI schema.</span></span> <span data-ttu-id="0e985-106">Para los esquemas HIPAA o X12, se trata de la **X12ConditionDesignator_Check** marca.</span><span class="sxs-lookup"><span data-stu-id="0e985-106">For X12 or HIPAA schemas, this is the **X12ConditionDesignator_Check** flag.</span></span> <span data-ttu-id="0e985-107">Para los esquemas EDIFACT, se trata de la **EdifactDependencyRule_Check** marca.</span><span class="sxs-lookup"><span data-stu-id="0e985-107">For EDIFACT schemas, this is the **EdifactDependencyRule_Check** flag.</span></span>  
  
-   <span data-ttu-id="0e985-108">Habilite la validación de tipo EDI en las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="0e985-108">Enable EDI-type validation in the agreement properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0e985-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0e985-109">Prerequisites</span></span>  
 <span data-ttu-id="0e985-110">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e985-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="configuring-cross-field-validation"></a><span data-ttu-id="0e985-111">Configurar la validación de campos cruzados</span><span class="sxs-lookup"><span data-stu-id="0e985-111">Configuring Cross-Field Validation</span></span>  
  
1.  <span data-ttu-id="0e985-112">Abra el esquema en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0e985-112">Open your schema in BizTalk Editor.</span></span>  
  
2.  <span data-ttu-id="0e985-113">En el caso de un X12 o esquema HIPAA, busque el **X12ConditionDesignator_Check** marca una anotación en la sección appinfo del esquema.</span><span class="sxs-lookup"><span data-stu-id="0e985-113">For an X12 or HIPAA schema, find the **X12ConditionDesignator_Check** flag in an annotation in the appinfo section of the schema.</span></span> <span data-ttu-id="0e985-114">Establézcalo en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0e985-114">Set it to **Yes**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0e985-115">Si establece la marca X12ConditionDesignator_Check para **Sí** no se puede realizar desde el Editor de esquema de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0e985-115">Setting the flag X12ConditionDesignator_Check to **Yes** cannot be performed from BizTalk Schema Editor.</span></span> <span data-ttu-id="0e985-116">pero puede abrirla en un bloc de notas o en un editor de texto similar, editarla y guardar el archivo de esquema (.xsd).</span><span class="sxs-lookup"><span data-stu-id="0e985-116">For setting the flag, you will have to open it in a notepad or similar text editor, edit, and then save the schema file (.xsd).</span></span>  
  
3.  <span data-ttu-id="0e985-117">En el caso de un esquema EDIFACT, busque el **EdifactDependencyRule_Check** marca la anotación en la sección appinfo del esquema.</span><span class="sxs-lookup"><span data-stu-id="0e985-117">For an EDIFACT schema, find the **EdifactDependencyRule_Check** flag in the annotation in the appinfo section of the schema.</span></span> <span data-ttu-id="0e985-118">Establézcalo en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0e985-118">Set it to **Yes**.</span></span>  
  
4.  <span data-ttu-id="0e985-119">Para los segmentos que correspondan del esquema, especifique las condiciones de relación (X12 e HIPAA) o las reglas de dependencia (EDIFACT) que sean de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e985-119">For the applicable segments of the schema, specify the relational conditions (X12 and HIPAA) or dependency rules (EDIFACT) that apply.</span></span> <span data-ttu-id="0e985-120">Para obtener más información, consulte [validación cruzada de segmentos de campos](../core/cross-field-segment-validation.md).</span><span class="sxs-lookup"><span data-stu-id="0e985-120">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0e985-121">Se especifica una regla o condición de validación de campos cruzados para un segmento del esquema EDI.</span><span class="sxs-lookup"><span data-stu-id="0e985-121">A cross-field validation condition or rule is entered for a segment in an EDI schema.</span></span> <span data-ttu-id="0e985-122">Si especifica una regla de validación de campos cruzados para un elemento de datos en lugar de un segmento, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará una advertencia cuando se lleve a cabo la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="0e985-122">If you enter a cross-field validation rule for a data element, rather than a segment, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a warning when schema validation is performed.</span></span>  
  
5.  <span data-ttu-id="0e985-123">En el **validación** página (bajo la **configuración del conjunto de transacciones** sección) de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo acuerdo correspondiente, Asegúrese de que el **validación de tipo EDI** propiedad está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0e985-123">In the **Validation** page (under the **Transaction Set Settings** section) of the one-way agreement tab of the **Agreement Properties** dialog box for relevant agreement, make sure that the **EDI type Validation** property is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e985-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e985-124">See Also</span></span>  
 [<span data-ttu-id="0e985-125">Desarrollo de esquemas EDI</span><span class="sxs-lookup"><span data-stu-id="0e985-125">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)