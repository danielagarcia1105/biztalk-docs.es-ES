---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 44da7839f0bee96db332dada214bdbc503067f56
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>Creación de puertos de envío para TIBCO Rendezvous
Siga estos pasos para crear un puerto de envío mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  Desde el **canalización de envío** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**. Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
    6.  Haga clic en **configurar** para configurar el puerto de envío.  
  
4.  En el **propiedades de transporte de TIBCO Rendezvous** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique las propiedades.  
  
         No tiene que establecer la información de inicio de sesión.  
  
    2.  En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema TIBCO Rendezvous.  
  
    3.  Para **usar SSO**, seleccione **Sí**.  
  
    4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)