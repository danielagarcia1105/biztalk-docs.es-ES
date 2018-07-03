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
# <a name="rnif-pipelines"></a><span data-ttu-id="33c24-102">Canalizaciones RNIF</span><span class="sxs-lookup"><span data-stu-id="33c24-102">RNIF Pipelines</span></span>
<span data-ttu-id="33c24-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] recibir y enviar canalizaciones realizan el procesamiento necesario para recibir o enviar mensajes de RosettaNet Implementation Framework (RNIF).</span><span class="sxs-lookup"><span data-stu-id="33c24-103">The Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive and send pipelines perform the processing required for receive or send RosettaNet Implementation Framework (RNIF) messages.</span></span> <span data-ttu-id="33c24-104">Este proceso implica el preprocesamiento, descodificar y codificar, cifrar o descifrar, desensamblado y ensamblado y autenticación de entidad.</span><span class="sxs-lookup"><span data-stu-id="33c24-104">This processing includes preprocessing, decoding/encoding, decrypting/encrypting, disassembly/assembly, and party authentication.</span></span>  
  
## <a name="pipeline-files"></a><span data-ttu-id="33c24-105">Archivos de canalización</span><span class="sxs-lookup"><span data-stu-id="33c24-105">Pipeline Files</span></span>  
 <span data-ttu-id="33c24-106">Estándar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recibir y enviar canalizaciones no procesan mensajes de RNIF de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="33c24-106">Standard [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive and send pipelines do not process RNIF messages natively.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="33c24-107"> ha agregado personalizado de recepción y canalizaciones de envío para este propósito.</span><span class="sxs-lookup"><span data-stu-id="33c24-107"> has added custom receive and send pipelines for this purpose.</span></span> <span data-ttu-id="33c24-108">Estas canalizaciones se basan en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalizaciones, pero agregue [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]: capacidad de procesamiento específica.</span><span class="sxs-lookup"><span data-stu-id="33c24-108">These pipelines are built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] pipelines, but add [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-specific processing capability.</span></span> <span data-ttu-id="33c24-109">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalizaciones (RNIFReceive.btp y RNIFSend.btp) están disponibles en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK en \< *unidad*\>: \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNPipelines.</span><span class="sxs-lookup"><span data-stu-id="33c24-109">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipelines (RNIFReceive.btp and RNIFSend.btp) are available in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK at \<*drive*\>:\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="33c24-110">Esto le permite personalizar para sus propios fines.</span><span class="sxs-lookup"><span data-stu-id="33c24-110">This lets you customize them for your own purposes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c24-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="33c24-111">See Also</span></span>  
 <span data-ttu-id="33c24-112">[Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="33c24-112">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="33c24-113">Canalización de envío de BTARN</span><span class="sxs-lookup"><span data-stu-id="33c24-113">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)