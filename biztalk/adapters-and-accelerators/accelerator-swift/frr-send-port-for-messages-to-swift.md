---
title: "Puerto de envío FRR mensajes SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a442b45f57009b839b4e184ef9662b253ba32b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-port-for-messages-to-swift"></a><span data-ttu-id="106e7-102">Puerto de envío FRR mensajes SWIFT</span><span class="sxs-lookup"><span data-stu-id="106e7-102">FRR Send Port for Messages to SWIFT</span></span>
<span data-ttu-id="106e7-103">Para habilitar la conciliación de respuesta FIN (FRR), debe configurar un puerto de envío FRR que envía un mensaje a AAS a través del adaptador de BizTalk para MQSeries.</span><span class="sxs-lookup"><span data-stu-id="106e7-103">To enable FIN response reconciliation (FRR), you must set up an FRR send port that sends a message to SAA through the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="106e7-104">Este rutas de puerto de envío un mensaje a través de un FRR personalizado componente de canalización que debe crear con los siguientes componentes de canalización de envío:</span><span class="sxs-lookup"><span data-stu-id="106e7-104">This send port routes a message through a custom FRR send pipeline component that you must create with the following pipeline components:</span></span>  
  
-   <span data-ttu-id="106e7-105">El ensamblador SWIFT en la fase de ensamblado</span><span class="sxs-lookup"><span data-stu-id="106e7-105">The SWIFT assembler in the Assemble stage</span></span>  
  
-   <span data-ttu-id="106e7-106">El componente de canalización SWIFTAsmFrrMQSeriesHelper en la fase de codificación</span><span class="sxs-lookup"><span data-stu-id="106e7-106">The SWIFTAsmFrrMQSeriesHelper pipeline component in the Encode stage</span></span>  
  
 <span data-ttu-id="106e7-107">El componente de canalización SWIFTAsmFrrMQSeriesHelper establece la propiedad MQMD_MsgID del mensaje saliente en el valor de la propiedad FRRCorrelationToken.</span><span class="sxs-lookup"><span data-stu-id="106e7-107">The SWIFTAsmFrrMQSeriesHelper pipeline component sets the MQMD_MsgID property of the outgoing message to the value of the FRRCorrelationToken property.</span></span> <span data-ttu-id="106e7-108">También asigna y promociona otras propiedades de contexto necesario a partir de "MQ" con los valores establecidos en el tiempo de diseño de canalización.</span><span class="sxs-lookup"><span data-stu-id="106e7-108">It also assigns and promotes any other required context properties starting with "MQ" with values set at the pipeline design time.</span></span> <span data-ttu-id="106e7-109">La canalización de envío incluye cada propiedad definida para MQSeries como una propiedad configurable.</span><span class="sxs-lookup"><span data-stu-id="106e7-109">The send pipeline includes each property defined for MQSeries as a configurable property.</span></span> <span data-ttu-id="106e7-110">Cada valor predeterminado es "No usado".</span><span class="sxs-lookup"><span data-stu-id="106e7-110">Each value defaults to "Not Used".</span></span>  
  
 <span data-ttu-id="106e7-111">El puerto de envío controla los mensajes que tienen [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == False y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND == True.</span><span class="sxs-lookup"><span data-stu-id="106e7-111">The send port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="106e7-112">El mecanismo de transporte es el adaptador de BizTalk para MQSeries.</span><span class="sxs-lookup"><span data-stu-id="106e7-112">The transport mechanism is the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="106e7-113">Para obtener información acerca de las propiedades de transporte, como el tamaño de la fragmentación, consulte la documentación de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="106e7-113">For information about the transport properties, such as the fragmentation size, see the MQSeries documentation.</span></span>