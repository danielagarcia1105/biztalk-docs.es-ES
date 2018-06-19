---
title: 'Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec380c088f27fe09f518c385990e3801b5c019dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965986"
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a>Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar
Completa [paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) antes de comenzar este paso.
  
## <a name="add-an-interact-send-port"></a>Agregar un puerto de envío INTERACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendRequest_RealTime**.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Establecer la contraseña según corresponda para la conectividad SAG.|  
    |**Nombre de usuario.**|Defina el nombre de usuario según corresponda para la conectividad SAG.|  
    |**Modo del adaptador**|En la lista desplegable, seleccione **en tiempo real**.|  
    |**Formato de mensaje**|**InteractMessage**.|  
    |**Indicador de sin repudio**|**FALSE**.|  
    |**Tipo de solicitud**|Escriba la correspondiente \<RequestType\> cadena, según su aprovisionamiento con SWIFT.|  
    |**ResponseCrypto**|**FALSE**.|  
    |**Solicitante**|Establézcalo en la correspondiente \<solicitante\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Servicio de respuesta**|Establézcalo en la correspondiente \<Respondedor\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Nombre del servicio**|Establézcalo en la correspondiente \<nombre del servicio\>, en función de su aprovisionamiento con SWIFT.|  
    |**Notificación de entrega**|En la lista desplegable, seleccione **FALSE**.|  
    |**Cola de notificación**|Escriba el nombre de la cola apropiada, en función de su aprovisionamiento con SWIFT.|  
  
    > [!NOTE]
    >  Si solo carga va a transferirse, conjunto MessageFormat a "Payloadonly" en la interacción puerto de recepción y puerto de envío de interacción. Establezca la recepción y canalizaciones de envío a PassThru.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione el host de interacción.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
    |**La canalización de recepción**|**XMLReceive**|  
  
9. En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|En la lista desplegable, seleccione **BTS. ReceivePortName**.|  
    |**Operador**|En la lista desplegable, seleccione  **==** .|  
    |**Valor**|Tipo de **Tutorial_IA_InputRequest_RealTime**.|  
    |**Agrupar por**|Dejar el valor predeterminado.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [Paso 3D: Agregar un puerto de envío de ARCHIVOS para capturar el mensaje Sw:HandleResponse para el escenario de InterAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)