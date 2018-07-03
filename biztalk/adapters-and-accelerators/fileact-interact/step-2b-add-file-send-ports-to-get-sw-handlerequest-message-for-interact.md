---
title: 'Paso 2B: agregar puertos de envío de archivos para capturar el mensaje SW: HandleRequest para el escenario InterAct Store y reenvío (extracción) | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56cee834f5974d993dfeaa8fbfee8313eeb74064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004445"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a>Paso 2B: agregar puertos de envío de archivos para capturar el mensaje SW: HandleRequest para el escenario InterAct Store y reenvío (extracción)
Antes de comenzar este paso, debe completar [paso 2A: Agregar archivo ubicaciones de recepción para la interacción Store y reenvío (extracción) de interact](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md).  

### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>Para agregar un archivo de puerto de envío para capturar el mensaje SW: HandleRequest  

1. Iniciar **administración de BizTalk Server**.  

2. En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  

3. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**  

4. En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendPullResponsetoReceiver**.  

5. En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  

6. En el **propiedades de transporte de archivo** cuadro de diálogo el **carpeta de destino** , escriba **C:\SWIFTAdapterTutorial\Interact\PullResponse**y, a continuación, haga clic en **Aceptar**.  

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
 [Paso 2A: Agregar archivo ubicaciones de recepción para el escenario InterAct Store y reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [Paso 2C: Agregar un puerto de envío INTERACT para el escenario de almacenamiento y reenvío (extracción) de InterAct](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)