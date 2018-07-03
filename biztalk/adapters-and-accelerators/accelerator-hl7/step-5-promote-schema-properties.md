---
title: 'Paso 5: Promocionar las propiedades de esquema | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60aa8681e9647e592af3173295c3d32e216f1f2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003221"
---
# <a name="step-5-promote-schema-properties"></a><span data-ttu-id="5ad4c-102">Paso 5: Promocionar las propiedades de esquema</span><span class="sxs-lookup"><span data-stu-id="5ad4c-102">Step 5: Promote Schema Properties</span></span>
<span data-ttu-id="5ad4c-103">En este paso, se promocionan las propiedades de esquema para que un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestación puede hacer referencia a esos valores de propiedad que se creación en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-103">In this step, you promote schema properties so that a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration can reference those property values that you create in later steps.</span></span> <span data-ttu-id="5ad4c-104">La promoción es un mecanismo que se usa para hacer referencia a un valor específico dentro de una instancia de mensaje y hacerla accesible a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componentes como orquestación o para fines de enrutamiento por contenidos.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-104">Promotion is a mechanism that you use to reference a specific value within a message instance and make it accessible to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] components such as orchestration or for content-based routing purposes.</span></span> <span data-ttu-id="5ad4c-105">Además, es visible de forma Microsoft IntelliSense en el Editor de expresiones de propiedad promocionada [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ad4c-105">Additionally, a promoted property is visible by Microsoft IntelliSense in the Expression Editor of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="5ad4c-106"> auditoría y la funcionalidad de registro con la herramienta de mantenimiento de BizTalk y el seguimiento de actividad (HAT) pueden realizar un seguimiento de propiedades promocionadas del esquema único.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-106"> auditing and logging functionality with the BizTalk Health and Activity Tracking (HAT) tool can track only promoted schema properties.</span></span>  
  
### <a name="to-promote-schema-properties"></a><span data-ttu-id="5ad4c-107">Para promocionar las propiedades de esquema</span><span class="sxs-lookup"><span data-stu-id="5ad4c-107">To promote schema properties</span></span>  
  
1. <span data-ttu-id="5ad4c-108">En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga doble clic en el **DoorBell.xsd** el nodo para abrir el esquema.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-108">In Solution Explorer, under **BTAHL7 Project**, double-click the **DoorBell.xsd** node to open the schema.</span></span>  
  
2. <span data-ttu-id="5ad4c-109">Haga clic en el **FirstName** elemento de campo, seleccione **promover**y, a continuación, haga clic en **promoción rápida**.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-109">Right-click the **FirstName** field element, point to **Promote**, and then click **Quick Promotion**.</span></span>  
  
3. <span data-ttu-id="5ad4c-110">Haga clic en **Aceptar** para agregar el esquema de propiedades al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-110">Click **OK** to add the property schema to the project.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="5ad4c-111"> Agrega un círculo de color naranja en el icono para el **FirstName** elemento, que indica que el elemento se ha promocionado.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-111"> adds an orange circle to the icon for the **FirstName** element, indicating that the element has been promoted.</span></span>  
  
4. <span data-ttu-id="5ad4c-112">Repita estos pasos para promover los siguientes elementos de campo:</span><span class="sxs-lookup"><span data-stu-id="5ad4c-112">Repeat these steps to promote the following field elements:</span></span>  
  
   -   <span data-ttu-id="5ad4c-113">**middleName**</span><span class="sxs-lookup"><span data-stu-id="5ad4c-113">**MiddleName**</span></span>  
  
   -   <span data-ttu-id="5ad4c-114">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="5ad4c-114">**LastName**</span></span>  
  
   -   <span data-ttu-id="5ad4c-115">**SSN**</span><span class="sxs-lookup"><span data-stu-id="5ad4c-115">**SSN**</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5ad4c-116">Es importante tener en cuenta que un identificador (PID) del paciente promocionar como un número del seguro social (SSN) hace que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para realizar el seguimiento de esa propiedad para cada mensaje entrante a través del sistema.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-116">It is important to note that promoting a patient ID (PID) such as a social security number (SSN) causes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to track that property for every inbound message through the system.</span></span> <span data-ttu-id="5ad4c-117">El inconveniente de esta situación es que la base de datos de seguimiento de mensajes mantiene una copia de los números de seguridad social del paciente.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-117">The side effect of this situation is that the message-tracking database keeps a copy of patient SSNs.</span></span> <span data-ttu-id="5ad4c-118">Esto puede crear un problema de seguridad importantes.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-118">This can create a significant security issue.</span></span> <span data-ttu-id="5ad4c-119">Debe proteger este almacén de datos con extremo cuidado o evitar por completo la promoción de los datos de PID.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-119">You must either protect this data store with extreme care or avoid the promotion of PID data completely.</span></span>  
  
    <span data-ttu-id="5ad4c-120">Para obtener más información sobre el seguimiento de documentos en función de los elementos de esquema que ha promocionado, consulte la Ayuda de BizTalk Server para obtener información sobre el seguimiento de estado y actividad.</span><span class="sxs-lookup"><span data-stu-id="5ad4c-120">For more information about tracking documents based on the schema elements that you promoted, see BizTalk Server Help for information on Health and Activity Tracking.</span></span>  
  
   <span data-ttu-id="5ad4c-121">Continúe con [paso 6: validar los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="5ad4c-121">Proceed to [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad4c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ad4c-122">See Also</span></span>  
 [<span data-ttu-id="5ad4c-123">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="5ad4c-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)