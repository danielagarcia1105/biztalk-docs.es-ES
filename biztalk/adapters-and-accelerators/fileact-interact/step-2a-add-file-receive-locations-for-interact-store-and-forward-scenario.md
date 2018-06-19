---
title: 'Paso 2A: Agregar archivo ubicaciones de recepción para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195480b616437eea7b1cfafa703d4ec5d0bd2b54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225276"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a>Paso 2A: Agregar archivo ubicaciones de recepción para el almacén de interacción y el escenario de avance (extracción)
Antes de comenzar este paso, debe completar [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de hacia delante y almacén de InterAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).  
  
### <a name="to-add-a-file-receive-location"></a>Para agregar una ubicación de recepción de archivos  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_IA_InputRequest_SnF**.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. Haga clic en **Aceptar**.  
  
10. Repita los pasos 1 y 2.  
  
11. Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
12. En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_IA_InputRequest_PullMode**.  
  
13. En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
14. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.  
  
15. En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Interact\PullRequest**y, a continuación, haga clic en **Aceptar**.  
  
16. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
17. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2B: agregar puertos de envío de archivo para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)   
 [Paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)