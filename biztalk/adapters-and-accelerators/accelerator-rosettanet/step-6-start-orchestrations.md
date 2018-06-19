---
title: 'Paso 6: Iniciar orquestaciones | Documentos de Microsoft'
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
ms.openlocfilehash: 7ef08b7c0db08d527df4943aa25650d81231e703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209516"
---
# <a name="step-6-start-orchestrations"></a>Paso 6: Iniciar orquestaciones
En este paso, utilizará [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para iniciar las orquestaciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a>Para iniciar las orquestaciones de BTARN con Visual Studio  
  
1.  En la Consola de administración de **BTARN** , expanda **Administración de BizTalk Server**, **Grupo de BizTalk**, **Aplicaciones**y **Aplicación de BizTalk 1**.  
  
2.  Haga clic en **Puertos de envío**e inicie los puertos de envío **PrivateInitiator_To_LOB** y **PrivateResponder_To_LOB** .  
  
3.  Haga clic en **Ubicaciones de recepción**y habilite las ubicaciones de recepción **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**y **Sync_Http_Receive** .  
  
4.  Haga clic en **Orquestaciones**e inicie todas las **Orquestaciones de BTARN**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 7: Crear un mensaje de LOB de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)   
 [Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)