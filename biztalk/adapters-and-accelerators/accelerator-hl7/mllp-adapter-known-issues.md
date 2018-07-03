---
title: Problemas conocidos del adaptador MLLP | Microsoft Docs
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
ms.openlocfilehash: cb90c62baebb8fc73b939c0a3ea20eb85e9b0e28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970837"
---
# <a name="mllp-adapter-known-issues"></a><span data-ttu-id="2cba8-102">Problemas conocidos del adaptador MLLP</span><span class="sxs-lookup"><span data-stu-id="2cba8-102">MLLP Adapter Known Issues</span></span>
<span data-ttu-id="2cba8-103">Esta sección contiene información útil que puede ayudarle a evitar errores del adaptador de protocolo de nivel inferior mínimo (MLLP).</span><span class="sxs-lookup"><span data-stu-id="2cba8-103">This section contains useful information that may help you avoid Minimal Lower Layer Protocol (MLLP) adapter errors.</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="2cba8-104">Adaptador MLLP bidireccional podría no detectar un problema con una confirmación</span><span class="sxs-lookup"><span data-stu-id="2cba8-104">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="2cba8-105">Cuando el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) recibe una confirmación (ACK) en un adaptador de MLLP bidireccional, el adaptador realiza una validación ligera en la confirmación para determinar su validez.</span><span class="sxs-lookup"><span data-stu-id="2cba8-105">When Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) receives an acknowledgment (ACK) on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="2cba8-106">Si se encuentra sea válido, se extrae el campo MSA1 y vuelve a intentar según su valor, el adaptador, suspende o elimina el mensaje original a la que se responde la confirmación.</span><span class="sxs-lookup"><span data-stu-id="2cba8-106">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="2cba8-107">Sin embargo, puesto que la validación realizada por el adaptador no es una validación completa, es posible que el adaptador no detecta un problema con la confirmación.</span><span class="sxs-lookup"><span data-stu-id="2cba8-107">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="2cba8-108">Por ejemplo, el adaptador podría determinar que la confirmación es válida y eliminar el mensaje original, mientras que la canalización podría determinar que la confirmación no tenía el formato correcto y suspender el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="2cba8-108">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="2cba8-109">Contadores de rendimiento de MLLP no cuentan confirmaciones</span><span class="sxs-lookup"><span data-stu-id="2cba8-109">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="2cba8-110">Una medida de rendimiento es el número de mensajes procesados por un adaptador MLLP, como se indica en los contadores de rendimiento de MLLP.</span><span class="sxs-lookup"><span data-stu-id="2cba8-110">One measure of performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="2cba8-111">Este recuento mide el número de mensajes recibidos o transmitir.</span><span class="sxs-lookup"><span data-stu-id="2cba8-111">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="2cba8-112">Sin embargo, el recuento no mide el número de confirmaciones recibidos o enviados.</span><span class="sxs-lookup"><span data-stu-id="2cba8-112">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a><span data-ttu-id="2cba8-113">Nombres de conexión del adaptador MLLP se garantiza que no sean únicos</span><span class="sxs-lookup"><span data-stu-id="2cba8-113">MLLP adapter connection names are not guaranteed to be unique</span></span>  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="2cba8-114"> no garantiza la exclusividad del nombre de conexión especificado en las páginas de propiedades de un adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="2cba8-114"> does not guarantee the uniqueness of the connection name entered in the property pages of an MLLP adapter.</span></span> <span data-ttu-id="2cba8-115">Asegúrese de esa conexión descriptiva y relevante se especifican los nombres en este campo obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2cba8-115">Ensure that descriptive and relevant connection names are entered in this required field.</span></span> <span data-ttu-id="2cba8-116">Uso de nombres de conexión que representan las aplicaciones de línea de negocio puede ser útil al tratar de comprender el comportamiento de la conexión.</span><span class="sxs-lookup"><span data-stu-id="2cba8-116">Using connection names that represent line-of-business applications can be useful when trying to understand the behavior of the connection.</span></span> <span data-ttu-id="2cba8-117">Por ejemplo, contadores PerfMon use el nombre de la conexión.</span><span class="sxs-lookup"><span data-stu-id="2cba8-117">For example, PerfMon counters use the connection name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cba8-118">BTAHL7 garantiza la unicidad de las ubicaciones de recepción o nombres de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="2cba8-118">BTAHL7 does ensure the uniqueness of receive locations or send port names.</span></span>  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a><span data-ttu-id="2cba8-119">Adaptadores MLLP bidireccionales no envían confirmaciones de confirmación para todos los mensajes en un lote</span><span class="sxs-lookup"><span data-stu-id="2cba8-119">Two-way MLLP adapters do not send Commit ACKs for all messages in a batch</span></span>  
 <span data-ttu-id="2cba8-120">Al configurar cada mensaje en un lote para generar una confirmación de confirmación y el sistema envía el lote al adaptador de recepción de un MLLP bidireccional, el adaptador sólo enviará la confirmación de confirmación correspondiente al primer mensaje en el lote.</span><span class="sxs-lookup"><span data-stu-id="2cba8-120">When you configure each message in a batch to generate a Commit ACK, and the system sends the batch to a two-way MLLP receive adapter, the adapter will only send the Commit ACK corresponding to the first message in the batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cba8-121">Se recomienda que use un adaptador de MLLP unidireccional para el transporte de lotes.</span><span class="sxs-lookup"><span data-stu-id="2cba8-121">It is recommended that you use a one-way MLLP adapter to transport batches.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="2cba8-122">NAK generado por el adaptador MLLP bidireccional</span><span class="sxs-lookup"><span data-stu-id="2cba8-122">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="2cba8-123">Cuando un adaptador de MLLP bidireccional suspende cualquier mensaje, el adaptador MLLP genera un NAK (confirmación negativa) y lo coloca en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2cba8-123">When a two-way MLLP adapter suspends any message, the MLLP adapter generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="2cba8-124">Esto puede ser un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="2cba8-124">This may be unexpected behavior.</span></span> <span data-ttu-id="2cba8-125">Es posible que desee quitar el NAK de la base de datos o asignarla a otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="2cba8-125">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a><span data-ttu-id="2cba8-126">Adaptador MLLP bidireccional solo admite el formato del mensaje 2.X</span><span class="sxs-lookup"><span data-stu-id="2cba8-126">Two-way MLLP adapter only supports the 2.X message format</span></span>  
 <span data-ttu-id="2cba8-127">El adaptador MLLP bidireccional actualmente admite solo el formato del mensaje 2.X.</span><span class="sxs-lookup"><span data-stu-id="2cba8-127">The two-way MLLP adapter currently supports only the 2.X message format.</span></span>  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a><span data-ttu-id="2cba8-128">El adaptador MLLP bidireccional no admite confirmaciones estáticas</span><span class="sxs-lookup"><span data-stu-id="2cba8-128">Two-way MLLP adapter does not support static acknowledgments</span></span>  
 <span data-ttu-id="2cba8-129">El de envío bidireccional adaptador no admite el procesamiento de confirmaciones estáticas.</span><span class="sxs-lookup"><span data-stu-id="2cba8-129">The two-way send adapter does not support processing static acknowledgments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cba8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cba8-130">See Also</span></span>  
 [<span data-ttu-id="2cba8-131">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="2cba8-131">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)