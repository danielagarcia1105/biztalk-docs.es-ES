---
title: 'Paso 6: Iniciar orquestaciones | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- loopback tutorial, starting orchestratrations
ms.assetid: f16a4a77-04fe-4e73-8517-556668174eb9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 973d0c5e8628d2363e8192c7faffeaebcc6d63b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993189"
---
# <a name="step-6-start-orchestrations"></a>Paso 6: Iniciar orquestaciones
En este paso, usará Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para iniciar las orquestaciones para Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a>Para iniciar las orquestaciones de BTARN con Visual Studio  
  
1.  En la Consola de administración de **BTARN** , expanda **Administración de BizTalk Server**, **Grupo de BizTalk**, **Aplicaciones**y **Aplicación de BizTalk 1**.  
  
2.  Haga clic en **Puertos de envío**e inicie los puertos de envío **PrivateInitiator_To_LOB** y **PrivateResponder_To_LOB** .  
  
3.  Haga clic en **Ubicaciones de recepción**y habilite las ubicaciones de recepción **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**y **Sync_Http_Receive** .  
  
4.  Haga clic en **Orquestaciones**e inicie todas las **Orquestaciones de BTARN**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 7: Crear un mensaje de LOB de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)   
 [Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)