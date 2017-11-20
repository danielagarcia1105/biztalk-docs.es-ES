---
title: "Componentes de envío y recepción de MLLP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab82aa317b205d62b8bd05aff513e80d406b658b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mllp-receive-and-send-components"></a><span data-ttu-id="711af-102">Componentes de envío y recepción de MLLP</span><span class="sxs-lookup"><span data-stu-id="711af-102">MLLP Receive and Send Components</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="711af-103">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) todos los admite [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tipos de adaptador nativo, incluidos el archivo, HTTP, SQL y FTP.</span><span class="sxs-lookup"><span data-stu-id="711af-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports all [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] native adapter types, including File, HTTP, SQL, and FTP.</span></span> <span data-ttu-id="711af-104">Para HL7 mensaje codificado en recibir y enviar, sin embargo, se suele usa el adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="711af-104">For HL7-encoded message receiving and sending, however, you typically use the MLLP adapter.</span></span> <span data-ttu-id="711af-105">Este adaptador es un adaptador de socket de TCP/IP que usa el protocolo de nivel inferior (MLLP) mínimo.</span><span class="sxs-lookup"><span data-stu-id="711af-105">This adapter is a TCP/IP socket adapter that uses the Minimal Lower Layer Protocol (MLLP).</span></span> <span data-ttu-id="711af-106">Este protocolo proporciona integración de aplicaciones sanitaria de soporte técnico y end-to-end de mensajes bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="711af-106">This protocol provides bi-directional message support and end-to-end health care application integration.</span></span>  
  
 <span data-ttu-id="711af-107">Puede configurar el MLLP como un adaptador bidireccional o un adaptador unidireccional del adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="711af-107">You can configure the MLLP receive adapter as either a two-way adapter or a one-way adapter.</span></span> <span data-ttu-id="711af-108">Puede configurar el adaptador de envío MLLP como adaptador de envío de una petición-respuesta bidireccional, un envío unidireccional adaptador configurado para recibir confirmaciones (ACK) en la misma conexión de socket o una unidireccional del adaptador que no devuelve ningún mensaje de envío.</span><span class="sxs-lookup"><span data-stu-id="711af-108">You can configure the MLLP send adapter as a two-way solicit-response send adapter, a one-way send adapter configured to receive acknowledgments (ACKs) on the same socket connection, or a one-way send adapter that does not return any messages.</span></span> <span data-ttu-id="711af-109">Cuando se usa el bidireccional adaptador MLLP de envío de petición-respuesta, puede configurar el puerto de recepción para devolver mensajes de confirmación o mensajes de respuesta.</span><span class="sxs-lookup"><span data-stu-id="711af-109">When you use the two-way solicit-response send MLLP adapter, you can configure the receive port to return either ACKs or response messages.</span></span> <span data-ttu-id="711af-110">Para obtener ejemplos de MLLP enviarán y adaptadores de recepción, consulte [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="711af-110">For examples of MLLP send and receive adapters, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
 <span data-ttu-id="711af-111">Los mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe o envía en un adaptador MLLP requiere los siguientes contenedores:</span><span class="sxs-lookup"><span data-stu-id="711af-111">Messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives or sends on an MLLP adapter require the following wrappers:</span></span>  
  
-   <span data-ttu-id="711af-112">\<SB > caracteres de bloque de inicio</span><span class="sxs-lookup"><span data-stu-id="711af-112">\<SB> Start Block character</span></span>  
  
-   <span data-ttu-id="711af-113">\<EB > caracteres de bloque final</span><span class="sxs-lookup"><span data-stu-id="711af-113">\<EB> End Block character</span></span>  
  
-   <span data-ttu-id="711af-114">\<CR > bytes de devolver del carro (opcional)</span><span class="sxs-lookup"><span data-stu-id="711af-114">\<CR> Carriage Return Byte (optional)</span></span>  
  
 <span data-ttu-id="711af-115">Adaptadores MLLP proporcionan control de errores de falta \<SB > o \<EB > contenedores, las conexiones interrumpidas o tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="711af-115">MLLP adapters provide error handling for missing \<SB> or \<EB> wrappers, dropped connections, or timeouts.</span></span> <span data-ttu-id="711af-116">Con un adaptador MLLP, puede configurar una limitación en el número de conexiones.</span><span class="sxs-lookup"><span data-stu-id="711af-116">With an MLLP adapter, you can configure a limitation on the number of connections.</span></span> <span data-ttu-id="711af-117">Puede usar una gran variedad de confirmaciones con un adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="711af-117">You can use an assortment of acknowledgments with an MLLP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711af-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="711af-118">See Also</span></span>  
 <span data-ttu-id="711af-119">[Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="711af-119">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 [<span data-ttu-id="711af-120">Acelerador de BizTalk para HL7 componentes</span><span class="sxs-lookup"><span data-stu-id="711af-120">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)