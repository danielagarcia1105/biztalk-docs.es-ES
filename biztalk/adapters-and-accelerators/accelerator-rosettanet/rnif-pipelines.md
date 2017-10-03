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
# <a name="rnif-pipelines"></a><span data-ttu-id="f87ef-102">Canalizaciones RNIF</span><span class="sxs-lookup"><span data-stu-id="f87ef-102">RNIF Pipelines</span></span>
<span data-ttu-id="f87ef-103">El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] recibir y enviar canalizaciones realizan el procesamiento necesario para recibir o enviar mensajes de RosettaNet Implementation Framework (RNIF).</span><span class="sxs-lookup"><span data-stu-id="f87ef-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive and send pipelines perform the processing required for receive or send RosettaNet Implementation Framework (RNIF) messages.</span></span> <span data-ttu-id="f87ef-104">Este proceso implica preprocesamiento, codificación o descodificación, cifrar/descifrar, desensamblado y ensamblado y autenticación de entidades.</span><span class="sxs-lookup"><span data-stu-id="f87ef-104">This processing includes preprocessing, decoding/encoding, decrypting/encrypting, disassembly/assembly, and party authentication.</span></span>  
  
## <a name="pipeline-files"></a><span data-ttu-id="f87ef-105">Archivos de canalización</span><span class="sxs-lookup"><span data-stu-id="f87ef-105">Pipeline Files</span></span>  
 <span data-ttu-id="f87ef-106">Estándar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recibir y enviar canalizaciones no procesan mensajes RNIF de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="f87ef-106">Standard [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive and send pipelines do not process RNIF messages natively.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f87ef-107">ha agregado personalizado de recepción y canalizaciones de envío para este propósito.</span><span class="sxs-lookup"><span data-stu-id="f87ef-107"> has added custom receive and send pipelines for this purpose.</span></span> <span data-ttu-id="f87ef-108">Estas canalizaciones se compilan en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalizaciones, pero agregar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-capacidad de procesamiento específico.</span><span class="sxs-lookup"><span data-stu-id="f87ef-108">These pipelines are built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] pipelines, but add [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-specific processing capability.</span></span> <span data-ttu-id="f87ef-109">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalizaciones (RNIFReceive.btp y RNIFSend.btp) están disponibles en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK en \< *unidad*>: \Microsoft BizTalk \<versión > Accelerator for RosettaNet\SDK\ RNPipelines.</span><span class="sxs-lookup"><span data-stu-id="f87ef-109">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipelines (RNIFReceive.btp and RNIFSend.btp) are available in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK at \<*drive*>:\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="f87ef-110">Esto le permite personalizar para sus propios fines.</span><span class="sxs-lookup"><span data-stu-id="f87ef-110">This lets you customize them for your own purposes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87ef-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f87ef-111">See Also</span></span>  
 <span data-ttu-id="f87ef-112">[Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="f87ef-112">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="f87ef-113">Canalización de envío BTARN</span><span class="sxs-lookup"><span data-stu-id="f87ef-113">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)