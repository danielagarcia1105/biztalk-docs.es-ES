---
title: Fragmentado por lotes entrantes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0807bbe83ea2f477a7e1625488ebbecf578f3adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204892"
---
# <a name="fragmented-inbound-batch"></a><span data-ttu-id="6dd9b-102">Fragmentados por lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="6dd9b-102">Fragmented Inbound Batch</span></span>
<span data-ttu-id="6dd9b-103">Puede configurar [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para recibir un lote de mensajes, extraer los mensajes del lote y, a continuación, enrutar los mensajes individuales en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-103">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive a message batch, extract the messages from the batch, and then route the individual messages to the destination system.</span></span> <span data-ttu-id="6dd9b-104">Si habilita la fragmentación, los fragmentos por lotes entrantes en mensajes individuales; en caso contrario, se procesa el lote y se enruta como un único 'batch' o el intercambio.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-104">If you enable fragmentation, the inbound batch fragments into individual messages; otherwise, the batch is processed and routed as a single 'batch' or interchange.</span></span> <span data-ttu-id="6dd9b-105">Use el Explorador de configuración de BTAHL7 para habilitar el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-105">You use BTAHL7 Configuration Explorer to enable batching.</span></span> <span data-ttu-id="6dd9b-106">Para obtener más información acerca de cómo habilitar el procesamiento por lotes, vea [configurar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span><span class="sxs-lookup"><span data-stu-id="6dd9b-106">For more information about enabling batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
 <span data-ttu-id="6dd9b-107">A continuación describen un escenario típico por lotes entrantes fragmentados:</span><span class="sxs-lookup"><span data-stu-id="6dd9b-107">The following describes a typical fragmented inbound batch scenario:</span></span>  
  
1.  <span data-ttu-id="6dd9b-108">Una aplicación de línea de negocio, que se ejecuta en el sistema A, envía un lote de mensajes a BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-108">A line-of-business application, running on System A, sends a message batch to BTAHL7.</span></span>  
  
     <span data-ttu-id="6dd9b-109">Mensajes por lotes pueden estar en dos formatos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-109">Batch messages can be in two different formats.</span></span> <span data-ttu-id="6dd9b-110">BTAHL7 puede procesar los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="6dd9b-110">BTAHL7 can process the following formats:</span></span>  
  
    -   <span data-ttu-id="6dd9b-111">Formato 1: Incluye un encabezado de archivo y par de finalizador (FHS/FTS) y uno o más encabezado de lote y finalizadores (BHS/BTS).</span><span class="sxs-lookup"><span data-stu-id="6dd9b-111">Format 1: Includes one file header and trailer (FHS/FTS) pair and one or more batch header and trailers (BHS/BTS).</span></span>  
  
        ```  
        FHS  
        BHS  
        MSH  
        .............  
        MSH  
        ...........  
        BTS  
        BHS  
        MSH  
        ..............  
        MSH  
        ...............  
        BTS  
        FTS  
        ```  
  
    -   <span data-ttu-id="6dd9b-112">Formato 2: No contiene contenedores de archivos y por lotes de HL7 definido y suspende una serie de mensajes en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-112">Format 2: Does not contain HL7 defined file and batch wrappers, and suspends a series are messages in a stream.</span></span>  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  <span data-ttu-id="6dd9b-113">BTAHL7 crea los mensajes individuales del lote y, a continuación, comprueba los mensajes individuales con los esquemas adecuados.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-113">BTAHL7 creates individual messages from the batch and then verifies the individual messages against the appropriate schemas.</span></span>  
  
3.  <span data-ttu-id="6dd9b-114">BTAHL7 envía un mensaje de confirmación independiente en el sistema A para cada mensaje extraído del lote.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-114">BTAHL7 sends a separate acknowledgment message to System A for each message extracted from the batch.</span></span>  
  
4.  <span data-ttu-id="6dd9b-115">BTAHL7 enruta los mensajes individuales en el sistema de destino en función de la información de enrutamiento en los mensajes individuales, en lugar de en el encabezado del mensaje por lotes.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-115">BTAHL7 routes the individual messages to the destination system based on the routing information in the individual messages, rather than the message batch header.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6dd9b-116">BTAHL7 no valida los encabezados/finalizadores por lotes y el archivo cuando la **FHS3** campo (entidad de envío) contiene un socio comercial que tenga habilitada la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="6dd9b-116">BTAHL7 does not validate batch and file headers/trailers when the **FHS3** field (sending party) contains a trading partner that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd9b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dd9b-117">See Also</span></span>  
 [<span data-ttu-id="6dd9b-118">Configurar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="6dd9b-118">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)