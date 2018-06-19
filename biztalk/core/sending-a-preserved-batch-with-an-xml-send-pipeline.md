---
title: Enviar un lote conservado con un documento XML de canalización de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14bd61538398bb11967cbbe750a4fadc016a5168
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269828"
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a><span data-ttu-id="c083f-102">Enviar un lote conservado con una canalización de envío XML</span><span class="sxs-lookup"><span data-stu-id="c083f-102">Sending a Preserved Batch with an XML Send Pipeline</span></span>
<span data-ttu-id="c083f-103">Por lo general, se envía un lote conservado mediante una canalización de envío EDI.</span><span class="sxs-lookup"><span data-stu-id="c083f-103">Normally, a preserved batch is sent using an EDI send pipeline.</span></span> <span data-ttu-id="c083f-104">No obstante, se puede usar una canalización de envío XML para enviar un lote conservado.</span><span class="sxs-lookup"><span data-stu-id="c083f-104">However, you can also use an XML send pipeline to send a preserved batch.</span></span> <span data-ttu-id="c083f-105">Puesto que el lote conservado que se genera y se coloca en el cuadro de mensajes a través de la canalización de recepción EDI se encuentra en formato XML, la canalización de envío XML debe pasar junto con el lote en formato XML.</span><span class="sxs-lookup"><span data-stu-id="c083f-105">Since the preserved batch that is generated and dropped in the MessageBox by the EDI receive pipeline is in the XML format, the XML send pipeline would pass along the batch in XML format.</span></span>  
  
 <span data-ttu-id="c083f-106">Para enviar un lote conservado mediante la canalización de envío XML, se debe implementar un proyecto con el esquema por lotes aplicable y los esquemas de documento para cada tipo de mensaje en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="c083f-106">To send a preserved batch using the XML send pipeline, you have to deploy a project with the applicable batch schema and the document schemas for each message type in the interchange.</span></span> <span data-ttu-id="c083f-107">Además, también debe cambiar el espacio de nombres del esquema por lotes que implementa en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c083f-107">In addition, you also have to change the namespace for the batch schema that you deploy in the project.</span></span> <span data-ttu-id="c083f-108">Si no lo hace, el espacio de nombres del archivo XML por lotes conservado no se corresponderá con el espacio de nombres del esquema por lotes.</span><span class="sxs-lookup"><span data-stu-id="c083f-108">If you do not do so, the namespace in the preserved batch XML file would not correspond to the namespace for the batch schema.</span></span> <span data-ttu-id="c083f-109">Debe cambiar el espacio de nombres del esquema por lotes como se muestra en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="c083f-109">You have to change the namespace for the batch schema as shown in the following table:</span></span>  
  
|<span data-ttu-id="c083f-110">Para este tipo de codificación:</span><span class="sxs-lookup"><span data-stu-id="c083f-110">For this encoding type:</span></span>|<span data-ttu-id="c083f-111">Cambie este espacio de nombres en el esquema por lotes:</span><span class="sxs-lookup"><span data-stu-id="c083f-111">Change this namespace in the batch schema:</span></span>|<span data-ttu-id="c083f-112">En el siguiente espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="c083f-112">To the following namespace:</span></span>|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|<span data-ttu-id="c083f-113">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="c083f-113">EDIFACT</span></span>|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|<span data-ttu-id="c083f-114">X12</span><span class="sxs-lookup"><span data-stu-id="c083f-114">X12</span></span>|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 <span data-ttu-id="c083f-115">Esto no es un problema con el ensamblador EDI.</span><span class="sxs-lookup"><span data-stu-id="c083f-115">This is not an issue with the EDI Assembler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c083f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c083f-116">See Also</span></span>  
 [<span data-ttu-id="c083f-117">Configuración de lotes de EDI</span><span class="sxs-lookup"><span data-stu-id="c083f-117">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)