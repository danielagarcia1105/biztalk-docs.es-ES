---
title: "Canalización de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b36340d241ac52fe4fb7f10025807f386c51a8ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-pipeline"></a><span data-ttu-id="88e8f-102">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="88e8f-102">Send Pipeline</span></span>
<span data-ttu-id="88e8f-103">Este ejemplo proporciona un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de envío que se puede personalizar para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="88e8f-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="88e8f-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="88e8f-104">Demonstrates</span></span>  
 <span data-ttu-id="88e8f-105">Este ejemplo muestra cómo procesar un mensaje XML saliente en el mensaje RNIF equivalente mediante la canalización de envío BTARN (PipelineSend.btp).</span><span class="sxs-lookup"><span data-stu-id="88e8f-105">This sample demonstrates how to process an outgoing XML message into the equivalent RNIF message using the BTARN send pipeline (PipelineSend.btp).</span></span> <span data-ttu-id="88e8f-106">PipelineSend.btp se encuentra en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\RNPipelines.</span><span class="sxs-lookup"><span data-stu-id="88e8f-106">PipelineSend.btp is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="88e8f-107">Incluye las etapas siguientes:</span><span class="sxs-lookup"><span data-stu-id="88e8f-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="88e8f-108">ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="88e8f-108">XML Assembler</span></span>  
  
-   <span data-ttu-id="88e8f-109">Codificador MIME</span><span class="sxs-lookup"><span data-stu-id="88e8f-109">MIME Encoder</span></span>  
  
-   <span data-ttu-id="88e8f-110">Enviar mensaje repudiate no</span><span class="sxs-lookup"><span data-stu-id="88e8f-110">Send message Non-repudiate</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88e8f-111">Si selecciona uno de los componentes anteriores de la BTARN canalización de envío en el Diseñador de canalizaciones en Visual Studio, las propiedades de ese componente no se mostrará en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="88e8f-111">If you select one of the above components of the BTARN send pipeline in the Pipeline Designer in Visual Studio, the properties for that component will not be displayed in the Properties pane.</span></span> <span data-ttu-id="88e8f-112">Para mostrar las propiedades del componente, debe agregar el componente al cuadro de herramientas mediante el **elegir elementos del cuadro de herramientas** de comandos en el menú Herramientas; eliminar el componente existente de la canalización de envío; y, a continuación, agregue el componente de la Cuadro de herramientas en la fase apropiada en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="88e8f-112">To display the properties of the component, you must add the component to the Toolbox by using the **Choose Toolbox Items** command in the Tools menu; delete the existing component from the send pipeline; and then add the component from the Toolbox into the appropriate stage in the Pipeline Designer.</span></span> <span data-ttu-id="88e8f-113">Si, a continuación, seleccione el componente, sus propiedades se mostrará en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="88e8f-113">If you then select the component, its properties will be displayed in the Properties pane.</span></span>  
  
 <span data-ttu-id="88e8f-114">Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes dentro de esta canalización, consulte [canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="88e8f-114">For more information about the components of this pipeline, and the message flow within this pipeline, see [BTARN Send Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e8f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="88e8f-115">See Also</span></span>  
 <span data-ttu-id="88e8f-116">[Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="88e8f-116">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="88e8f-117">Canalización de envío BTARN</span><span class="sxs-lookup"><span data-stu-id="88e8f-117">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)