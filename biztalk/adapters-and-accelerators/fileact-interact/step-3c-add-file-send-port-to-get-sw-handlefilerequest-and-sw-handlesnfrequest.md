---
title: 'Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6858164ee82f935c607246e7e93ffd86908f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225948"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a>Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de reenvío y almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 3B: agregar una ubicación de recepción de FILEACT para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md).  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a>Para agregar un archivo de puerto de envío para capturar Sw:ResponseServer mensaje  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_FA_SendResponseToReceiver.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ResponseServer y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
  
8.  En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Primera fila: propiedad**|En la lista desplegable, seleccione **BTS. MessageType**.|  
    |**Primera fila: operador**|En la lista desplegable, seleccione  **==** .|  
    |**Primera fila: valor**|Tipo de **Sw-HandleFileRequest**.|  
    |**Primera fila: Agrupar por**|En la lista desplegable, seleccione **o**.|  
    |**Segunda fila: propiedad**|En la lista desplegable, seleccione **BTS. MessageType**.|  
    |**Segunda fila: operador**|En la lista desplegable, seleccione  **==** .|  
    |**Segunda fila: valor**|Tipo de **Sw-HandleSnFRequest**.|  
    |**Segunda fila: Agrupar por**|Dejar el valor predeterminado.|  
  
9. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [Paso 3B: agregar un FILEACT ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [Paso 3D: agregar un puerto de envío de FILEACT para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)