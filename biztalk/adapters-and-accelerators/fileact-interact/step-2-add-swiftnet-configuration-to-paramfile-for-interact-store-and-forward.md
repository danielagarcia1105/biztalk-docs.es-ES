---
title: "Paso 2: Agregar configuración de SWIFTNet la Paramfile para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05524abd4cd57b8d804ab5995072905392fd3645
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a>Paso 2: Agregar configuración de SWIFTNet la Paramfile para el almacén de interacción y el escenario de reenvío
Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.  
  
 Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Para agregar configuración de SWIFTNet a la paramfile  
  
1.  Abra el paramfile en un editor de texto, como el Bloc de notas.  
  
    > [!NOTE]
    >  Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.  
  
2.  En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:  
  
     username:snlowner  
  
     subsystem_name:InteractStub  
  
     \#subsystem_group:Interactsnf  
  
     \#subsystem_dependency:support, conjunto  
  
     subsystem_nature: crítico  
  
     subsystem_start:  
  
     **spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para interactuar SnF\> - AdapterMode Interact"**  
  
     * FINAL  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * FINAL  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * FINAL  
  
     start_event:SNL001:Subsystem InteractStubSnF está activo  
  
     stop_event:SNL002:Subsystem InteractStubSnF está inactivo  
  
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
  
## <a name="see-also"></a>Vea también  
 [Interactuar almacén y escenario de reenvío (inserción)](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)   
 [Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 4: Probar el escenario integral de almacenamiento y reenvío de InterAct](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)