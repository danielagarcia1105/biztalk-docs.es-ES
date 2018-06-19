---
title: 'Paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb46943b20676dbe98f79db8760043bb51606c56
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964178"
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a>Paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de avance (extracción)
Antes de comenzar este paso, debe completar [paso 2B: Agregar archivo puertos de envío para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).  
  
### <a name="to-add-an-interact-send-port"></a>Para agregar un puerto de envío INTERACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendRequest_SnF**.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Establecer la contraseña según corresponda para la conectividad SAG.|  
    |**Nombre de usuario.**|Defina el nombre de usuario según corresponda para la conectividad SAG.|  
    |**Formato de mensaje**|**InteractMessage**|  
    |**Indicador de sin repudio**|**FALSE**|  
    |**Tipo de solicitud**|Escriba la correspondiente \<RequestType\> cadena, según su aprovisionamiento con SWIFT.|  
    |**ResponseCrypto**|**FALSE**|  
    |**Solicitante**|Escriba la correspondiente \<RequestorDN\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Servicio de respuesta**|Escriba la correspondiente \<ResponderDN\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Nombre del servicio**|Escriba la correspondiente \<nombre del servicio\>, en función de su aprovisionamiento con SWIFT.|  
    |**Notificación de entrega**|En la lista desplegable, seleccione **FALSE**.|  
    |**Cola de notificación**|Escriba el nombre de la cola apropiada, en función de su aprovisionamiento con SWIFT.|  
  
    > [!NOTE]
    >  Si solo carga va a transferirse, conjunto MessageFormat a "Carga" en la interacción puerto de recepción y puerto de envío de interacción. Establecer las canalizaciones de envío y recepción en PassThru.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione el host de interacción.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|En la lista desplegable, seleccione **BTS. ReceivePortName**.|  
    |**Operador**|En la lista desplegable, seleccione  **==** .|  
    |**Valor**|Tipo de **Tutorial_IA_InputRequest_SnF**.|  
    |**Agrupar por**|Dejar el valor predeterminado.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2A: Agregar archivo ubicaciones de recepción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [Paso 2B: Agregar puertos de envío de ARCHIVOS para capturar el mensaje Sw:HandleRequest para el escenario de almacenamiento y reenvío (extracción) de InterAct](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)