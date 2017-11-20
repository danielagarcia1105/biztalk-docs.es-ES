---
title: "FRR puertos de envío de mensajes a los controladores personalizados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6babc312ddad7d77a96e29bc9e59ec9298aa6ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a><span data-ttu-id="f7338-102">FRR puertos de envío de mensajes a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="f7338-102">FRR Send Ports for Messages to the Custom Handlers</span></span>
<span data-ttu-id="f7338-103">Para habilitar a los controladores personalizados para FRR, debe crear una serie de puertos de envío FRR, cada uno de los cuales enruta una copia de un mensaje original de un tipo determinado para los controladores personalizados.</span><span class="sxs-lookup"><span data-stu-id="f7338-103">To enable custom handlers for FRR, you must create a series of FRR send ports, each one of which routes a copy of an original message of a certain type to the custom handlers.</span></span> <span data-ttu-id="f7338-104">Estos puertos de envío deben tienen los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="f7338-104">These send ports must have the following pipeline components:</span></span>  
  
-   <span data-ttu-id="f7338-105">El ensamblador SWIFT en la fase de ensamblado</span><span class="sxs-lookup"><span data-stu-id="f7338-105">The SWIFT assembler in the Assemble stage</span></span>  
  
-   <span data-ttu-id="f7338-106">El componente de canalización SWIFTSendFrrComponent en la fase de codificación</span><span class="sxs-lookup"><span data-stu-id="f7338-106">The SWIFTSendFrrComponent pipeline component in the Encode stage</span></span>  
  
 <span data-ttu-id="f7338-107">Para todos los mensajes excepto los mensajes de SWIFT FINÉS categoría 0 a 9 y que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="f7338-107">For all messages except Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f7338-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="f7338-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
-   <span data-ttu-id="f7338-109">BTS. Operación que se establece en el valor necesario para cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7338-109">BTS.Operation set to the value required for each message type.</span></span> <span data-ttu-id="f7338-110">Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="f7338-110">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  
  
 <span data-ttu-id="f7338-111">Para los mensajes de FIN de SWIFT categoría 0 a 9 y que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="f7338-111">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f7338-112">_SendingServiceTyp ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="f7338-112">_SendingServiceTyp==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f7338-113">_FrrFailed == true</span><span class="sxs-lookup"><span data-stu-id="f7338-113">_FrrFailed==True</span></span>  
  
-   <span data-ttu-id="f7338-114">BTS. Operación ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span><span class="sxs-lookup"><span data-stu-id="f7338-114">BTS.Operation==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f7338-115">_FRRFailedReason se establece en el valor necesario para cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7338-115">_FRRFailedReason set to the value required for each message type.</span></span> <span data-ttu-id="f7338-116">Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="f7338-116">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>