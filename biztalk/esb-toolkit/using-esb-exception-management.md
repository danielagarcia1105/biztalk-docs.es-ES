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
ms.openlocfilehash: fec20c447b184c2fdadf87f62f37f576f5100d08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-esb-exception-management"></a><span data-ttu-id="66a21-102">Uso de administración de excepciones de ESB</span><span class="sxs-lookup"><span data-stu-id="66a21-102">Using ESB Exception Management</span></span>
<span data-ttu-id="66a21-103">Errores y excepciones pueden producirse en un intervalo de contextos y durante una serie de fases de procesamiento diferentes en un ESB.</span><span class="sxs-lookup"><span data-stu-id="66a21-103">Errors and exceptions can occur in a range of contexts and during a number of different processing stages in an ESB.</span></span> <span data-ttu-id="66a21-104">Esta sección proporciona información sobre el control de excepciones y describe cómo publicar detalles a través del Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="66a21-104">This section provides information about handling exceptions and describes how you can publish details through the ESB Management Portal.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="66a21-105">Información general</span><span class="sxs-lookup"><span data-stu-id="66a21-105">Overview</span></span>  
 <span data-ttu-id="66a21-106">Hay muchas maneras de controlar las excepciones en un [!INCLUDE[prague](../includes/prague-md.md)] solución, incluido el uso de marcos de trabajo, como la biblioteca de información empresarial.</span><span class="sxs-lookup"><span data-stu-id="66a21-106">There are many ways to handle exceptions in a [!INCLUDE[prague](../includes/prague-md.md)] solution, including using frameworks such as the Enterprise Library.</span></span> <span data-ttu-id="66a21-107">Sin embargo, cuando se desarrolla con ESB y BizTalk Server, se trabaja en un entorno basado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="66a21-107">However, when developing with ESB and BizTalk Server, you are working in a message-based environment.</span></span> <span data-ttu-id="66a21-108">Todo el contenido de una solución de BizTalk está orientado a mensajes, y los programadores de BizTalk pensar en un modo orientado a mensajes.</span><span class="sxs-lookup"><span data-stu-id="66a21-108">Everything in a BizTalk solution is message-oriented, and BizTalk developers think in a message-oriented way.</span></span> <span data-ttu-id="66a21-109">Por lo tanto, la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implementa un enfoque orientado a mensajes para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="66a21-109">Therefore, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a message-oriented approach to exception handling.</span></span>  
  
 <span data-ttu-id="66a21-110">El marco de trabajo de administración de excepciones de ESB sigue un patrón de diseño que proporciona un enfoque flexible para la supervisión de excepciones y permite que las respuestas de error que se origine desde fuera de la solución, quizás en el nivel de unidad de negocio.</span><span class="sxs-lookup"><span data-stu-id="66a21-110">The ESB Exception Management Framework follows a design pattern that provides a flexible approach to exception monitoring and enables error responses to originate from outside of the solution—perhaps at business-unit level.</span></span>  
  
 <span data-ttu-id="66a21-111">Los temas siguientes describen el marco de trabajo de administración de excepciones de ESB con más detalle:</span><span class="sxs-lookup"><span data-stu-id="66a21-111">The following topics discuss the ESB Exception Management Framework in more detail:</span></span>  
  
-   [<span data-ttu-id="66a21-112">Diseño de la estructura de administración de la excepción de ESB</span><span class="sxs-lookup"><span data-stu-id="66a21-112">Design of the ESB Exception Management Framework</span></span>](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [<span data-ttu-id="66a21-113">Los componentes del marco de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="66a21-113">The Components of the Exception Management Framework</span></span>](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="66a21-114">Mediante el marco de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="66a21-114">Using the Exception Management Framework</span></span>](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="66a21-115">Crear controladores de excepción personalizada</span><span class="sxs-lookup"><span data-stu-id="66a21-115">Creating Custom Exception Handlers</span></span>](../esb-toolkit/creating-custom-exception-handlers.md)