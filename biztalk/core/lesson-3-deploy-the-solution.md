---
title: 'Lección 3: Implementar la solución | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, deploying solutions
ms.assetid: b2f50fe7-7636-45bf-a09b-776065dd8a33
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1f8c565a55bf59c49ccda9f1c521ebadc60aac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261916"
---
# <a name="lesson-3-deploy-the-solution"></a><span data-ttu-id="fc613-102">Lección 3: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="fc613-102">Lesson 3: Deploy the Solution</span></span>
<span data-ttu-id="fc613-103">El primer paso para la implementación de la solución EAISolution consiste en agregar ensamblados a la base de datos de administración de BizTalk y a la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="fc613-103">The first step in deploying EAISolution is to add assemblies to the BizTalk Management database and the global assembly cache.</span></span>  
  
 <span data-ttu-id="fc613-104">El segundo paso se centra en la configuración de la aplicación y su inicio.</span><span class="sxs-lookup"><span data-stu-id="fc613-104">The second step is to configure and start the application.</span></span>  
  
 <span data-ttu-id="fc613-105">En [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md), se han agregado puertos lógicos a la orquestación EAIProcess.</span><span class="sxs-lookup"><span data-stu-id="fc613-105">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), you added logical ports to the EAIProcess orchestration.</span></span> <span data-ttu-id="fc613-106">En esta lección, definirá los puertos físicos y los enlazará a los puertos lógicos.</span><span class="sxs-lookup"><span data-stu-id="fc613-106">In this lesson, you define the physical ports, and bind the physical ports to the logical ports.</span></span> <span data-ttu-id="fc613-107">También deberá asignar la orquestación y los puertos de envío y de recepción a los host.</span><span class="sxs-lookup"><span data-stu-id="fc613-107">You must also assign orchestration, receive port and send ports to hosts.</span></span>  <span data-ttu-id="fc613-108">Un host es un contenedor virtual para los artefactos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fc613-108">A host is a virtual container for BizTalk artifacts.</span></span>  <span data-ttu-id="fc613-109">Cada host tiene varias instancias de host designadas para procesar los artefactos.</span><span class="sxs-lookup"><span data-stu-id="fc613-109">Each host has designated host instances to process the artifacts.</span></span>  
  
 <span data-ttu-id="fc613-110">En esta lección, obtendrá información sobre cómo administrar los artefactos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fc613-110">In this lesson, you learn about administering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts by using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="fc613-111">Para obtener información sobre el uso de la consola de administración de BizTalk Server, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="fc613-111">For information about using the BizTalk Server Administration Console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc613-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fc613-112">In This Section</span></span>  
  
-   [<span data-ttu-id="fc613-113">Paso 1: Implementar los proyectos</span><span class="sxs-lookup"><span data-stu-id="fc613-113">Step 1: Deploy the Projects</span></span>](../core/step-1-deploy-the-projects.md)  
  
-   [<span data-ttu-id="fc613-114">Paso 2: Configurar e iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fc613-114">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)  
  
-   [<span data-ttu-id="fc613-115">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="fc613-115">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc613-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc613-116">See Also</span></span>  
 <span data-ttu-id="fc613-117">[Antes de empezar el Tutorial](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="fc613-117">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="fc613-118">[Lección 1: Definir los esquemas y un mapa](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="fc613-118">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="fc613-119">Lección 2: Definir el proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="fc613-119">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)