---
title: Problemas conocidos del adaptador MLLP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cbae1bf4bf04e2ecf4e643ad5107b9e0fd70f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206060"
---
# <a name="mllp-adapter-known-issues"></a><span data-ttu-id="68d91-102">Problemas conocidos del adaptador MLLP</span><span class="sxs-lookup"><span data-stu-id="68d91-102">MLLP Adapter Known Issues</span></span>
<span data-ttu-id="68d91-103">Esta sección contiene información útil que puede ayudar a evitar errores del adaptador de protocolo de nivel inferior mínimo (MLLP).</span><span class="sxs-lookup"><span data-stu-id="68d91-103">This section contains useful information that may help you avoid Minimal Lower Layer Protocol (MLLP) adapter errors.</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="68d91-104">Adaptador MLLP bidireccional podría no detectar un problema con una confirmación</span><span class="sxs-lookup"><span data-stu-id="68d91-104">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="68d91-105">Cuando [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) recibe una confirmación (ACK) en un adaptador MLLP bidireccional, el adaptador realiza una validación ligera en la confirmación para determinar su validez.</span><span class="sxs-lookup"><span data-stu-id="68d91-105">When [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) receives an acknowledgment (ACK) on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="68d91-106">Si se encuentra sea válido, se extrae el campo MSA1 y dependiendo de su valor, el adaptador de reintentos, suspende o elimina el mensaje original a la que se responde la confirmación.</span><span class="sxs-lookup"><span data-stu-id="68d91-106">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="68d91-107">Sin embargo, dado que la validación realizada por el adaptador no es una validación completa, es posible que el adaptador no detectan un problema con la confirmación.</span><span class="sxs-lookup"><span data-stu-id="68d91-107">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="68d91-108">Por ejemplo, el adaptador puede determinar que la confirmación es válida y eliminar el mensaje original, mientras que la canalización podría determinar que la confirmación no tenía el formato correcto y suspender el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="68d91-108">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="68d91-109">Contadores de rendimiento de MLLP no cuentan confirmaciones</span><span class="sxs-lookup"><span data-stu-id="68d91-109">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="68d91-110">Una medida de rendimiento es el número de mensajes procesados por un adaptador MLLP, como se indica en los contadores de rendimiento de MLLP.</span><span class="sxs-lookup"><span data-stu-id="68d91-110">One measure of performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="68d91-111">Este contador mide el número de mensajes recibidos o transmitida.</span><span class="sxs-lookup"><span data-stu-id="68d91-111">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="68d91-112">Sin embargo, el recuento no mide el número de confirmaciones recibidos o enviados.</span><span class="sxs-lookup"><span data-stu-id="68d91-112">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a><span data-ttu-id="68d91-113">No se garantiza que los nombres de conexión de adaptador MLLP ser único</span><span class="sxs-lookup"><span data-stu-id="68d91-113">MLLP adapter connection names are not guaranteed to be unique</span></span>  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="68d91-114">no garantiza la exclusividad del nombre de conexión especificado en las páginas de propiedades de un adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="68d91-114"> does not guarantee the uniqueness of the connection name entered in the property pages of an MLLP adapter.</span></span> <span data-ttu-id="68d91-115">Asegurarse de esa conexión descriptiva y relevante nombres se escriben en este campo obligatorio.</span><span class="sxs-lookup"><span data-stu-id="68d91-115">Ensure that descriptive and relevant connection names are entered in this required field.</span></span> <span data-ttu-id="68d91-116">Uso de nombres de conexión que representan las aplicaciones de línea de negocio puede ser útil al tratar de comprender el comportamiento de la conexión.</span><span class="sxs-lookup"><span data-stu-id="68d91-116">Using connection names that represent line-of-business applications can be useful when trying to understand the behavior of the connection.</span></span> <span data-ttu-id="68d91-117">Por ejemplo, los contadores PerfMon utilizar el nombre de la conexión.</span><span class="sxs-lookup"><span data-stu-id="68d91-117">For example, PerfMon counters use the connection name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68d91-118">BTAHL7 asegurar la exclusividad de las ubicaciones de recepción o nombres de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="68d91-118">BTAHL7 does ensure the uniqueness of receive locations or send port names.</span></span>  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a><span data-ttu-id="68d91-119">Adaptadores MLLP bidireccionales no envían confirmación ACK para todos los mensajes en un lote</span><span class="sxs-lookup"><span data-stu-id="68d91-119">Two-way MLLP adapters do not send Commit ACKs for all messages in a batch</span></span>  
 <span data-ttu-id="68d91-120">Al configurar cada mensaje en un lote que se va a generar una confirmación de confirmación y el sistema envía el lote a un MLLP bidireccional del adaptador de recepción, el adaptador sólo enviará la confirmación de confirmación correspondiente al primer mensaje en el lote.</span><span class="sxs-lookup"><span data-stu-id="68d91-120">When you configure each message in a batch to generate a Commit ACK, and the system sends the batch to a two-way MLLP receive adapter, the adapter will only send the Commit ACK corresponding to the first message in the batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68d91-121">Se recomienda que utilice un adaptador MLLP unidireccional para el transporte de lotes.</span><span class="sxs-lookup"><span data-stu-id="68d91-121">It is recommended that you use a one-way MLLP adapter to transport batches.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="68d91-122">NAK generado por el adaptador MLLP bidireccional</span><span class="sxs-lookup"><span data-stu-id="68d91-122">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="68d91-123">Cuando un adaptador MLLP bidireccional suspende cualquier mensaje, el adaptador MLLP genera un NAK (confirmación negativa) y lo coloca en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="68d91-123">When a two-way MLLP adapter suspends any message, the MLLP adapter generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="68d91-124">Esto puede ser un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="68d91-124">This may be unexpected behavior.</span></span> <span data-ttu-id="68d91-125">Puede que desee quitar el NAK desde la base de datos de cuadro de mensajes o asignar a otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="68d91-125">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a><span data-ttu-id="68d91-126">Adaptador MLLP bidireccional sólo es compatible con el formato del mensaje 2.X</span><span class="sxs-lookup"><span data-stu-id="68d91-126">Two-way MLLP adapter only supports the 2.X message format</span></span>  
 <span data-ttu-id="68d91-127">El adaptador MLLP bidireccional admite actualmente solo el formato del mensaje 2.X.</span><span class="sxs-lookup"><span data-stu-id="68d91-127">The two-way MLLP adapter currently supports only the 2.X message format.</span></span>  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a><span data-ttu-id="68d91-128">El adaptador MLLP bidireccional no admite confirmaciones estáticas</span><span class="sxs-lookup"><span data-stu-id="68d91-128">Two-way MLLP adapter does not support static acknowledgments</span></span>  
 <span data-ttu-id="68d91-129">La de envío bidireccional adaptador no admite el procesamiento de confirmaciones estáticas.</span><span class="sxs-lookup"><span data-stu-id="68d91-129">The two-way send adapter does not support processing static acknowledgments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d91-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="68d91-130">See Also</span></span>  
 [<span data-ttu-id="68d91-131">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="68d91-131">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)