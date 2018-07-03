---
title: Canalización de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5700b3adb0769edff4ec820b4d95353383c08e6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968021"
---
# <a name="send-pipeline"></a><span data-ttu-id="cd509-102">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="cd509-102">Send Pipeline</span></span>
<span data-ttu-id="cd509-103">Este ejemplo proporciona un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de envío que se puede personalizar para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd509-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="cd509-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="cd509-104">Demonstrates</span></span>  
 <span data-ttu-id="cd509-105">Este ejemplo muestra cómo procesar un mensaje XML saliente en el mensaje RNIF equivalente mediante la canalización de envío BTARN (PipelineSend.btp).</span><span class="sxs-lookup"><span data-stu-id="cd509-105">This sample demonstrates how to process an outgoing XML message into the equivalent RNIF message using the BTARN send pipeline (PipelineSend.btp).</span></span> <span data-ttu-id="cd509-106">PipelineSend.btp se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNPipelines.</span><span class="sxs-lookup"><span data-stu-id="cd509-106">PipelineSend.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="cd509-107">Incluye las etapas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd509-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="cd509-108">ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="cd509-108">XML Assembler</span></span>  
  
-   <span data-ttu-id="cd509-109">Codificador MIME</span><span class="sxs-lookup"><span data-stu-id="cd509-109">MIME Encoder</span></span>  
  
-   <span data-ttu-id="cd509-110">Enviar mensaje Non-repudiate</span><span class="sxs-lookup"><span data-stu-id="cd509-110">Send message Non-repudiate</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd509-111">Si selecciona uno de los componentes anteriores de la BTARN canalización de envío en el Diseñador de canalizaciones en Visual Studio, las propiedades de ese componente no se mostrará en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cd509-111">If you select one of the above components of the BTARN send pipeline in the Pipeline Designer in Visual Studio, the properties for that component will not be displayed in the Properties pane.</span></span> <span data-ttu-id="cd509-112">Para mostrar las propiedades del componente, debe agregar el componente al cuadro de herramientas mediante el **elegir elementos del cuadro de herramientas** comando en el menú Herramientas; elimine el componente existente desde la canalización de envío; y, a continuación, agregue el componente desde el Cuadro de herramientas en la fase apropiada en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="cd509-112">To display the properties of the component, you must add the component to the Toolbox by using the **Choose Toolbox Items** command in the Tools menu; delete the existing component from the send pipeline; and then add the component from the Toolbox into the appropriate stage in the Pipeline Designer.</span></span> <span data-ttu-id="cd509-113">Si, a continuación, seleccione el componente, sus propiedades se mostrará en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cd509-113">If you then select the component, its properties will be displayed in the Properties pane.</span></span>  
  
 <span data-ttu-id="cd509-114">Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes dentro de esta canalización, consulte [canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="cd509-114">For more information about the components of this pipeline, and the message flow within this pipeline, see [BTARN Send Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd509-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd509-115">See Also</span></span>  
 <span data-ttu-id="cd509-116">[Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="cd509-116">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="cd509-117">Canalización de envío de BTARN</span><span class="sxs-lookup"><span data-stu-id="cd509-117">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)