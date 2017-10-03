---
title: "Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f4bae51-6869-4334-a3a1-ef7e662197ca
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d2027878771249ceb2dcb45683a71b4475a75cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a>Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío
Completa [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de hacia delante y almacén de InterAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) antes de comenzar este paso.
  
## <a name="add-a-file-receive-location"></a>Agregar ubicación de recepción de un archivo  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_IA_InputRequest_SnF.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, escriba C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. Haga clic en **Aceptar**.  
  
## <a name="complete-steps"></a>Complete los pasos
 [Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [Paso 3D: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)