---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: e5f68232aa0cb59835523df0afac01f3d1949489
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a>Configuración de canalizaciones para PeopleSoft Enterprise
El Adaptador de Microsoft BizTalk para PeopleSoft Enterprise requiere que seleccione una canalización apropiada.  
  
## <a name="setting-pipelines"></a>Configuración de canalizaciones  
  
#### <a name="to-set-pipelines"></a>Para establecer las canalizaciones  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
4.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de PeopleSoft](../core/creating-peoplesoft-send-handlers.md)