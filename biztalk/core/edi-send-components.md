---
title: Componentes de envío EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5520a0c1dd0a6ef7e42818314a9f87733aebcb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239932"
---
# <a name="edi-send-components"></a><span data-ttu-id="4ace2-102">Componentes de envío de EDI</span><span class="sxs-lookup"><span data-stu-id="4ace2-102">EDI Send Components</span></span>
<span data-ttu-id="4ace2-103">La canalización y los componentes de canalización descritos en este tema procesan los mensajes EDI que no son mensajes EDI o AS2.</span><span class="sxs-lookup"><span data-stu-id="4ace2-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="4ace2-104">Para obtener información sobre el envío de EDI y AS2 o mensajes que no sean EDI o AS2, vea [componentes de envío de AS2](../core/as2-send-components.md).</span><span class="sxs-lookup"><span data-stu-id="4ace2-104">For information about the sending of EDI/AS2 or non-EDI/AS2 messages, see [AS2 Send Components](../core/as2-send-components.md).</span></span> <span data-ttu-id="4ace2-105">Tenga en cuenta que los componentes de envío de AS2 realizan procesamiento de EDI además del de AS2.</span><span class="sxs-lookup"><span data-stu-id="4ace2-105">Note that AS2 send components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-send-pipeline"></a><span data-ttu-id="4ace2-106">Canalización de envío EDI</span><span class="sxs-lookup"><span data-stu-id="4ace2-106">EDI Send Pipeline</span></span>  
 <span data-ttu-id="4ace2-107">La mayor parte del procesamiento de envío de EDI se realiza en la siguiente canalización EDISend.</span><span class="sxs-lookup"><span data-stu-id="4ace2-107">EDI send processing is performed in the following EDISend pipeline.</span></span> <span data-ttu-id="4ace2-108">Esta canalización se instala en `Microsoft.BizTalk.Edi.EdiPipelines.dll`, en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ace2-108">This pipeline is installed in `Microsoft.BizTalk.Edi.EdiPipelines.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="4ace2-109">**Canalización EDISend**</span><span class="sxs-lookup"><span data-stu-id="4ace2-109">**EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="4ace2-110">Esta canalización genera y envía mensajes EDI.</span><span class="sxs-lookup"><span data-stu-id="4ace2-110">This pipeline generates and sends EDI messages.</span></span> <span data-ttu-id="4ace2-111">No procesa mensajes EDI con codificación AS2 recibidos a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="4ace2-111">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="4ace2-112">El procesamiento de los mensajes EDI con codificación AS2 se realiza mediante una canalización AS2.</span><span class="sxs-lookup"><span data-stu-id="4ace2-112">Processing of AS2-encoded EDI messages is performed by an AS2 pipeline.</span></span> <span data-ttu-id="4ace2-113">Las canalizaciones de envío AS2 utilizan los mismos componentes para procesar mensajes EDI que utilizan las canalizaciones EDI.</span><span class="sxs-lookup"><span data-stu-id="4ace2-113">The AS2 send pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ace2-114">La ejecución de la canalización EDISend desde una orquestación no está admitida.</span><span class="sxs-lookup"><span data-stu-id="4ace2-114">Running the EDISend pipeline from an orchestration is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ace2-115">La canalización AS2EDISend genera y envía los mensajes EDI a través de transporte AS2.</span><span class="sxs-lookup"><span data-stu-id="4ace2-115">The AS2EDISend pipeline generates and sends EDI messages over AS2 transport.</span></span> <span data-ttu-id="4ace2-116">Para obtener más información, consulte [componentes de envío de AS2](../core/as2-send-components.md).</span><span class="sxs-lookup"><span data-stu-id="4ace2-116">For more information, see [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
 <span data-ttu-id="4ace2-117">La canalización consta del componente de canalización del ensamblador EDI:</span><span class="sxs-lookup"><span data-stu-id="4ace2-117">The pipeline consists of the EDI Assembler pipeline component:</span></span>  
  
## <a name="edi-send-pipeline-component"></a><span data-ttu-id="4ace2-118">Componente de la canalización de envío EDI</span><span class="sxs-lookup"><span data-stu-id="4ace2-118">EDI Send Pipeline Component</span></span>  
 <span data-ttu-id="4ace2-119">La canalización EDISend usa el componente de canalización del ensamblador EDI.</span><span class="sxs-lookup"><span data-stu-id="4ace2-119">The EDISend pipeline uses the EDI Assembler pipeline component.</span></span> <span data-ttu-id="4ace2-120">Este componente se instala en `Microsoft.BizTalk.Edi.PipelineComponents.dll` en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]componentes de canalización\\.</span><span class="sxs-lookup"><span data-stu-id="4ace2-120">This component is installed in `Microsoft.BizTalk.Edi.PipelineComponents.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="4ace2-121">El ensamblador EDI realiza más procesamiento de intercambios con codificación EDI en la canalización EDISend.</span><span class="sxs-lookup"><span data-stu-id="4ace2-121">The EDI Assembler performs most processing of EDI-encoded interchanges in the EDISend Pipeline.</span></span> <span data-ttu-id="4ace2-122">Para obtener información acerca de cómo el ensamblador EDI procesa mensajes EDI, vea [cómo funciona el de ensamblador de EDI](../core/how-the-edi-assembler-works.md).</span><span class="sxs-lookup"><span data-stu-id="4ace2-122">For information about how the EDI Assembler processes EDI messages, see [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>