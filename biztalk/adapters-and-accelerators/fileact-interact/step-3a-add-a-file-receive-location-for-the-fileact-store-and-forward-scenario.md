---
title: "Paso 3A: agregar un archivo de ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ecbf4a-a2b4-4534-8ca1-3bfbb6a697bf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e02f636500ed21d4442a43078bcd407c91d69d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario"></a>Paso 3A: agregar un archivo de ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md).  
  
### <a name="to-add-a-file-receive-location"></a>Para agregar un archivo de ubicación de recepción  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_FA_InputRequest_SnF.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 3B: agregar un FILEACT ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [Paso 3D: agregar un puerto de envío de FILEACT para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)