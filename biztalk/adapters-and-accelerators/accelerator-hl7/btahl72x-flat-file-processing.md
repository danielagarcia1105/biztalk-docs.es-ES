---
title: Procesamiento de archivos planos BTAHL72X | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- 2.X messages, disassembler
- property promotion, MSH-header schemas
- disassembler, validating messages
- HL7, errors
- 2.X messages, validating headers
- acknowledgements, generating
- assembler, validating messages
- messages, multi-part messages
- property promotion, property schemas
- generating aknowledgements
- messages, 2.X messages
- schemas, MSH-header schemas
- 2.X messages, validating message bodies
- 2.X messages
- schemas, property schemas
- message modes, 2.X messages
- errors, HL7 error format
- flat files
- validating, messages
- schemas, property promotion
- headers, validating
- 2.X messages, message modes
- 2.X messages, header validation
- 2.X messages, parsing flat files
ms.assetid: c92e2f70-0bfa-4bc8-8044-4a6e62cabee3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15d21653b9f0d6109487677484506c7a5d6bcc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="btahl72x-flat-file-processing"></a><span data-ttu-id="4ed3c-102">Procesamiento de archivo sin formato BTAHL72X</span><span class="sxs-lookup"><span data-stu-id="4ed3c-102">BTAHL72X Flat File Processing</span></span>
<span data-ttu-id="4ed3c-103">Los componentes siguientes en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proceso HL7 2.X (codificada HL7) mensajes:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-103">The following components in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.X (HL7-encoded) messages:</span></span>  
  
-   <span data-ttu-id="4ed3c-104">Las canalizaciones y las bibliotecas principales: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineCommon.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="4ed3c-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
-   <span data-ttu-id="4ed3c-105">Bibliotecas de ensamblador y desensamblador: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72fAsm.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72fDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="4ed3c-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fDAsm.dll</span></span>  
  
-   <span data-ttu-id="4ed3c-106">Adaptador de envío de la biblioteca de validación de confirmación (ACK) utilizada para la MLLP bidireccional: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="4ed3c-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="hl7-message-modes"></a><span data-ttu-id="4ed3c-107">HL7 Modos de mensaje</span><span class="sxs-lookup"><span data-stu-id="4ed3c-107">HL7 Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-108">admite los siguientes modos de mensaje para los mensajes 2.X:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-108"> supports the following message modes for 2.X messages:</span></span>  
  
-   <span data-ttu-id="4ed3c-109">Modo de publicador y el suscriptor (publicación-suscripción)</span><span class="sxs-lookup"><span data-stu-id="4ed3c-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
     <span data-ttu-id="4ed3c-110">El publicador se difunde a una entidad de suscriptores, como declarativas o un no solicitados update.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4ed3c-111">y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporcionar flexibilidad de este modo, ya que puede administrar las suscripciones y las entidades después de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
-   <span data-ttu-id="4ed3c-112">Modo de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="4ed3c-112">Request-response mode</span></span>  
  
     <span data-ttu-id="4ed3c-113">Intercambio de mensajes un interrogative o consulta en la que da como resultado una solicitud específica de una entidad específica en un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="flat-file-parsing"></a><span data-ttu-id="4ed3c-114">Análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="4ed3c-114">Flat File Parsing</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-115">analiza HL7 mensajes de varias partes de 2.X en tres partes:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-115"> parses HL7 2.X multi-part messages into three parts:</span></span>  
  
-   <span data-ttu-id="4ed3c-116">Parte del encabezado MSH</span><span class="sxs-lookup"><span data-stu-id="4ed3c-116">Header-MSH part</span></span>  
  
-   <span data-ttu-id="4ed3c-117">Parte del cuerpo</span><span class="sxs-lookup"><span data-stu-id="4ed3c-117">Body part</span></span>  
  
-   <span data-ttu-id="4ed3c-118">Parte de la Z</span><span class="sxs-lookup"><span data-stu-id="4ed3c-118">Z part</span></span>  
  
## <a name="hl7-header-validation"></a><span data-ttu-id="4ed3c-119">HL7 Validación de encabezados</span><span class="sxs-lookup"><span data-stu-id="4ed3c-119">HL7 Header Validation</span></span>  
 <span data-ttu-id="4ed3c-120">El Desensamblador de HL7 y de ensamblador realizan la validación estructural y esquemática del encabezado de un mensaje 2.X, con el fin de comprobar que puede procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-120">The HL7 disassembler and assembler perform structural and schematic validation of the header of a 2.X message, in order to verify that it can process the message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-121">basa la validación del esquema en el esquema de encabezado común, MSH_25_GLO_DEF.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-121"> bases the schematic validation on the common header schema, MSH_25_GLO_DEF.</span></span>  
  
 <span data-ttu-id="4ed3c-122">Por ejemplo, el analizador determina que los campos MSH1 y MSH2 sean correctos.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-122">For instance, the parser determines that the MSH1 and MSH2 fields are well formed.</span></span> <span data-ttu-id="4ed3c-123">MSH1 debe tener un solo carácter.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-123">MSH1 must have only one character.</span></span> <span data-ttu-id="4ed3c-124">MSH2 debe estar comprendido entre dos y cuatro caracteres y no puede repetir ningún carácter.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-124">MSH2 must be between two and four characters, and no characters can repeat.</span></span>  
  
## <a name="hl7-body-validation"></a><span data-ttu-id="4ed3c-125">HL7 Validación de cuerpo</span><span class="sxs-lookup"><span data-stu-id="4ed3c-125">HL7 Body Validation</span></span>  
 <span data-ttu-id="4ed3c-126">El Desensamblador de HL7 y de ensamblador realizan una validación básica del cuerpo de un mensaje 2.X estructural y validación de esquema, si se habilita.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-126">The HL7 disassembler and assembler perform basic structural validation of the body of a 2.X message, and schematic validation, if you enable it.</span></span>  
  
 <span data-ttu-id="4ed3c-127">La validación estructural básica del cuerpo, que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] siempre realiza, incluye comprobar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-127">The basic structural validation of the body, which [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] always performs, includes verifying the following:</span></span>  
  
-   <span data-ttu-id="4ed3c-128">Hay tres caracteres en segmentos</span><span class="sxs-lookup"><span data-stu-id="4ed3c-128">That there are three characters in segments</span></span>  
  
-   <span data-ttu-id="4ed3c-129">Que es el delimitador de segmento \<CR > o \<CR >\<LF > (opcional para el último segmento)</span><span class="sxs-lookup"><span data-stu-id="4ed3c-129">That the segment delimiter is \<CR> or \<CR>\<LF> (optional for the last segment)</span></span>  
  
-   <span data-ttu-id="4ed3c-130">Que son adecuados los delimitadores de campo</span><span class="sxs-lookup"><span data-stu-id="4ed3c-130">That field delimiters are appropriate</span></span>  
  
-   <span data-ttu-id="4ed3c-131">Que no hay ningún segmento declarado (con una etiqueta de segmento definido de tres caracteres) en un segmento de Z no declarado</span><span class="sxs-lookup"><span data-stu-id="4ed3c-131">That there are no declared segments (with a defined three-character segment tag) in an undeclared Z segment</span></span>  
  
 <span data-ttu-id="4ed3c-132">Validación de esquema más amplia del cuerpo de la incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-132">More extensive schema validation of the body includes the following:</span></span>  
  
-   <span data-ttu-id="4ed3c-133">Delimitadores de campo finales</span><span class="sxs-lookup"><span data-stu-id="4ed3c-133">Trailing-field delimiters</span></span>  
  
     <span data-ttu-id="4ed3c-134">En el segmento de encabezado MSH y segmentos de cuerpo</span><span class="sxs-lookup"><span data-stu-id="4ed3c-134">In Header-MSH segment and body segments</span></span>  
  
-   <span data-ttu-id="4ed3c-135">Segmento de Z</span><span class="sxs-lookup"><span data-stu-id="4ed3c-135">Z segment</span></span>  
  
-   <span data-ttu-id="4ed3c-136">Tipo de datos admite XSD y personalizados</span><span class="sxs-lookup"><span data-stu-id="4ed3c-136">XSD-supported and custom data type</span></span>  
  
     <span data-ttu-id="4ed3c-137">XSD compatibles y los tipos de XSD no (TS (marca de tiempo), DT (fecha), TM (tiempo) y TN (número de teléfono)</span><span class="sxs-lookup"><span data-stu-id="4ed3c-137">XSD supported and non-XSD types (TS (Time Stamp), DT (date), TM (time), and TN (telephone number)</span></span>  
  
-   <span data-ttu-id="4ed3c-138">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="4ed3c-138">Enumerations</span></span>  
  
     <span data-ttu-id="4ed3c-139">Id. (tablas definidas por el HL7) e IS (tablas definidas por el usuario)</span><span class="sxs-lookup"><span data-stu-id="4ed3c-139">ID (HL7-defined tables) and IS (user-defined tables)</span></span>  
  
-   <span data-ttu-id="4ed3c-140">Definir la opcionalidad como</span><span class="sxs-lookup"><span data-stu-id="4ed3c-140">Optionality</span></span>  
  
     <span data-ttu-id="4ed3c-141">Obligatorios y opcionales</span><span class="sxs-lookup"><span data-stu-id="4ed3c-141">Required and optional</span></span>  
  
-   <span data-ttu-id="4ed3c-142">Repetición</span><span class="sxs-lookup"><span data-stu-id="4ed3c-142">Repetition</span></span>  
  
     <span data-ttu-id="4ed3c-143">Segmento y el campo</span><span class="sxs-lookup"><span data-stu-id="4ed3c-143">Segment and field</span></span>  
  
-   <span data-ttu-id="4ed3c-144">Secuencias de escape</span><span class="sxs-lookup"><span data-stu-id="4ed3c-144">Escape sequences</span></span>  
  
     <span data-ttu-id="4ed3c-145">La codificación de caracteres, el formato y los juegos de caracteres</span><span class="sxs-lookup"><span data-stu-id="4ed3c-145">Encoding characters, formatting, and character sets</span></span>  
  
 <span data-ttu-id="4ed3c-146">Habilitar o deshabilitar la validación de esquema para todos los mensajes recibidos o enviados a un usuario específico (entidad de origen para el desensamblador, la entidad de destino para el ensamblador).</span><span class="sxs-lookup"><span data-stu-id="4ed3c-146">You enable or disable schematic validation for all messages received from or sent to a specific party (source party for the disassembler, destination party for the assembler).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-147">usa el HL7 2.X esquemas directamente para este procesamiento, según lo determinado por el campo de encabezado de la estructura de los mensajes MSH9.3, el campo de Id. de versión MSH12 (2.3.1, 2.4 o 2.5) y el espacio de nombres en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-147"> uses the HL7 2.X schemas directly for this processing, as determined by the MSH9.3 message-structure header field, the MSH12 Version ID field (2.3.1, 2.4, or 2.5), and the namespace setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="hl7-disassembler-processing"></a><span data-ttu-id="4ed3c-148">HL7 Procesamiento de desensamblador</span><span class="sxs-lookup"><span data-stu-id="4ed3c-148">HL7 Disassembler Processing</span></span>  
 <span data-ttu-id="4ed3c-149">El Desensamblador de HL7 analiza los mensajes entrantes de HL7 en segmentos XML para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-149">The HL7 disassembler parses incoming HL7 messages into XML segments for processing.</span></span> <span data-ttu-id="4ed3c-150">A medida que analiza los mensajes, el Desensamblador realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-150">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="4ed3c-151">Identificadores de secuencias de escape</span><span class="sxs-lookup"><span data-stu-id="4ed3c-151">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="4ed3c-152">Controla las comprobaciones de las propiedades obligatorias y opcionales</span><span class="sxs-lookup"><span data-stu-id="4ed3c-152">Handles checks of the required/optional properties</span></span>  
  
-   <span data-ttu-id="4ed3c-153">Identificadores definen segmentos e indefinidos o inesperados Z (para obtener una descripción de los segmentos de Z, consulte [personalizar mensajes a través de objetos de Z](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).</span><span class="sxs-lookup"><span data-stu-id="4ed3c-153">Handles defined segments and undefined or unexpected Z segments (for a description of Z segments, see [Customizing Messages through Z Objects](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).</span></span>  
  
-   <span data-ttu-id="4ed3c-154">Omite los segmentos inesperados al final de una instancia (que se convierten en no declarados segmentos Z)</span><span class="sxs-lookup"><span data-stu-id="4ed3c-154">Ignores unexpected segments at the end of an instance (which become undeclared Z segments)</span></span>  
  
## <a name="error-reporting"></a><span data-ttu-id="4ed3c-155">Informes de errores</span><span class="sxs-lookup"><span data-stu-id="4ed3c-155">Error Reporting</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-156">notifica la mayoría de los errores en el formato de error estándar HL7, que incluyen el código de segmento, secuencia, campo y error.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-156"> reports most errors in standard HL7 error format, which include the segment, sequence, field, and error code.</span></span> <span data-ttu-id="4ed3c-157">Sin embargo, la condición de error puede ser tal que no todas ellas están disponibles, por ejemplo, si no hay ningún esquema.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-157">However, the error condition may be such that not all of these are available, for instance, if no schema is present.</span></span> <span data-ttu-id="4ed3c-158">Para tratar estos casos, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede notificar los errores en una alternativa [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] formato de error.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-158">To handle such cases, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can report errors in an alternate [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error format.</span></span> <span data-ttu-id="4ed3c-159">El segmento en un mensaje de error incluye dos partes: una para el error HL7 y otra para la alternativa [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-159">The error segment in a message includes two parts: one for the HL7 error and one for the alternative [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="4ed3c-160">Generación de confirmación</span><span class="sxs-lookup"><span data-stu-id="4ed3c-160">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-161">admite los siguientes tipos de confirmaciones (ACK) para los mensajes 2.X.</span><span class="sxs-lookup"><span data-stu-id="4ed3c-161"> supports the following types of acknowledgments (ACKs) for 2.X messages.</span></span> <span data-ttu-id="4ed3c-162">El tipo de error de HL7 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se utiliza el tipo de error (alternativo):</span><span class="sxs-lookup"><span data-stu-id="4ed3c-162">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="4ed3c-163">Asignación de confirmación y del mensaje original</span><span class="sxs-lookup"><span data-stu-id="4ed3c-163">Mapping original message and ACK</span></span>  
  
-   <span data-ttu-id="4ed3c-164">Confirmaciones originales HL7</span><span class="sxs-lookup"><span data-stu-id="4ed3c-164">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="4ed3c-165">HL7 mejorado confirmaciones</span><span class="sxs-lookup"><span data-stu-id="4ed3c-165">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="4ed3c-166">Acepte la confirmación y aplicación acepte</span><span class="sxs-lookup"><span data-stu-id="4ed3c-166">Commit Accept and Application Accept</span></span>  
  
-   <span data-ttu-id="4ed3c-167">Confirmación de estático/proxy</span><span class="sxs-lookup"><span data-stu-id="4ed3c-167">Static/proxy ACK</span></span>  
  
     <span data-ttu-id="4ed3c-168">Confirmación o NAK</span><span class="sxs-lookup"><span data-stu-id="4ed3c-168">ACK or NAK</span></span>  
  
## <a name="property-promotion"></a><span data-ttu-id="4ed3c-169">Promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="4ed3c-169">Property Promotion</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4ed3c-170">admite la promoción de las propiedades 2.X siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ed3c-170"> supports promoting the following 2.X properties:</span></span>  
  
-   <span data-ttu-id="4ed3c-171">Esquema de propiedades</span><span class="sxs-lookup"><span data-stu-id="4ed3c-171">Property schema</span></span>  
  
-   <span data-ttu-id="4ed3c-172">Esquema de encabezado de MSH</span><span class="sxs-lookup"><span data-stu-id="4ed3c-172">MSH-header schema</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ed3c-173">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ed3c-173">In This Section</span></span>  
  
-   [<span data-ttu-id="4ed3c-174">Determinación del esquema en el Desensamblador 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="4ed3c-174">Schema Determination in the HL7 2.X Disassembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [<span data-ttu-id="4ed3c-175">Determinación del esquema en el ensamblador 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="4ed3c-175">Schema Determination in the HL7 2.X Assembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ed3c-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ed3c-176">See Also</span></span>  
 <span data-ttu-id="4ed3c-177">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="4ed3c-177">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 <span data-ttu-id="4ed3c-178">[Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4ed3c-178">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="4ed3c-179">Utilizar esquemas 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="4ed3c-179">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)