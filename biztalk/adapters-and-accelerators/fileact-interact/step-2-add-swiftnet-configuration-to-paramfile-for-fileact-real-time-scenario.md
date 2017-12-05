---
title: "Paso 2: Agregar configuración de SWIFTNet la Paramfile para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4feec3f-4755-477e-b3d6-1dd6d075255e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adad4d98be93e17bef4ab5eeb9e49271ffc94b74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a>Paso 2: Agregar configuración de SWIFTNet la Paramfile para el escenario en tiempo real de FileAct
Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.  
  
 Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Para agregar configuración de SWIFTNet a la paramfile  
  
1.  Abra el paramfile en un editor de texto, como el Bloc de notas.  
  
    > [!NOTE]
    >  Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2.  En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:  
  
     username:snlowner  
  
     subsystem_name:FileactStub  
  
     \#subsystem_group:fileact  
  
     \#subsystem_dependency:support, conjunto  
  
     subsystem_nature: crítico  
  
     subsystem_start:  
  
     **spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para fileact RT \> fileact - AdapterMode"**  
  
     * FINAL  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * FINAL  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * FINAL  
  
     start_event:SNL001:Subsystem FileactStub está activo  
  
     stop_event:SNL002:Subsystem FileactStub está inactivo  
  
     \#subsystem_name:User  
  
     \##subsystem_group:user  
  
     \##subsystem_dependency:  
  
     \#subsystem_nature: crítico  
  
     \#subsystem_start:  
  
     \#* FINAL  
  
     \#subsystem_stop:  
  
     \#* FINAL  
  
     \#subsystem_status:  
  
     #<a name="end"></a>* FINAL  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:Subsystem usuario está activo  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:Subsystem usuario está inactivo  
  
## <a name="see-also"></a>Vea también  
 [Escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)   
 [Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [Paso 4: Probar el escenario integral de FileAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)