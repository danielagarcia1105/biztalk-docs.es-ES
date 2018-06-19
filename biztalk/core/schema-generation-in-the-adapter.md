---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 4e4209c75ca52585c0a11141dbe0d9841fa6a5ba
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24016023"
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="1feb8-101">Generación de esquemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="1feb8-101">Schema Generation in the Adapter</span></span>
<span data-ttu-id="1feb8-102">Un sistema TIBCO Rendezvous no incluye un repositorio de tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1feb8-102">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="1feb8-103">Todos los análisis y construcciones de mensajes se incluyen en el tipo de aplicación Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="1feb8-103">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="1feb8-104">Debido a esta limitación, el adaptador de Microsoft BizTalk para TIBCO Rendezvous no puede proporcionar capacidades de generación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="1feb8-104">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="1feb8-105">Esquemas de escritura</span><span class="sxs-lookup"><span data-stu-id="1feb8-105">Writing Schemas</span></span>  
 <span data-ttu-id="1feb8-106">Debe escribir un esquema y usar **Agregar elemento existente** en Visual Studio para importarlo para su uso en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="1feb8-106">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="1feb8-107">Los esquemas son muy importantes para las herramientas de desarrollo de BizTalk Server y para la integración en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1feb8-107">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="1feb8-108">Los programadores de BizTalk Server tienen la opción de proporcionar un esquema completo, minimalista o una versión intermedia.</span><span class="sxs-lookup"><span data-stu-id="1feb8-108">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1feb8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1feb8-109">See Also</span></span>  
 [<span data-ttu-id="1feb8-110">Introducción</span><span class="sxs-lookup"><span data-stu-id="1feb8-110">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)