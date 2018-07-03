---
title: Puertos de envío de FRR para mensajes a los controladores personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8ba2b085268f2c0c272b81b27768db716b63c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996157"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a><span data-ttu-id="9ba86-102">Puertos de envío de FRR para mensajes a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="9ba86-102">FRR Send Ports for Messages to the Custom Handlers</span></span>
<span data-ttu-id="9ba86-103">Para habilitar los controladores personalizados para FRR, debe crear una serie de puertos de envío FRR, cada uno de los cuales enruta una copia de un mensaje original de un tipo determinado a los controladores personalizados.</span><span class="sxs-lookup"><span data-stu-id="9ba86-103">To enable custom handlers for FRR, you must create a series of FRR send ports, each one of which routes a copy of an original message of a certain type to the custom handlers.</span></span> <span data-ttu-id="9ba86-104">Estos puertos de envío deben los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="9ba86-104">These send ports must have the following pipeline components:</span></span>  

- <span data-ttu-id="9ba86-105">En la fase de ensamblado del ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="9ba86-105">The SWIFT assembler in the Assemble stage</span></span>  

- <span data-ttu-id="9ba86-106">El componente de canalización SWIFTSendFrrComponent en la fase de codificación</span><span class="sxs-lookup"><span data-stu-id="9ba86-106">The SWIFTSendFrrComponent pipeline component in the Encode stage</span></span>  

  <span data-ttu-id="9ba86-107">Para todos los mensajes excepto los mensajes de FIN de SWIFT categoría 0 al 9 que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="9ba86-107">For all messages except Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9ba86-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="9ba86-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  

- <span data-ttu-id="9ba86-109">BTS. Operación establece en el valor necesario para cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9ba86-109">BTS.Operation set to the value required for each message type.</span></span> <span data-ttu-id="9ba86-110">Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="9ba86-110">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  

  <span data-ttu-id="9ba86-111">Para los mensajes de categoría de 0 a 9 SWIFT FIN que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="9ba86-111">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9ba86-112">_SendingServiceTyp ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="9ba86-112">_SendingServiceTyp==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9ba86-113">_FrrFailed == true</span><span class="sxs-lookup"><span data-stu-id="9ba86-113">_FrrFailed==True</span></span>  

- <span data-ttu-id="9ba86-114">BTS. Operación ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span><span class="sxs-lookup"><span data-stu-id="9ba86-114">BTS.Operation==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9ba86-115">_FRRFailedReason establecido en el valor necesario para cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9ba86-115">_FRRFailedReason set to the value required for each message type.</span></span> <span data-ttu-id="9ba86-116">Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="9ba86-116">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>
