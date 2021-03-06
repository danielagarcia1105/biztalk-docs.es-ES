---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 72cdd3553289df39442b71730a61e3271db381e7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013147"
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a>Establecimiento de canalizaciones de envío para TIBCO Rendezvous
Microsoft BizTalk Adapter para TIBCO Rendezvous requiere que seleccione XMLTransmit y XMLReceive para las canalizaciones de envío y recepción respectivamente.  
  
### <a name="to-set-pipelines"></a>Para establecer las canalizaciones  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
4.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de envío TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)   
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)