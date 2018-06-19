---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 263f1f5d9441a30687df3e1a7a1170b7bf35e2fc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015075"
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a>Establecimiento de canalizaciones de envío para JD Edwards EnterpriseOne
Microsoft BizTalk Adapter para JD Edwards EnterpriseOne requiere que seleccione **XMLTransmit** y **XMLReceive** para el envío y las canalizaciones de recepción respectivamente.  
  
### <a name="to-set-pipelines"></a>Para establecer las canalizaciones  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SendToJDEEnterpriseOne`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **JDE EnterpriseOne**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
4.  Haga clic en **Aceptar**.  
  
