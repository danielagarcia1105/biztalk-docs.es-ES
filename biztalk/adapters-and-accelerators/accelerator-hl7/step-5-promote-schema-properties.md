---
title: 'Paso 5: Promocionar las propiedades de esquema | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9000b0466c8c0fc8d466f8174bc0e900a93bf392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-promote-schema-properties"></a><span data-ttu-id="ff2c8-102">Paso 5: Promocionar las propiedades de esquema</span><span class="sxs-lookup"><span data-stu-id="ff2c8-102">Step 5: Promote Schema Properties</span></span>
<span data-ttu-id="ff2c8-103">En este paso, se promocionan las propiedades de esquema para que un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestación puede hacer referencia a esos valores de propiedad que se crean en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-103">In this step, you promote schema properties so that a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration can reference those property values that you create in later steps.</span></span> <span data-ttu-id="ff2c8-104">La promoción es un mecanismo que utiliza para hacer referencia a un valor específico dentro de una instancia de mensaje y hacerla accesible a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componentes como orquestación o para fines de enrutamiento basado en contenido.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-104">Promotion is a mechanism that you use to reference a specific value within a message instance and make it accessible to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] components such as orchestration or for content-based routing purposes.</span></span> <span data-ttu-id="ff2c8-105">Además, una propiedad promocionada está visible de forma [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] IntelliSense en el Editor de expresiones de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff2c8-105">Additionally, a promoted property is visible by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] IntelliSense in the Expression Editor of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="ff2c8-106">auditoría y la funcionalidad de registro con la herramienta de mantenimiento de BizTalk y seguimiento de actividad (HAT) pueden realizar un seguimiento de propiedades promocionadas del esquema único.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-106"> auditing and logging functionality with the BizTalk Health and Activity Tracking (HAT) tool can track only promoted schema properties.</span></span>  
  
### <a name="to-promote-schema-properties"></a><span data-ttu-id="ff2c8-107">Para promocionar las propiedades de esquema</span><span class="sxs-lookup"><span data-stu-id="ff2c8-107">To promote schema properties</span></span>  
  
1.  <span data-ttu-id="ff2c8-108">En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga doble clic en el **DoorBell.xsd** nodo para abrir el esquema.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-108">In Solution Explorer, under **BTAHL7 Project**, double-click the **DoorBell.xsd** node to open the schema.</span></span>  
  
2.  <span data-ttu-id="ff2c8-109">Haga clic en el **FirstName** elemento de campo, seleccione **promover**y, a continuación, haga clic en **promoción rápida**.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-109">Right-click the **FirstName** field element, point to **Promote**, and then click **Quick Promotion**.</span></span>  
  
3.  <span data-ttu-id="ff2c8-110">Haga clic en **Aceptar** para agregar el esquema de propiedades para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-110">Click **OK** to add the property schema to the project.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="ff2c8-111">Agrega un círculo naranja en el icono de la **FirstName** elemento, que indica que el elemento se ha promocionado.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-111"> adds an orange circle to the icon for the **FirstName** element, indicating that the element has been promoted.</span></span>  
  
4.  <span data-ttu-id="ff2c8-112">Repita estos pasos para promover los siguientes elementos de campo:</span><span class="sxs-lookup"><span data-stu-id="ff2c8-112">Repeat these steps to promote the following field elements:</span></span>  
  
    -   <span data-ttu-id="ff2c8-113">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="ff2c8-113">**MiddleName**</span></span>  
  
    -   <span data-ttu-id="ff2c8-114">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="ff2c8-114">**LastName**</span></span>  
  
    -   <span data-ttu-id="ff2c8-115">**SSN**</span><span class="sxs-lookup"><span data-stu-id="ff2c8-115">**SSN**</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ff2c8-116">Es importante tener en cuenta que promover un paciente identificador (PID), como un número del seguro social (SSN) hace [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para realizar el seguimiento de esa propiedad para cada mensaje entrante a través del sistema.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-116">It is important to note that promoting a patient ID (PID) such as a social security number (SSN) causes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to track that property for every inbound message through the system.</span></span> <span data-ttu-id="ff2c8-117">El efecto secundario de esta situación es que la base de datos de seguimiento de mensajes mantiene una copia del paciente números de seguridad social.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-117">The side effect of this situation is that the message-tracking database keeps a copy of patient SSNs.</span></span> <span data-ttu-id="ff2c8-118">Esto puede crear un problema de seguridad importante.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-118">This can create a significant security issue.</span></span> <span data-ttu-id="ff2c8-119">Debe proteger este almacén de datos con mucho cuidado cuando o evitar la promoción de datos PID completamente.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-119">You must either protect this data store with extreme care or avoid the promotion of PID data completely.</span></span>  
  
     <span data-ttu-id="ff2c8-120">Para obtener más información sobre el seguimiento de documentos en función de los elementos de esquema que usted ha promocionado, consulte [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda para obtener información sobre el seguimiento de estado y actividad.</span><span class="sxs-lookup"><span data-stu-id="ff2c8-120">For more information about tracking documents based on the schema elements that you promoted, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help for information on Health and Activity Tracking.</span></span>  
  
 <span data-ttu-id="ff2c8-121">Continúe con [paso 6: validar los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="ff2c8-121">Proceed to [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2c8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff2c8-122">See Also</span></span>  
 [<span data-ttu-id="ff2c8-123">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="ff2c8-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)