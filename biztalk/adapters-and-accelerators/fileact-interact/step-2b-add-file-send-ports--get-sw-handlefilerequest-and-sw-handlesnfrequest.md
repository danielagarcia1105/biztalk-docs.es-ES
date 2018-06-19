---
title: 'Paso 2B: agregar puertos de envío de archivo para capturar la Sw:HandleFileRequest y Sw:HandleSnFRequest mensajes para el almacenamiento de FileAct y el reenvío de escenario (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c2eb55cd6aca9b26b8a8ac47ab6dbe192f174d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224364"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a>Paso 2B: agregar puertos de envío de archivo para capturar la Sw:HandleFileRequest y Sw:HandleSnFRequest mensajes para el almacenamiento de FileAct y el reenvío de escenario (extracción)
Antes de comenzar este paso, debe completar la [paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) sección.  
  
### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a>Para agregar un archivo de puerto de envío para capturar el Sw: mensaje HandleFileRequest  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_FA_SendPullResponsetoReceiver**.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba **C:\SWIFTAdapterTutorial\FileAct\PullResponse**y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
  
8.  Haga clic en **Aceptar**.  
  
9. Repita los pasos 1 y 2.  
  
10. Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta dinámico**.  
  
11. En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **, Tutorial_IA_DynamicSendPort**.  
  
12. En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
13. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [Paso 2c: agregar un puerto de envío de FILEACT para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)