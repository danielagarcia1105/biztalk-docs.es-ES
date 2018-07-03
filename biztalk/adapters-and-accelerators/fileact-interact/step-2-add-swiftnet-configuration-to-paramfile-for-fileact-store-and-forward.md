---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el FileAct Store y reenvío | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a287c6063ff60b08a53ec4f05d45da9225f1c30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998245"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a>Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el FileAct Store y el reenvío de Interact
Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores.  
  
Completa [paso 1: configurar el adaptador de SWIFT para el escenario de hacia delante y FileAct Store](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) antes de comenzar este paso.
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a>Agregar la configuración de SWIFTNet al archivo de parámetros  
  
1. Abra el archivo de parámetros en un editor de texto como Bloc de notas.  
  
2. Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
3. En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:  
    
    username:snlowner  
  
    subsystem_name:FileactStub  
  
    \#subsystem_group:fileactsnf  
  
    \#subsystem_dependency:support, Swarm  
  
    subsystem_nature: crítico  
  
    subsystem_start:  
  
    **spawn "snlreceiver - SagMessagePartner \<Server MessagePartnerName para fileact SnF\> - AdapterMode fileact"**  
  
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
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:Subsystem usuario está activo  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:Subsystem usuario está inactivo  
    
  
## <a name="complete-steps"></a>Complete los pasos
 [FileAct Store y reenvío de Interact](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para el FileAct Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)   
 [Paso 3: Crear puertos de envío y recepción para el FileAct Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 4: Probar el escenario integral de almacenamiento y reenvío de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)