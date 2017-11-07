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
# <a name="tibco-rendezvous-limitations"></a>Limitaciones de TIBCO Rendezvous
En TIBCO Rendezvous, la exclusividad del nombre de campo no se garantiza. Si un mensaje de TIBCO Rendezvous contiene dos nombres de campo que son iguales, el XML resultante no es válido.  
  
 Otras limitaciones incluyen:  
  
-   No se proporciona la ordenación y clasificación de los campos.  
  
-   Según la documentación de TIBCO Rendezvous, los caracteres no imprimibles no se usan en nombres de asunto; sin embargo, sigue siendo posible usarlos. BizTalk Adapter para TIBCO Rendezvous no admite nombres de asunto que contengan esos caracteres.  
  
-   No se admite la conexión a daemons.  
  
-   No se admiten tipos de datos personalizados.  
  
-   No se admite la mensajería certificada en el lado de transmisión.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)