---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el escenario en tiempo real de InterAct | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a900a6e-3e08-430a-8766-4a7192adba5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d36758716fb368760e9a93909f70bf4d92c5f840
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992457"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a>Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el escenario en tiempo real de InterAct
Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores. Antes de comenzar el procedimiento, debe completar las instrucciones de [paso 1: configurar el adaptador de SWIFT para el escenario en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Para agregar la configuración de SWIFTNet al archivo de parámetros  
  
1. Abra el archivo de parámetros en un editor de texto como Bloc de notas.  
  
    Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2. En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:  
  
    username:snlowner  
  
    subsystem_name:InteractStub  
  
    \#subsystem_group:InteractRT  
  
    \#subsystem_dependency:support, Swarm  
  
    subsystem_nature: crítico  
  
    subsystem_start:  
  
    **spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para interactuar RT \> - AdapterMode Interact"**  
  
    * FINAL  
  
    subsystem_stop:  
  
    * KILL9:snlreceiver  
  
    * FINAL  
  
    subsystem_status:  
  
    * NB:1:snlreceiver  
  
    * FINAL  
  
    start_event:SNL001:Subsystem InteractStub está activo  
  
    stop_event:SNL002:Subsystem InteractStub está inactivo  
  
    \#subsystem_name:User  
  
    \##subsystem_group:user  
  
    \##subsystem_dependency:  
  
    \#subsystem_nature: crítico  
  
    \#subsystem_start:  
  
    \#* FINAL  
  
    \#subsystem_stop:  
  
    \#* FINAL  
  
    \#subsystem_status:  
  
    # <a name="end"></a>* FINAL  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:Subsystem usuario está activo  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:Subsystem usuario está inactivo  
  
## <a name="see-also"></a>Vea también  
 [Escenario en tiempo real de interAct](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de InterAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [Paso 3: Creación de envío y recepción para el escenario en tiempo real de InterAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [Paso 4: Probar el escenario integral de InterAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)