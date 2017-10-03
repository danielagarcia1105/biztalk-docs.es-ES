---
title: "La canalización de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7461ce357b3fa9cb6216dfce6381876100bb4287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-pipeline"></a><span data-ttu-id="011ce-102">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="011ce-102">Receive Pipeline</span></span>
<span data-ttu-id="011ce-103">Este ejemplo proporciona un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de recepción que puede personalizar para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="011ce-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="011ce-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="011ce-104">Demonstrates</span></span>  
 <span data-ttu-id="011ce-105">Este ejemplo muestra cómo procesar un mensaje entrante de RNIF en el equivalente mensaje de XML mediante la canalización de recepción de BTARN (PipelineReceive.btp).</span><span class="sxs-lookup"><span data-stu-id="011ce-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="011ce-106">PipelineReceive.btp se encuentra en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\RNPipelines.</span><span class="sxs-lookup"><span data-stu-id="011ce-106">PipelineReceive.btp is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="011ce-107">Incluye las etapas siguientes:</span><span class="sxs-lookup"><span data-stu-id="011ce-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="011ce-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="011ce-108">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="011ce-109">RNMimeDecoder (preprocesador y descodificador MIME)</span><span class="sxs-lookup"><span data-stu-id="011ce-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="011ce-110">RNDAsm (desensamblador XML)</span><span class="sxs-lookup"><span data-stu-id="011ce-110">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="011ce-111">RNPartyRes (componente de resolución de entidades)</span><span class="sxs-lookup"><span data-stu-id="011ce-111">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="011ce-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="011ce-112">MessageUpdater</span></span>  
  
 <span data-ttu-id="011ce-113">Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes en esta canalización, consulte [canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="011ce-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011ce-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="011ce-114">See Also</span></span>  
 <span data-ttu-id="011ce-115">[Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="011ce-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="011ce-116">Canalización de recepción de BTARN</span><span class="sxs-lookup"><span data-stu-id="011ce-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)