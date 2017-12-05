---
title: "Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394e570ad9bd1c0e7532923dac9c2cc702f2f567
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a>Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct
Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.  
  
Completa [paso 1: configurar el adaptador de SWIFT para el escenario al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) antes de comenzar este paso.
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a>Agregar configuración SWIFTNet el paramfile  
  
1.  Abra el paramfile en un editor de texto, como el Bloc de notas.  
  
2.  Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
3.  En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:  
    
     username:snlowner  
  
     subsystem_name:FileactStub  
  
     \#subsystem_group:fileactsnf  
  
     \#subsystem_dependency:support, conjunto  
  
     subsystem_nature: crítico  
  
     subsystem_start:  
  
     **spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para fileact SnF\> - AdapterMode fileact"**  
  
     * FINAL  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * FINAL  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * FINAL  
  
     start_event:SNL001:Subsystem FileactStubSnF está activo  
  
     stop_event:SNL002:Subsystem FileactStubSnF está inactivo  
  
     \#subsystem_name:User  
  
     \##subsystem_group:user  
  
     \##subsystem_dependency:  
  
     \#subsystem_nature: crítico  
  
     \#subsystem_start:  
  
     \#* FINAL  
  
     \#subsystem_stop:  
  
     \#* FINAL  
  
     \#subsystem_status:  
  
     \#* FINAL  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:Subsystem usuario está activo  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:Subsystem usuario está inactivo  
    
  
## <a name="complete-steps"></a>Complete los pasos
 [Escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)   
 [Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 4: Probar el escenario integral de almacenamiento y reenvío de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)