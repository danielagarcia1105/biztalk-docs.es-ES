---
title: "Mediante la administración de excepciones de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eff5a729b8c8ca191b2185180e312f9e895c02
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="using-esb-exception-management"></a><span data-ttu-id="6cc8d-102">Uso de administración de excepciones de ESB</span><span class="sxs-lookup"><span data-stu-id="6cc8d-102">Using ESB Exception Management</span></span>
<span data-ttu-id="6cc8d-103">Errores y excepciones pueden producirse en un intervalo de contextos y durante una serie de fases de procesamiento diferentes en un ESB.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-103">Errors and exceptions can occur in a range of contexts and during a number of different processing stages in an ESB.</span></span> <span data-ttu-id="6cc8d-104">Esta sección proporciona información sobre el control de excepciones y describe cómo publicar detalles a través del Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-104">This section provides information about handling exceptions and describes how you can publish details through the ESB Management Portal.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="6cc8d-105">Información general</span><span class="sxs-lookup"><span data-stu-id="6cc8d-105">Overview</span></span>  
 <span data-ttu-id="6cc8d-106">Hay muchas maneras de controlar las excepciones producidas en una solución de BizTalk Server, incluido el uso de marcos de trabajo, como la biblioteca de información empresarial.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-106">There are many ways to handle exceptions in a BizTalk Server solution, including using frameworks such as the Enterprise Library.</span></span> <span data-ttu-id="6cc8d-107">Sin embargo, cuando se desarrolla con ESB y BizTalk Server, se trabaja en un entorno basado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-107">However, when developing with ESB and BizTalk Server, you are working in a message-based environment.</span></span> <span data-ttu-id="6cc8d-108">Todo el contenido de una solución de BizTalk está orientado a mensajes, y los programadores de BizTalk pensar en un modo orientado a mensajes.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-108">Everything in a BizTalk solution is message-oriented, and BizTalk developers think in a message-oriented way.</span></span> <span data-ttu-id="6cc8d-109">Por lo tanto, la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implementa un enfoque orientado a mensajes para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-109">Therefore, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a message-oriented approach to exception handling.</span></span>  
  
 <span data-ttu-id="6cc8d-110">El marco de trabajo de administración de excepciones de ESB sigue un patrón de diseño que proporciona un enfoque flexible para la supervisión de excepciones y permite que las respuestas de error que se origine desde fuera de la solución, quizás en el nivel de unidad de negocio.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-110">The ESB Exception Management Framework follows a design pattern that provides a flexible approach to exception monitoring and enables error responses to originate from outside of the solution—perhaps at business-unit level.</span></span>  
  
 <span data-ttu-id="6cc8d-111">Los temas siguientes describen el marco de trabajo de administración de excepciones de ESB con más detalle:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-111">The following topics discuss the ESB Exception Management Framework in more detail:</span></span>  
  
-   [<span data-ttu-id="6cc8d-112">Diseño del marco de administración de excepciones de ESB</span><span class="sxs-lookup"><span data-stu-id="6cc8d-112">Design of the ESB Exception Management Framework</span></span>](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [<span data-ttu-id="6cc8d-113">Los componentes del marco de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="6cc8d-113">The Components of the Exception Management Framework</span></span>](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="6cc8d-114">Uso del marco de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="6cc8d-114">Using the Exception Management Framework</span></span>](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="6cc8d-115">Creación de controladores de excepción personalizados</span><span class="sxs-lookup"><span data-stu-id="6cc8d-115">Creating Custom Exception Handlers</span></span>](../esb-toolkit/creating-custom-exception-handlers.md)