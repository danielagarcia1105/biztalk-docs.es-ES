---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 6b15d9d03ef967bcf7189ef756da8fc63a0eb3f6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013683"
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a>Creación de puertos de envío para TIBCO Enterprise Message Service
Siga estos pasos para crear un puerto de envío.  
  
## <a name="creating-a-send-port"></a>Crear un puerto de envío  
  
#### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCOEMS`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **TIBCO EMS**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
    6.  Haga clic en **configurar** para configurar el puerto de envío.  
  
4.  En el **propiedades de transporte de TIBCO EMS** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba **el control de mensajes**, **definición de conexión de servidor**, **compatibilidad con transacciones**, **nombre de usuario**y el  **contraseña**.  
  
         No tiene que establecer la información de inicio de sesión.  
  
    2.  En la lista, seleccione la aplicación afiliada que ha creado para representar el sistema TIBCO EMS.  
  
    3.  Para **usar SSO**, seleccione **Sí**.  
  
    4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
  [Creación de controladores de envío de TIBCO Enterprise Message Service](../core/creating-tibco-enterprise-message-service-send-handlers.md)