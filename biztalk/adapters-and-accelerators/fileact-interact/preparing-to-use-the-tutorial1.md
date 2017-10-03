---
title: Preparando para utilizar el SimulationTutorial1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efedfeb184b8b0105b8622b6b3f068faffd6a906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-to-use-the-tutorial"></a>Preparando para utilizar el Tutorial
Debe hacer lo siguiente antes de usar el tutorial de extremo a extremo de adaptador de A4SWIFT.  
  
1.  Para este tutorial, necesitará los siguientes artefactos SWIFT:  
  
    -   Puerta de enlace SWIFT Alliance (SAG) 6.1  
  
    -   Acceso remoto (RA) 6.1  
  
    -   SWIFT WebStation 6.0  
  
    -   Vínculo de SWIFTNet (SNL) 6.1  
  
2.  Debe configurar SAG: crear el MessagePartners, dos puntos finales y reglas de enrutamiento en SAG y pruebe la conectividad SAG en el equipo donde instale los adaptadores. Para obtener información, consulte la documentación de SAG.  
  
3.  Siga las instrucciones indicadas en el tema "Cómo para crear un nuevo Host" en la Ayuda de Microsoft BizTalk Server ([http://go.microsoft.com/fwlink/? LinkId = 100422](http://go.microsoft.com/fwlink/?LinkId=100422)) para crear un Host in-process para el adaptador de InterAct, denominado *interacthost*y otro Host en curso para el adaptador de FileAct, denominado *fileacthost*. Utilizará estos hosts durante la creación de controladores para los adaptadores.  
  
4.  Cree las siguientes carpetas para el tutorial:  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ClientLocation  
  
    -   c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ResponseClient  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ResponseServer  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ServerLocation  
  
    -   c:\SWIFTAdapterTutorial\Fileact\StatusEvents  
  
    -   c:\SWIFTAdapterTutorial\Fileact\PullRequest  
  
    -   c:\SWIFTAdapterTutorial\Fileact\PullResponse  
  
    -   c:\SWIFTAdapterTutorial\Interact\HandleRequest  
  
    -   c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime  
  
    -   c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF  
  
    -   c:\SWIFTAdapterTutorial\Interact\Response  
  
    -   c:\SWIFTAdapterTutorial\Interact\PullRequest  
  
    -   c:\SWIFTAdapterTutorial\Interact\Pullresponse  
  
5.  Debe tener una conexión a ITB SWIFT o entorno activo para probar el adaptador.  
  
## <a name="see-also"></a>Vea también  
 [BizTalk FileAct e interactuar Tutorial de adaptadores-to-End](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)   
 [Interactuar en tiempo real escenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [Interactuar almacén y escenario de reenvío (inserción)](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [Escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [Escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)