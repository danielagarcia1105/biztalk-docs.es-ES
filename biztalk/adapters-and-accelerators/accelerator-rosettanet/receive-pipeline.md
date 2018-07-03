---
title: Canalización de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a2c1de940fab14aa370dc1358efe36fe702a9d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990309"
---
# <a name="receive-pipeline"></a><span data-ttu-id="4b56d-102">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="4b56d-102">Receive Pipeline</span></span>
<span data-ttu-id="4b56d-103">Este ejemplo proporciona un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de recepción que se puede personalizar para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b56d-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4b56d-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="4b56d-104">Demonstrates</span></span>  
 <span data-ttu-id="4b56d-105">Este ejemplo muestra cómo procesar un mensaje entrante de RNIF en el equivalente mensaje de XML mediante la canalización de recepción de BTARN (PipelineReceive.btp).</span><span class="sxs-lookup"><span data-stu-id="4b56d-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="4b56d-106">PipelineReceive.btp se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNPipelines.</span><span class="sxs-lookup"><span data-stu-id="4b56d-106">PipelineReceive.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="4b56d-107">Incluye las etapas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b56d-107">It includes the following stages:</span></span>  
  
- <span data-ttu-id="4b56d-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="4b56d-108">ReceiveMessageNonRepudiate</span></span>  
  
- <span data-ttu-id="4b56d-109">RNMimeDecoder (preprocesador y descodificador MIME)</span><span class="sxs-lookup"><span data-stu-id="4b56d-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
- <span data-ttu-id="4b56d-110">RNDAsm (desensamblador XML)</span><span class="sxs-lookup"><span data-stu-id="4b56d-110">RNDAsm (XML Disassembler)</span></span>  
  
- <span data-ttu-id="4b56d-111">RNPartyRes (componente de resolución de entidades)</span><span class="sxs-lookup"><span data-stu-id="4b56d-111">RNPartyRes (Party Resolution component)</span></span>  
  
- <span data-ttu-id="4b56d-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="4b56d-112">MessageUpdater</span></span>  
  
  <span data-ttu-id="4b56d-113">Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes en esta canalización, consulte [canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="4b56d-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b56d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b56d-114">See Also</span></span>  
 <span data-ttu-id="4b56d-115">[Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="4b56d-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="4b56d-116">Canalización de recepción de BTARN</span><span class="sxs-lookup"><span data-stu-id="4b56d-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)