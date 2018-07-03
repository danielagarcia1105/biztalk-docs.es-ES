---
title: Componentes de envío y recepción de MLLP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eebc51d23c66fb9dd7047f29982fbcc05a8215f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971805"
---
# <a name="mllp-receive-and-send-components"></a><span data-ttu-id="68f56-102">Componentes de envío y recepción de MLLP</span><span class="sxs-lookup"><span data-stu-id="68f56-102">MLLP Receive and Send Components</span></span>
<span data-ttu-id="68f56-103">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) es compatible con todos los Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tipos de adaptador nativo, incluidos el archivo, HTTP, FTP y SQL.</span><span class="sxs-lookup"><span data-stu-id="68f56-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports all Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] native adapter types, including File, HTTP, SQL, and FTP.</span></span> <span data-ttu-id="68f56-104">Para HL7 mensaje codificado en recibir y enviar, sin embargo, se suele usa el adaptador de MLLP.</span><span class="sxs-lookup"><span data-stu-id="68f56-104">For HL7-encoded message receiving and sending, however, you typically use the MLLP adapter.</span></span> <span data-ttu-id="68f56-105">Este adaptador es un adaptador de socket de TCP/IP que usa el protocolo de capa inferior (MLLP) mínimos.</span><span class="sxs-lookup"><span data-stu-id="68f56-105">This adapter is a TCP/IP socket adapter that uses the Minimal Lower Layer Protocol (MLLP).</span></span> <span data-ttu-id="68f56-106">Este protocolo proporciona integración de mensajes bidireccionales-to-end y de soporte técnico principal aplicación sanitaria.</span><span class="sxs-lookup"><span data-stu-id="68f56-106">This protocol provides bi-directional message support and end-to-end health care application integration.</span></span>  
  
 <span data-ttu-id="68f56-107">Puede configurar el MLLP como un adaptador bidireccional o un adaptador unidireccional del adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="68f56-107">You can configure the MLLP receive adapter as either a two-way adapter or a one-way adapter.</span></span> <span data-ttu-id="68f56-108">Puede configurar el adaptador de envío MLLP como adaptador de envío de una petición-respuesta bidireccional, configurado para recibir la confirmación (ACK) en la misma conexión de socket de adaptador de envío unidireccional o adaptador que no devuelve ningún mensaje de envío unidireccional.</span><span class="sxs-lookup"><span data-stu-id="68f56-108">You can configure the MLLP send adapter as a two-way solicit-response send adapter, a one-way send adapter configured to receive acknowledgments (ACKs) on the same socket connection, or a one-way send adapter that does not return any messages.</span></span> <span data-ttu-id="68f56-109">Al usar bidireccional de petición-respuesta del adaptador MLLP de envío, puede configurar el puerto de recepción para devolver mensajes de confirmación o mensajes de respuesta.</span><span class="sxs-lookup"><span data-stu-id="68f56-109">When you use the two-way solicit-response send MLLP adapter, you can configure the receive port to return either ACKs or response messages.</span></span> <span data-ttu-id="68f56-110">Para obtener ejemplos de MLLP enviarán y adaptadores de recepción, vea [Tutorial de interrogación](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="68f56-110">For examples of MLLP send and receive adapters, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
 <span data-ttu-id="68f56-111">Los mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe o envía en un adaptador MLLP requiere los siguientes contenedores:</span><span class="sxs-lookup"><span data-stu-id="68f56-111">Messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives or sends on an MLLP adapter require the following wrappers:</span></span>  
  
- <span data-ttu-id="68f56-112">\<SB\> carácter de inicio de bloque</span><span class="sxs-lookup"><span data-stu-id="68f56-112">\<SB\> Start Block character</span></span>  
  
- <span data-ttu-id="68f56-113">\<EB\> caracteres de bloque final</span><span class="sxs-lookup"><span data-stu-id="68f56-113">\<EB\> End Block character</span></span>  
  
- <span data-ttu-id="68f56-114">\<CR\> bytes de devolver del carro (opcional)</span><span class="sxs-lookup"><span data-stu-id="68f56-114">\<CR\> Carriage Return Byte (optional)</span></span>  
  
  <span data-ttu-id="68f56-115">Los adaptadores MLLP proporcionan control de errores de falta \<SB\> o \<EB\> contenedores, las conexiones interrumpidas o tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="68f56-115">MLLP adapters provide error handling for missing \<SB\> or \<EB\> wrappers, dropped connections, or timeouts.</span></span> <span data-ttu-id="68f56-116">Con un adaptador MLLP, puede configurar una limitación del número de conexiones.</span><span class="sxs-lookup"><span data-stu-id="68f56-116">With an MLLP adapter, you can configure a limitation on the number of connections.</span></span> <span data-ttu-id="68f56-117">Puede usar una gran variedad de confirmaciones con un adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="68f56-117">You can use an assortment of acknowledgments with an MLLP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f56-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="68f56-118">See Also</span></span>  
 <span data-ttu-id="68f56-119">[Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="68f56-119">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 [<span data-ttu-id="68f56-120">Acelerador de BizTalk para componentes de HL7</span><span class="sxs-lookup"><span data-stu-id="68f56-120">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)