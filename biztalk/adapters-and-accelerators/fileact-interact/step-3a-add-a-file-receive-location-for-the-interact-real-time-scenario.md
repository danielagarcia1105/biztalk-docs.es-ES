---
title: "Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5579375-8c05-4583-bcaa-b483ac275d8a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29b3eb291b1b36daab5d77aae74f6055a3c738
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a>Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar
Configurar una ubicación de recepción que le permite colocar fácilmente los archivos de prueba de validación. Utilice esta ubicación para el escenario de prueba.  
  
## <a name="add-a-file-receive-location"></a>Agregar ubicación de recepción de un archivo  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_IA_InputRequest_RealTime**.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**y, a continuación, haga clic en  **Aceptar**.  
  
8.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [Paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)