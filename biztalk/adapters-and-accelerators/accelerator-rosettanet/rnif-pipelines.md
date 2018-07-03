---
title: Canalizaciones RNIF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNIF, pipelines
- pipelines, RNIF
ms.assetid: 6cf480fe-6b54-4b13-8318-617f3bba71d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9245517e9a333229912e6c18c3a48ea06eadf50a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988501"
---
# <a name="rnif-pipelines"></a>Canalizaciones RNIF
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] recibir y enviar canalizaciones realizan el procesamiento necesario para recibir o enviar mensajes de RosettaNet Implementation Framework (RNIF). Este proceso implica el preprocesamiento, descodificar y codificar, cifrar o descifrar, desensamblado y ensamblado y autenticación de entidad.  
  
## <a name="pipeline-files"></a>Archivos de canalización  
 Estándar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recibir y enviar canalizaciones no procesan mensajes de RNIF de forma nativa. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ha agregado personalizado de recepción y canalizaciones de envío para este propósito. Estas canalizaciones se basan en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalizaciones, pero agregue [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]: capacidad de procesamiento específica. El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalizaciones (RNIFReceive.btp y RNIFSend.btp) están disponibles en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK en \< *unidad*\>: \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNPipelines. Esto le permite personalizar para sus propios fines.  
  
## <a name="see-also"></a>Vea también  
 [Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [Canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)