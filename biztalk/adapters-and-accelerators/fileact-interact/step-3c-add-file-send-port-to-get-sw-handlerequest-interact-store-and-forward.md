---
title: "Paso 3c: Agregar puerto de envío de archivo para obtener Sw:HandleRequest-interactuar almacenar y retransmitir | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c57f2f3a6e2fcfc199e56d34c44aa7667451d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a>Paso 3c: Agregar puerto de envío de archivo para obtener Sw:HandleRequest-interactuar almacenamiento y reenvío
Antes de comenzar este paso, debe completar [paso 3B: agregar una ubicación de recepción interactuar para el escenario de hacia delante y almacén de InterAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md).  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>Para agregar un archivo de puerto de envío para capturar el mensaje Sw:HandleRequest  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_IA_SendResponseToReceiver.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Interact\HandleRequest y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
  
8.  En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|En la lista desplegable, seleccione **BTS. ReceivePortName**.|  
    |**Operador**|En la lista desplegable, seleccione  **==** .|  
    |**Valor**|Tipo de **Tutorial_IA_InputRequest_SnF**.|  
    |**Agrupar por**|Dejar el valor predeterminado.|  
  
9. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [Paso 3D: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)