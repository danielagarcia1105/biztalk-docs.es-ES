---
title: "Conciliación de respuesta FIN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- FRR
- FIN Response Reconciliation
- SAA
- NAKs
- FRR, about FRR
- acknowledgements
- FIN Response Reconciliation, about FIN Response Reconciliation
- FIN Response Reconciliation, acknowledgements
ms.assetid: 987b932b-e487-4ca8-acd0-410d71df8e6d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5452dbacb8a9a20c8d2e62d62f6043aaea2d18da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation"></a><span data-ttu-id="c7cb5-102">Conciliación de respuesta FIN</span><span class="sxs-lookup"><span data-stu-id="c7cb5-102">FIN Response Reconciliation</span></span>
<span data-ttu-id="c7cb5-103">La característica de conciliación de respuesta de FIN (FRR) de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconcilia una respuesta FIN con el correspondiente mensaje original enviado por [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7cb5-103">The FIN Response Reconciliation (FRR) feature of [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconciles a FIN response with the corresponding original message sent by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="c7cb5-104">Esto establece el estado del mensaje original y permite [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para tomar medidas en función de ese estado.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-104">This establishes the status of the original message, and enables [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to take steps based upon that status.</span></span> <span data-ttu-id="c7cb5-105">Sin conciliación, esto no sería posible.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-105">Without reconciliation, this would not be possible.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="c7cb5-106">¿sabe que, correctamente (o sin éxito) envía el mensaje original a AAS y tendría la respuesta que recibió de AAS, que indica el estado de la transmisión, pero no sería capaz de realizar la conexión entre los dos.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-106"> would know that it successfully (or unsuccessfully) sent the original message to SAA, and it would have the response that it received from SAA, indicating the status of the transmission, but it would not be able to make the connection between the two.</span></span> <span data-ttu-id="c7cb5-107">FRR establece esa conexión.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-107">FRR establishes that connection.</span></span>  
  
 <span data-ttu-id="c7cb5-108">Las respuestas FIN son confirmaciones (ACK) o confirmaciones negativas (NAKs) enviadas por AAS a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], o enviados por la red SWIFT a AAS y, a continuación, reenvía AAS a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7cb5-108">FIN responses are acknowledgments (ACKs) or negative acknowledgments (NAKs) sent by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], or sent by the SWIFT network to SAA and then forwarded by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="c7cb5-109">La presencia o ausencia de dichas confirmaciones define el estado de negocios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-109">The presence or absence of these acknowledgments defines the business status of the message.</span></span> <span data-ttu-id="c7cb5-110">Puede supervisar este estado a través de informes de supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="c7cb5-110">You can monitor this status through Business Activity Monitoring (BAM) reporting.</span></span>  
  
 <span data-ttu-id="c7cb5-111">También puede implementar un comportamiento de la aplicación personalizada alrededor de FRR.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-111">You can also implement custom application behavior around FRR.</span></span> <span data-ttu-id="c7cb5-112">Un controlador personalizado puede implementar su propia lógica para controlar conjuntos conciliados de respuestas FIN.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-112">A custom handler can implement your own logic for handling reconciled sets of FIN responses.</span></span> <span data-ttu-id="c7cb5-113">Para obtener un ejemplo de un controlador personalizado que procesa los mensajes que se correlacionan FRR con un mensaje MTS21_FIN_ACKNAK NAK, consulte [FRR NAK controlador ejemplo](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c7cb5-113">For an example of a custom handler that processes messages that FRR has correlated with a MTS21_FIN_ACKNAK NAK message, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
 <span data-ttu-id="c7cb5-114">La orquestación FRR se instala de forma predeterminada el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-114">The FRR orchestration is installed by default by the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program.</span></span> <span data-ttu-id="c7cb5-115">Es necesario para configurar el sistema FRR mediante la creación de una canalización de recepción, ubicaciones de recepción y puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-115">You need to configure the FRR system by creating a receive pipeline, receive locations, and send ports.</span></span> <span data-ttu-id="c7cb5-116">También debe configurar FRR para especificar cuánto tiempo debe esperar para NAKs diferidas y para las respuestas en general.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-116">You also need to configure FRR to specify how long it should wait for delayed NAKs, and for responses in general.</span></span> <span data-ttu-id="c7cb5-117">Para obtener más información acerca de la administración y configuración de FRR, consulte [conciliación de respuesta de FIN de configurar](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) y [conciliación de respuesta de FIN de administrar](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).</span><span class="sxs-lookup"><span data-stu-id="c7cb5-117">For more information about FRR configuration and administration, see [Configuring FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) and [Administering FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="c7cb5-118">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="c7cb5-118">This section contains:</span></span>  
  
-   [<span data-ttu-id="c7cb5-119">Tipos de respuesta FIN</span><span class="sxs-lookup"><span data-stu-id="c7cb5-119">FIN Response Types</span></span>](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [<span data-ttu-id="c7cb5-120">Procesamiento de FRR</span><span class="sxs-lookup"><span data-stu-id="c7cb5-120">FRR Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [<span data-ttu-id="c7cb5-121">Orquestación de FRR</span><span class="sxs-lookup"><span data-stu-id="c7cb5-121">FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [<span data-ttu-id="c7cb5-122">FRR ubicación de recepción para los mensajes de la aplicación de Back-End</span><span class="sxs-lookup"><span data-stu-id="c7cb5-122">FRR Receive Location for Messages from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="c7cb5-123">Puerto de envío FRR mensajes SWIFT</span><span class="sxs-lookup"><span data-stu-id="c7cb5-123">FRR Send Port for Messages to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [<span data-ttu-id="c7cb5-124">FRR ubicación de recepción para mensajes de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="c7cb5-124">FRR Receive Location for Messages from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [<span data-ttu-id="c7cb5-125">FRR puertos de envío de mensajes a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="c7cb5-125">FRR Send Ports for Messages to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [<span data-ttu-id="c7cb5-126">Control conciliado conjuntos de mensajes</span><span class="sxs-lookup"><span data-stu-id="c7cb5-126">Handling Reconciled Message Sets</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)