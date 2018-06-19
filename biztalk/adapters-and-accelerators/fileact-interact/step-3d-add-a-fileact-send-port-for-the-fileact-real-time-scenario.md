---
title: 'Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a22ba41-4f43-4fbb-92f7-a0fd7558d2ce
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f7440a0bad39fbfddb6319f4051a397f08ac09f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966378"
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario"></a>Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct
Antes de empezar este paso, debe completar [paso 3c: agregar un puerto de envío de archivo para capturar Sw:HandleRequest mensaje para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md).  
  
### <a name="to-add-a-fileact-send-port"></a>Para agregar un puerto de envío FILEACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_FA_SendRequest_RealTime.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **FILEACT**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte FILEACT** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Establecer la contraseña según corresponda para la conectividad SAG.|  
    |**Nombre de usuario.**|Defina el nombre de usuario según corresponda para la conectividad SAG.|  
    |**Modo del adaptador**|En la lista desplegable, seleccione **almacenar y retransmitir**.|  
    |**Indicador de sin repudio**|En la lista desplegable, seleccione **FALSE**.|  
    |**Tipo de solicitud**|Establecer correspondientes \<RequestType\> cadena, según su aprovisionamiento con SWIFT.|  
    |**ResponseCrypto**|En la lista desplegable, seleccione **FALSE**.|  
    |**Solicitante**|Establecer correspondientes \<solicitante\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Servicio de respuesta**|Establecer correspondientes \<Respondedor\> cadena según su aprovisionamiento con SWIFT.|  
    |**Nombre del servicio**|Establecer correspondientes \<nombre del servicio\> en función de su aprovisionamiento con SWIFT.|  
    |**Indicador de confirmación**|En la lista desplegable, seleccione **FALSE**.|  
    |**Extremo de eventos**|En la lista desplegable, seleccione **FALSE**.|  
    |**Compresión de archivos**|En la lista desplegable, seleccione **ninguno**.|  
    |**Nombre de la carpeta física**|Escriba C:\SWIFTAdapterTutorial\Fileact\ClientLocation.|  
    |**Transferencia de extremo**|Escriba el extremo adecuado para el conjunto de enrutamiento SAG. Este valor debe coincidir con el punto de conexión de SnL que configuró en SAG.|  
    |**PerfilServicio**|En la lista desplegable, seleccione **recuento de transacciones**.|  
    |**Notificación de entrega**|En la lista desplegable, seleccione **FALSE**.|  
    |**Cola de notificación**|Escriba el nombre de cola, en función de su aprovisionamiento con SWIFT.|  
  
    > [!NOTE]
    >  Si el mensaje con el recuento de transacciones que se va a transferirse, establezca el modo de perfil de servicio para "recuento de transacciones" en el FileAct puerto de envío.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione el host de Fileact.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. En la ventana Propiedades de puerto de envío, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|En la lista desplegable, seleccione **BTS. ReceivePortName**.|  
    |**Operador**|En la lista desplegable, seleccione  **==** .|  
    |**Valor**|Tutorial_FA_InputRequest_RealTime de tipo.|  
    |**Agrupar por**|Dejar el valor predeterminado.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [Paso 3E: Agregar un puerto de envío de ARCHIVOS para capturar el mensaje Sw:ExchangeFileResponse para el escenario de FileAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)