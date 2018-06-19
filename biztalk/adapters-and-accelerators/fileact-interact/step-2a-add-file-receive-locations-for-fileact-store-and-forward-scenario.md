---
title: 'Paso 2A: agregar ubicaciones de recepción de archivo | Documentos de Microsoft'
description: 'Paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct en BizTalk Server'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13720ebb-fbe4-4fe1-a095-9ae14c62def1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e297a85f309445c3caf569d2d752be58997e9754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224076"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a>Paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de reenvío (extracción) y el almacenamiento de FileAct](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md).  
  
## <a name="add-a-file-receive-location"></a>Agregar una ubicación de recepción de archivos  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_FA_InputRequest_SnF**.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. Haga clic en **Aceptar**.  
  
10. Repita los pasos 1 y 2.  
  
11. Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
12. En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_ FA_InputRequest_PullMode**.  
  
13. En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
14. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
15. En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Interact\PullRequest**y, a continuación, haga clic en **Aceptar**.  
  
16. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
17. Haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes
-  [Paso 2B: agregar puertos de envío de archivo para capturar la Sw:HandleFileRequest y Sw:HandleSnFRequest mensajes para el almacenamiento de FileAct y el reenvío de escenario (extracción)](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [Paso 2c: agregar un puerto de envío de FILEACT para el escenario de avance (extracción) y el almacenamiento de FileAct](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)