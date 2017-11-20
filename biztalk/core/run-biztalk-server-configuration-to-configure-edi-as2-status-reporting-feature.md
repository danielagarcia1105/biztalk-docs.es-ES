---
title: "Para habilitar los informes de estado, ejecutar &#39; Configuración de BizTalk Server &#39; y configurar la característica de informes de estado de EDI y AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334e77ed58d460aea3ca37f73c1165d62da0f10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a><span data-ttu-id="661ef-102">Para habilitar los informes de estado, ejecutar &#39; Configuración de BizTalk Server &#39; y configurar la característica de informes de estado de EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="661ef-102">To enable status reporting, run &#39;BizTalk Server Configuration&#39; and configure EDI-AS2 status reporting feature</span></span>
## <a name="details"></a><span data-ttu-id="661ef-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="661ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="661ef-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="661ef-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="661ef-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="661ef-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="661ef-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="661ef-106">Event ID</span></span>|-|  
|<span data-ttu-id="661ef-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="661ef-107">Event Source</span></span>|<span data-ttu-id="661ef-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="661ef-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="661ef-109">Componente</span><span class="sxs-lookup"><span data-stu-id="661ef-109">Component</span></span>|<span data-ttu-id="661ef-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="661ef-110">EDI Engine</span></span>|  
|<span data-ttu-id="661ef-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="661ef-111">Symbolic Name</span></span>|<span data-ttu-id="661ef-112">0</span><span class="sxs-lookup"><span data-stu-id="661ef-112">0</span></span>|  
|<span data-ttu-id="661ef-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="661ef-113">Message Text</span></span>|<span data-ttu-id="661ef-114">Para habilitar los informes de estado, ejecute 'Configuración de BizTalk Server' y configure la característica de informes de estado de EDI/AS2.</span><span class="sxs-lookup"><span data-stu-id="661ef-114">To enable status reporting, run 'BizTalk Server Configuration' and configure EDI/AS2 status reporting feature.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="661ef-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="661ef-115">Explanation</span></span>  
 <span data-ttu-id="661ef-116">Este evento de error,  indica que no funciona la generación de informes de estado de EDI/AS2 porque no se ha configurado.</span><span class="sxs-lookup"><span data-stu-id="661ef-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not working because it has not been configured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="661ef-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="661ef-117">User Action</span></span>  
 <span data-ttu-id="661ef-118">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="661ef-118">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="661ef-119">Ejecute el Asistente para configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="661ef-119">Run the BizTalk Server Configuration wizard.</span></span> <span data-ttu-id="661ef-120">Haga clic en el nodo Tiempo de ejecución de EDI y AS2 de BizTalk y active la propiedad "Habilitar informes de estado de tiempo de ejecución de EDI y AS2 de BizTalk para este grupo de BizTalk".</span><span class="sxs-lookup"><span data-stu-id="661ef-120">Click the BizTalk EDI/AS2 Runtime node, and check the "Enable BizTalk EDI/AS2 Runtime Status Reporting for this BizTalk Group" property.</span></span> <span data-ttu-id="661ef-121">Debe configurar BAM para configurar los informes de estado de EDI/AS2.</span><span class="sxs-lookup"><span data-stu-id="661ef-121">You must configure BAM in order to configure EDI/AS2 status reporting.</span></span>  
  
2.  <span data-ttu-id="661ef-122">En la consola de administración de BizTalk Server, habilite los informes de estado de EDI para la entidad al hacer clic en la propiedad "Activar informes de EDI" de la página General del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="661ef-122">In the BizTalk Server Administration Console, enable EDI status reporting for the party by clicking the "Activate EDI reporting" property in the General page of the EDI Properties dialog box.</span></span> <span data-ttu-id="661ef-123">Habilite los informes de estado de AS2 para la entidad al hacer clic en la propiedad "Activar informes de AS2" de la página General del cuadro de diálogo Propiedades de AS2.</span><span class="sxs-lookup"><span data-stu-id="661ef-123">Enable AS2 status reporting for the party by clicking the "Activate AS2 reporting" property in the General page of the AS2 Properties dialog box.</span></span> <span data-ttu-id="661ef-124">Debe reiniciar el servicio de BizTalk después de habilitar los informes de estado de EDI o AS2.</span><span class="sxs-lookup"><span data-stu-id="661ef-124">You must restart the BizTalk service after enabling EDI or AS2 status reporting.</span></span>