---
title: "Paso 2c: agregar un puerto de envío de FILEACT para el escenario de avance (extracción) y el almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8743a868-9625-477b-a7da-673bfa262723
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 803a8c671081afd3ba18b81d4770b80b26205eaf
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a>Paso 2c: agregar un puerto de envío de FILEACT para el escenario de avance (extracción) y el almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 2B: Agregar archivo puertos de envío para capturar los mensajes de Sw:HandleSnFRequest para el escenario de reenvío (extracción) y el almacenamiento de FileAct y Sw:HandleFileRequest](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md).  
  
### <a name="to-add-a-fileact-send-port"></a>Para agregar un puerto de envío de FileACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_FA_SendRequest_SnF**.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **FILEACT**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte FILEACT** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Establecer la contraseña según corresponda para la conectividad SAG.|  
    |**Nombre de usuario.**|Defina el nombre de usuario según corresponda para la conectividad SAG.|  
    |**Modo del adaptador**|En la lista desplegable, seleccione **almacenar y retransmitir**.|  
    |**Indicador de sin repudio**|En la lista desplegable, seleccione **FALSE**.|  
    |**Tipo de solicitud**|Establecer correspondientes \<RequestType\> cadena, según su aprovisionamiento con SWIFT.|  
    |**RequestCrypto**|En la lista desplegable, seleccione **FALSE**.|  
    |**Solicitante**|Establecer correspondientes \<solicitante\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Servicio de respuesta**|Establecer correspondientes \<Respondedor\> cadena.|  
    |**Nombre del servicio**|Establecer correspondientes  **\<nombre del servicio\>**.|  
    |**Indicador de confirmación**|En la lista desplegable, seleccione **FALSE**.|  
    |**Extremo de eventos**|En la lista desplegable, seleccione **FALSE**.|  
    |**Compresión de archivos**|En la lista desplegable, seleccione **ninguno**.|  
    |**Nombre de la carpeta física**|Escriba C:\SWIFTAdapterTutorial\Fileact\ClientLocation.|  
    |**Transferencia de extremo**|Escriba el extremo adecuado para el conjunto de enrutamiento SAG. Este valor debe coincidir con el punto de conexión SNL que configuró en SAG.|  
    |**PerfilServicio**|En la lista desplegable, seleccione **recuento de transacciones**.|  
    |**Notificación de entrega**|En la lista desplegable, seleccione **FALSE**.|  
    |**Cola de notificación**|Escriba el nombre de cola, en función de su aprovisionamiento con SWIFT.|  
  
    > [!NOTE]
    >  Si el mensaje con el recuento de transacciones que se va a transferirse, establezca el modo de perfil de servicio para "recuento de transacciones" en el FileAct puerto de envío.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione la **FileActHost**.|  
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
 [Paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [Paso 2B: Agregar puertos de envío de ARCHIVOS para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de almacenamiento y reenvío (extracción) de FileAct](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)