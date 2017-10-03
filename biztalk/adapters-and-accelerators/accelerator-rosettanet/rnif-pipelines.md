---
title: Las canalizaciones RNIF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNIF, pipelines
- pipelines, RNIF
ms.assetid: 6cf480fe-6b54-4b13-8318-617f3bba71d0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ec3b4d5c98414e3e6b9f5355dd8375d199decbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="rnif-pipelines"></a>Canalizaciones RNIF
El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] recibir y enviar canalizaciones realizan el procesamiento necesario para recibir o enviar mensajes de RosettaNet Implementation Framework (RNIF). Este proceso implica preprocesamiento, codificación o descodificación, cifrar/descifrar, desensamblado y ensamblado y autenticación de entidades.  
  
## <a name="pipeline-files"></a>Archivos de canalización  
 Estándar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recibir y enviar canalizaciones no procesan mensajes RNIF de forma nativa. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ha agregado personalizado de recepción y canalizaciones de envío para este propósito. Estas canalizaciones se compilan en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalizaciones, pero agregar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-capacidad de procesamiento específico. El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalizaciones (RNIFReceive.btp y RNIFSend.btp) están disponibles en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK en \< *unidad*>: \Microsoft BizTalk \<versión > Accelerator for RosettaNet\SDK\ RNPipelines. Esto le permite personalizar para sus propios fines.  
  
## <a name="see-also"></a>Vea también  
 [Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [Canalización de envío BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)