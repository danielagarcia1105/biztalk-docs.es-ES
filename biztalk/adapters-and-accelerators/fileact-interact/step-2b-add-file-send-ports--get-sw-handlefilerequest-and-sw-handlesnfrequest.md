---
title: 'Paso 2B: agregar puertos de envío de archivos para capturar el handlefilerequest y SW mensajes del FileAct Store y reenvío (extracción) | Microsoft Docs'
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
ms.openlocfilehash: 47515324fae89937754e0643563f16df9777868a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991493"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a>Paso 2B: agregar puertos de envío de archivos para capturar el handlefilerequest y SW mensajes del FileAct Store y reenvío (extracción)
Antes de comenzar este paso, debe completar el [paso 2A: Agregar archivo ubicaciones de recepción para el FileAct Store y reenvío (extracción) de interact](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) sección.  

### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a>Para agregar un archivo de puerto de envío para capturar el Sw: HandleFileRequest mensaje  

1. Iniciar **administración de BizTalk Server**.  

2. En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  

3. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**  

4. En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_FA_SendPullResponsetoReceiver**.  

5. En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  

6. En el **propiedades de transporte de archivo** cuadro de diálogo el **carpeta de destino** , escriba **C:\SWIFTAdapterTutorial\FileAct\PullResponse**y, a continuación, haga clic en **Aceptar**.  

7. En el **propiedades de puerto de envío** ventana, haga lo siguiente:  


   |   **Úselo**    |                        **Para ello**                         |
   |-------------------|---------------------------------------------------------------|
   | **Controlador de envío**  | En la lista desplegable, seleccione **BizTalkServerApplication**. |
   | **Canalización de envío** |       En la lista desplegable, seleccione **XMLTransmit**.        |


8. Haga clic en **Aceptar**.  

9. Repita los pasos 1 y 2.  

10. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta dinámico**.  

11. En el **propiedades de puerto de envío** ventana, nombre el puerto de envío<strong>, Tutorial_IA_DynamicSendPort</strong>.  

12. En el **propiedades de puerto de envío** ventana, haga lo siguiente:  


    |     **Úselo**     |                  **Para ello**                  |
    |----------------------|--------------------------------------------------|
    |  **Canalización de envío**   | En la lista desplegable, seleccione **XMLTransmit**. |
    | **Canalización de recepción** | En la lista desplegable, seleccione **XMLReceive**.  |


13. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Paso 2A: Agregar archivo ubicaciones de recepción para el escenario FileAct Store y reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [Paso 2C: Agregar un puerto de envío de FILEACT para el escenario de almacenamiento y reenvío (extracción) de FileAct](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)