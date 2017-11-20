---
title: "Componente de canalización de desensamblador de BizTalk Framework | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ab54ddb9ef0b5fa389e6716fc4426978dcbd7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="e935c-102">Componente de canalización de desensamblador de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="e935c-102">BizTalk Framework Disassembler Pipeline Component</span></span>
<span data-ttu-id="e935c-103">El componente de canalización de desensamblador de BizTalk Framework analiza datos XML y determina si contienen carga de mensajería basada en BizTalk Framework.</span><span class="sxs-lookup"><span data-stu-id="e935c-103">The BizTalk Framework Disassembler pipeline component parses XML data and determines whether it contains a BizTalk Framework-based messaging payload.</span></span> <span data-ttu-id="e935c-104">El componente de canalización guarda el contexto del mensaje y se crea uno nuevo con la propiedad de BizTalk Framework que haya que generar.</span><span class="sxs-lookup"><span data-stu-id="e935c-104">The pipeline component saves the message context, and a new message context is created with the BizTalk Framework property that needs to be generated.</span></span> <span data-ttu-id="e935c-105">Esta propiedad se utiliza para enrutar el mensaje al controlador de entrada de BizTalk Framework de forma que pueda recibir el mensaje que procesar.</span><span class="sxs-lookup"><span data-stu-id="e935c-105">This property is used to route the message to the BizTalk Framework inbound handler, so it can receive the message to process.</span></span>  
  
 <span data-ttu-id="e935c-106">El componente de canalización de desensamblador de BizTalk Framework proporciona una confirmación para el mensaje generado si el remitente solicitó una mediante el encabezado deliverReceiptRequest dentro del sobre de BizTalk Framework.</span><span class="sxs-lookup"><span data-stu-id="e935c-106">The BizTalk Framework Disassembler pipeline component generates an acknowledgment for the generated message if the sender requested one using the deliverReceiptRequest header within the BizTalk Framework envelope.</span></span> <span data-ttu-id="e935c-107">Esto lo controla la propiedad generar notificación de entrega del componente de canalización de ensamblador de BizTalk Framework.</span><span class="sxs-lookup"><span data-stu-id="e935c-107">This is controlled by the generate delivery receipt property in the BizTalk Framework Assembler pipeline component.</span></span> <span data-ttu-id="e935c-108">Para obtener más información sobre el marco de trabajo de BizTalk, consulte [componente de canalización de ensamblador de BizTalk Framework](../core/biztalk-framework-assembler-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="e935c-108">For more information about the BizTalk Framework, see [BizTalk Framework Assembler Pipeline Component](../core/biztalk-framework-assembler-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="e935c-109">Para obtener información sobre cómo configurar el componente de canalización de desensamblador de BizTalk Framework y crear la orquestación, consulte [cómo configurar el componente de canalización de desensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="e935c-109">For information about configuring the BizTalk Framework Disassembler pipeline component and creating the orchestration, see [How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e935c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e935c-110">See Also</span></span>  
 <span data-ttu-id="e935c-111">[Cómo configurar el componente de canalización de desensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e935c-111">[How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="e935c-112">Componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="e935c-112">Pipeline Components</span></span>](../core/pipeline-components.md)