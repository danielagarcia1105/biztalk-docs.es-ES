---
title: 'Paso 16: Iniciar la orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- message enrichment tutorial, orchestrations
ms.assetid: a9032b0b-1497-4f6a-8474-a94c14976be0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d2d1429d6b5d8df7facf55900683356200279b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992774"
---
# <a name="step-16-start-the-orchestration"></a>Paso 16: Iniciar la orquestación
En este paso, dé de alta el servicio con el fin de asociar el proceso empresarial que se ha diseñado en la orquestación con el entorno físico en el que se ejecutará la orquestación. Además, inicia el procesamiento de la orquestación para que pueda probar la aplicación.  
  
### <a name="to-start-the-orchestration"></a>Para iniciar la orquestación  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, en el panel de árbol de consola, en **orquestaciones**, haga clic en **BTAHL7_Project.Doorbell_Orchestration**y, a continuación, haga clic en **dar de alta** .  
  
2. Haga clic en **BTAHL7_Project.Doorbell_Orchestration**y, a continuación, haga clic en **iniciar**.  
  
   > [!NOTE]
   >  Asegúrese de que ha iniciado la **MLLPSendPort** puerto de envío y habilitar el **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** ubicación de recepción.  
  
   Continúe con [paso 17: crear la aplicación WSClient](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)