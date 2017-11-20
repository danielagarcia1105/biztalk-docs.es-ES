---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: bcccc92430a73685ced9ad7259d8ec57dfc450b8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-limitations"></a><span data-ttu-id="87d2c-101">Limitaciones de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="87d2c-101">TIBCO Rendezvous Limitations</span></span>
<span data-ttu-id="87d2c-102">En TIBCO Rendezvous, la exclusividad del nombre de campo no se garantiza.</span><span class="sxs-lookup"><span data-stu-id="87d2c-102">In TIBCO Rendezvous, field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="87d2c-103">Si un mensaje de TIBCO Rendezvous contiene dos nombres de campo que son iguales, el XML resultante no es válido.</span><span class="sxs-lookup"><span data-stu-id="87d2c-103">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
 <span data-ttu-id="87d2c-104">Otras limitaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="87d2c-104">Other limitations include the following:</span></span>  
  
-   <span data-ttu-id="87d2c-105">No se proporciona la ordenación y clasificación de los campos.</span><span class="sxs-lookup"><span data-stu-id="87d2c-105">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="87d2c-106">Según la documentación de TIBCO Rendezvous, los caracteres no imprimibles no se usan en nombres de asunto; sin embargo, sigue siendo posible usarlos.</span><span class="sxs-lookup"><span data-stu-id="87d2c-106">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="87d2c-107">BizTalk Adapter para TIBCO Rendezvous no admite nombres de asunto que contengan esos caracteres.</span><span class="sxs-lookup"><span data-stu-id="87d2c-107">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="87d2c-108">No se admite la conexión a daemons.</span><span class="sxs-lookup"><span data-stu-id="87d2c-108">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="87d2c-109">No se admiten tipos de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="87d2c-109">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="87d2c-110">No se admite la mensajería certificada en el lado de transmisión.</span><span class="sxs-lookup"><span data-stu-id="87d2c-110">Certified Messaging is not supported on the transmit side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d2c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="87d2c-111">See Also</span></span>  
 <span data-ttu-id="87d2c-112">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="87d2c-112">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="87d2c-113">Introducción</span><span class="sxs-lookup"><span data-stu-id="87d2c-113">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)