---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para la interacción Store y reenvío | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9495d6a53e9048dc5dee839f1dc859c62b4e9187
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014501"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a>Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para la interacción Store y el reenvío de Interact
Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores.  
  
 Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de hacia delante y Store InterAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Para agregar la configuración de SWIFTNet al archivo de parámetros  
  
1. Abra el archivo de parámetros en un editor de texto como Bloc de notas.  
  
   > [!NOTE]
   >  Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.  
  
2. En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:  
  
    username:snlowner  
  
    subsystem_name:InteractStub  
  
    \#subsystem_group:Interactsnf  
  
    \#subsystem_dependency:support, Swarm  
  
    subsystem_nature: crítico  
  
    subsystem_start:  
  
    **spawn "snlreceiver - SagMessagePartner \<MessagePartnerName del servidor de Interact SnF\> - AdapterMode Interact"**  
  
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
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:Subsystem usuario está activo  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:Subsystem usuario está inactivo  
  
## <a name="see-also"></a>Vea también  
 [Store y reenvío (inserción) de Interact](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para la interacción Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)   
 [Paso 3: Crear puertos de envío y recepción para la interacción Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 4: Probar el escenario integral de almacenamiento y reenvío de InterAct](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)