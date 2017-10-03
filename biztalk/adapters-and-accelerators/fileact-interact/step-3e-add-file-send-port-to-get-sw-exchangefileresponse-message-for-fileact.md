---
title: "Paso 3E: agregar un puerto de envío de archivo para capturar los mensajes de Sw:ExchangeFileResponse para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9314f86-a2c9-4ef3-8474-b7e2e2f8bf66
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18e26d13196a46045191b9e5767040e2216ceba2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-a-file-send-port-to-capture-swexchangefileresponse-message-for-the-fileact-real-time-scenario"></a>Paso 3E: agregar un puerto de envío de archivo para capturar los mensajes de Sw:ExchangeFileResponse para el escenario en tiempo real de FileAct
Antes de comenzar este paso, debe completar [paso 3D: agregar un puerto de envío de FILEACT para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md).  
  
### <a name="to-add-a-file-send-port-to-capture-swexchangefileresponse-message"></a>Para agregar un archivo de puerto de envío para capturar Sw:ExchangeFileResponse mensaje  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_FA_SendResponseToSender.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ResponseClient y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
  
8.  En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|En la lista desplegable, seleccione **BTS. SPName**.|  
    |**Operador**|En la lista desplegable, seleccione  **==** .|  
    |**Valor**|Tutorial_FA_SendRequest_RealTime de tipo.|  
    |**Agrupar por**|Dejar el valor predeterminado.|  
  
9. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)