---
title: Desarrollo de esquemas EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b241b5d0477d7aa477511c43b642e4e312f2651a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-edi-schemas"></a><span data-ttu-id="fb661-102">Desarrollar esquemas EDI</span><span class="sxs-lookup"><span data-stu-id="fb661-102">Developing EDI Schemas</span></span>
<span data-ttu-id="fb661-103">En los temas de esta sección se describe cómo modificar los esquemas EDI para su uso con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb661-103">The topics in this section describe how to modify EDI Schemas for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fb661-104">Para usar un esquema de documento en la solución, debe implementar el esquema al agregarlo a un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. A continuación, debe crear e implementar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb661-104">To use a document schema in your solution, you need to deploy the schema by adding it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and then building and deploying the project.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="fb661-105">implementará el proyecto en el valor predeterminado 1 de aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fb661-105"> will deploy the project in the default BizTalk Application 1.</span></span> <span data-ttu-id="fb661-106">Puede ver los esquemas que se implementan abriendo el **esquemas** nodo bajo **BizTalk Application 1** nodo el **aplicaciones** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="fb661-106">You can see the schemas that are deployed by opening the **Schemas** node under **BizTalk Application 1** node the **Applications** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="fb661-107">Puede implementar un ensamblado en una aplicación diferente mediante la herramienta de implementación de línea de comandos `BTSTask`.</span><span class="sxs-lookup"><span data-stu-id="fb661-107">You can deploy an assembly into a different application by using the command-line deployment tool `BTSTask`.</span></span>  
  
 <span data-ttu-id="fb661-108">El Asistente para configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementa automáticamente los esquemas de control y servicio.</span><span class="sxs-lookup"><span data-stu-id="fb661-108">The service and control schemas are automatically deployed by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration wizard.</span></span> <span data-ttu-id="fb661-109">Para verlos, haga clic en el **esquemas** nodo en el **aplicación EDI de BizTalk** nodo en la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="fb661-109">To see them, click the **Schemas** node in the **BizTalk EDI Application** node in the Administration Console.</span></span> <span data-ttu-id="fb661-110">Para obtener más información acerca de estos esquemas, vea [servicio EDI y esquemas de Control](../core/edi-service-and-control-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="fb661-110">For more information about these schemas, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb661-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fb661-111">In This Section</span></span>  
  
-   [<span data-ttu-id="fb661-112">Modificación de esquemas EDI</span><span class="sxs-lookup"><span data-stu-id="fb661-112">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md)  
  
-   [<span data-ttu-id="fb661-113">Personalizar enumeraciones en el esquema de sobres</span><span class="sxs-lookup"><span data-stu-id="fb661-113">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [<span data-ttu-id="fb661-114">Configuración de la validación de campos cruzados</span><span class="sxs-lookup"><span data-stu-id="fb661-114">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a><span data-ttu-id="fb661-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb661-115">See Also</span></span>  
 [<span data-ttu-id="fb661-116">Desarrollar y configurar soluciones EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fb661-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)