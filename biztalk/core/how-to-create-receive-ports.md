---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0cd93bcd2d1855f137600214b6a07d52b6f52e4f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-receive-ports"></a>Cómo crear puertos de recepción
Siga estos pasos para crear un puerto de recepción mediante Visual Studio.  
  
### <a name="to-create-a-receive-port"></a>Para crear un puerto de recepción  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.  
  
3.  En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:  
  
    1.  En el **nombre** , escriba `ReceiveFromTIBCORV`.  
  
    2.  En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.  
  
    3.  Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.  
  
4.  En el **ubicaciones de recepción** página, realice lo siguiente:  
  
    1.  Haga clic en **Nueva**.  
  
    2.  En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.  
  
    3.  Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.  
  
    4.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.  
  
    5.  En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.  
  
    6.  Seleccione el **habilitar ventana de servicio** casilla de verificación.  
  
    7.  Haga clic en **Aceptar**.  
  
5.  En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.  
  
6.  En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.  
  
7.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)