---
title: Procesamiento de archivos planos BTAHL72X | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a0220d44386eed94efbddc1a5a22fe6704a7780
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975557"
---
# <a name="btahl72x-flat-file-processing"></a><span data-ttu-id="1f24f-102">Procesamiento de archivos planos BTAHL72X</span><span class="sxs-lookup"><span data-stu-id="1f24f-102">BTAHL72X Flat File Processing</span></span>
<span data-ttu-id="1f24f-103">Los siguientes componentes en el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) mensajes de proceso HL7 2.X (codificada HL7):</span><span class="sxs-lookup"><span data-stu-id="1f24f-103">The following components in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.X (HL7-encoded) messages:</span></span>  
  
- <span data-ttu-id="1f24f-104">Las canalizaciones y las bibliotecas de core: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineCommon.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="1f24f-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
- <span data-ttu-id="1f24f-105">Bibliotecas de ensamblador y desensamblador: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72fAsm.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72fDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="1f24f-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fDAsm.dll</span></span>  
  
- <span data-ttu-id="1f24f-106">Adaptador de envío de la biblioteca de validación de confirmación (ACK) usada para el MLLP bidireccional: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="1f24f-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="hl7-message-modes"></a><span data-ttu-id="1f24f-107">HL7 Modos de mensaje</span><span class="sxs-lookup"><span data-stu-id="1f24f-107">HL7 Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-108"> admite los siguientes modos de mensaje para mensajes 2.X:</span><span class="sxs-lookup"><span data-stu-id="1f24f-108"> supports the following message modes for 2.X messages:</span></span>  
  
- <span data-ttu-id="1f24f-109">Modo de publicación-suscripción (pub-sub)</span><span class="sxs-lookup"><span data-stu-id="1f24f-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
   <span data-ttu-id="1f24f-110">El publicador se difunde a una entidad de los suscriptores, de forma declarativas o un no solicitados update.</span><span class="sxs-lookup"><span data-stu-id="1f24f-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1f24f-111"> y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporcionan flexibilidad de este modo, ya que puede administrar las suscripciones y las partes después de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="1f24f-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
- <span data-ttu-id="1f24f-112">Modo de solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="1f24f-112">Request-response mode</span></span>  
  
   <span data-ttu-id="1f24f-113">Intercambio de mensajes un interrogative o consulta en el que da como resultado una solicitud específica de una entidad específica en un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1f24f-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="flat-file-parsing"></a><span data-ttu-id="1f24f-114">Análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="1f24f-114">Flat File Parsing</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-115"> analiza HL7 2.X mensajes varias partes en tres partes:</span><span class="sxs-lookup"><span data-stu-id="1f24f-115"> parses HL7 2.X multi-part messages into three parts:</span></span>  
  
-   <span data-ttu-id="1f24f-116">Parte de encabezado MSH</span><span class="sxs-lookup"><span data-stu-id="1f24f-116">Header-MSH part</span></span>  
  
-   <span data-ttu-id="1f24f-117">Parte del cuerpo</span><span class="sxs-lookup"><span data-stu-id="1f24f-117">Body part</span></span>  
  
-   <span data-ttu-id="1f24f-118">Parte de la Z</span><span class="sxs-lookup"><span data-stu-id="1f24f-118">Z part</span></span>  
  
## <a name="hl7-header-validation"></a><span data-ttu-id="1f24f-119">HL7 Validación de encabezados</span><span class="sxs-lookup"><span data-stu-id="1f24f-119">HL7 Header Validation</span></span>  
 <span data-ttu-id="1f24f-120">El Desensamblador HL7 y ensamblador de realizan la validación estructural y esquemática del encabezado de un mensaje 2.X, con el fin de comprobar que puede procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1f24f-120">The HL7 disassembler and assembler perform structural and schematic validation of the header of a 2.X message, in order to verify that it can process the message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-121"> bases de la validación de esquema en el esquema de encabezado común, MSH_25_GLO_DEF.</span><span class="sxs-lookup"><span data-stu-id="1f24f-121"> bases the schematic validation on the common header schema, MSH_25_GLO_DEF.</span></span>  
  
 <span data-ttu-id="1f24f-122">Por ejemplo, el analizador determina que los campos MSH1 y MSH2 están bien formados.</span><span class="sxs-lookup"><span data-stu-id="1f24f-122">For instance, the parser determines that the MSH1 and MSH2 fields are well formed.</span></span> <span data-ttu-id="1f24f-123">MSH1 debe tener un solo carácter.</span><span class="sxs-lookup"><span data-stu-id="1f24f-123">MSH1 must have only one character.</span></span> <span data-ttu-id="1f24f-124">MSH2 debe estar comprendido entre dos y cuatro caracteres y no puede repetir ningún carácter.</span><span class="sxs-lookup"><span data-stu-id="1f24f-124">MSH2 must be between two and four characters, and no characters can repeat.</span></span>  
  
## <a name="hl7-body-validation"></a><span data-ttu-id="1f24f-125">HL7 Validación de cuerpo</span><span class="sxs-lookup"><span data-stu-id="1f24f-125">HL7 Body Validation</span></span>  
 <span data-ttu-id="1f24f-126">El Desensamblador HL7 y ensamblador realizan validación estructural básica del cuerpo de un mensaje 2.X y validación de esquema, si habilita esta opción.</span><span class="sxs-lookup"><span data-stu-id="1f24f-126">The HL7 disassembler and assembler perform basic structural validation of the body of a 2.X message, and schematic validation, if you enable it.</span></span>  
  
 <span data-ttu-id="1f24f-127">La validación estructural básica del cuerpo, que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] siempre lleva a cabo, incluye la comprobación de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f24f-127">The basic structural validation of the body, which [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] always performs, includes verifying the following:</span></span>  
  
- <span data-ttu-id="1f24f-128">Hay tres caracteres en segmentos</span><span class="sxs-lookup"><span data-stu-id="1f24f-128">That there are three characters in segments</span></span>  
  
- <span data-ttu-id="1f24f-129">Que es el delimitador de segmento \<CR\> o \<CR\>\<LF\> (opcional para el último segmento)</span><span class="sxs-lookup"><span data-stu-id="1f24f-129">That the segment delimiter is \<CR\> or \<CR\>\<LF\> (optional for the last segment)</span></span>  
  
- <span data-ttu-id="1f24f-130">Que son adecuados los delimitadores de campo</span><span class="sxs-lookup"><span data-stu-id="1f24f-130">That field delimiters are appropriate</span></span>  
  
- <span data-ttu-id="1f24f-131">Que no hay ningún segmento declarado (con una etiqueta de segmento de tres caracteres definido) en un segmento de Z no declarado</span><span class="sxs-lookup"><span data-stu-id="1f24f-131">That there are no declared segments (with a defined three-character segment tag) in an undeclared Z segment</span></span>  
  
  <span data-ttu-id="1f24f-132">Validación de esquema más extensa del cuerpo de la incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f24f-132">More extensive schema validation of the body includes the following:</span></span>  
  
- <span data-ttu-id="1f24f-133">Delimitadores de campo al final</span><span class="sxs-lookup"><span data-stu-id="1f24f-133">Trailing-field delimiters</span></span>  
  
   <span data-ttu-id="1f24f-134">En el segmento de encabezado MSH y segmentos de cuerpo</span><span class="sxs-lookup"><span data-stu-id="1f24f-134">In Header-MSH segment and body segments</span></span>  
  
- <span data-ttu-id="1f24f-135">Segmento de Z</span><span class="sxs-lookup"><span data-stu-id="1f24f-135">Z segment</span></span>  
  
- <span data-ttu-id="1f24f-136">Tipo de datos de XSD compatibles y personalizadas</span><span class="sxs-lookup"><span data-stu-id="1f24f-136">XSD-supported and custom data type</span></span>  
  
   <span data-ttu-id="1f24f-137">XSD compatibles y los tipos de XSD no (TS (marca de tiempo), DT (fecha), TM (tiempo) y TN (número de teléfono)</span><span class="sxs-lookup"><span data-stu-id="1f24f-137">XSD supported and non-XSD types (TS (Time Stamp), DT (date), TM (time), and TN (telephone number)</span></span>  
  
- <span data-ttu-id="1f24f-138">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1f24f-138">Enumerations</span></span>  
  
   <span data-ttu-id="1f24f-139">Id. (las tablas definidas por HL7) e IS (tablas definidas por el usuario)</span><span class="sxs-lookup"><span data-stu-id="1f24f-139">ID (HL7-defined tables) and IS (user-defined tables)</span></span>  
  
- <span data-ttu-id="1f24f-140">Opcionalidad</span><span class="sxs-lookup"><span data-stu-id="1f24f-140">Optionality</span></span>  
  
   <span data-ttu-id="1f24f-141">Obligatorios y opcionales</span><span class="sxs-lookup"><span data-stu-id="1f24f-141">Required and optional</span></span>  
  
- <span data-ttu-id="1f24f-142">Repetición</span><span class="sxs-lookup"><span data-stu-id="1f24f-142">Repetition</span></span>  
  
   <span data-ttu-id="1f24f-143">Segmento y campo</span><span class="sxs-lookup"><span data-stu-id="1f24f-143">Segment and field</span></span>  
  
- <span data-ttu-id="1f24f-144">Secuencias de escape</span><span class="sxs-lookup"><span data-stu-id="1f24f-144">Escape sequences</span></span>  
  
   <span data-ttu-id="1f24f-145">Codificación de caracteres, el formato y los juegos de caracteres</span><span class="sxs-lookup"><span data-stu-id="1f24f-145">Encoding characters, formatting, and character sets</span></span>  
  
  <span data-ttu-id="1f24f-146">Habilitar o deshabilitar la validación de esquema para todos los mensajes recibidos o enviados a una entidad específica (entidad de origen para el desensamblador, la entidad de destino para el ensamblador).</span><span class="sxs-lookup"><span data-stu-id="1f24f-146">You enable or disable schematic validation for all messages received from or sent to a specific party (source party for the disassembler, destination party for the assembler).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-147"> usa el HL7 2.X esquemas directamente para este procesamiento, según lo determinado por el campo de encabezado MSH9.3 estructura de mensaje, el campo de Id. de versión MSH12 (2.3.1 2.4 y 2.5) y el espacio de nombres en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f24f-147"> uses the HL7 2.X schemas directly for this processing, as determined by the MSH9.3 message-structure header field, the MSH12 Version ID field (2.3.1, 2.4, or 2.5), and the namespace setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="hl7-disassembler-processing"></a><span data-ttu-id="1f24f-148">HL7 Procesamiento de desensamblador</span><span class="sxs-lookup"><span data-stu-id="1f24f-148">HL7 Disassembler Processing</span></span>  
 <span data-ttu-id="1f24f-149">El Desensamblador HL7 analiza los mensajes entrantes de HL7 en segmentos XML para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1f24f-149">The HL7 disassembler parses incoming HL7 messages into XML segments for processing.</span></span> <span data-ttu-id="1f24f-150">A medida que analiza los mensajes, el Desensamblador realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="1f24f-150">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="1f24f-151">Identificadores de secuencias de escape</span><span class="sxs-lookup"><span data-stu-id="1f24f-151">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="1f24f-152">Controla las comprobaciones de las propiedades obligatorias y opcionales</span><span class="sxs-lookup"><span data-stu-id="1f24f-152">Handles checks of the required/optional properties</span></span>  
  
-   <span data-ttu-id="1f24f-153">Identificadores definen segmentos e indefinidos o inesperados Z (para obtener una descripción de los segmentos de Z, consulte [personalizar mensajes a través de objetos de Z](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).</span><span class="sxs-lookup"><span data-stu-id="1f24f-153">Handles defined segments and undefined or unexpected Z segments (for a description of Z segments, see [Customizing Messages through Z Objects](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).</span></span>  
  
-   <span data-ttu-id="1f24f-154">Omite los segmentos inesperados al final de una instancia (que se convierten en segmentos de Z no declarados)</span><span class="sxs-lookup"><span data-stu-id="1f24f-154">Ignores unexpected segments at the end of an instance (which become undeclared Z segments)</span></span>  
  
## <a name="error-reporting"></a><span data-ttu-id="1f24f-155">Informes de errores</span><span class="sxs-lookup"><span data-stu-id="1f24f-155">Error Reporting</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-156"> notifica la mayoría de los errores en el formato de error estándar HL7, que incluyen el código de segmento, secuencia, campo y error.</span><span class="sxs-lookup"><span data-stu-id="1f24f-156"> reports most errors in standard HL7 error format, which include the segment, sequence, field, and error code.</span></span> <span data-ttu-id="1f24f-157">Sin embargo, la condición de error puede ser que no todos ellos están disponibles, por ejemplo, si no hay ningún esquema.</span><span class="sxs-lookup"><span data-stu-id="1f24f-157">However, the error condition may be such that not all of these are available, for instance, if no schema is present.</span></span> <span data-ttu-id="1f24f-158">Para controlar estos casos, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede informar sobre errores en uno alternativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] formato de error.</span><span class="sxs-lookup"><span data-stu-id="1f24f-158">To handle such cases, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can report errors in an alternate [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error format.</span></span> <span data-ttu-id="1f24f-159">El segmento en un mensaje de error incluye dos partes: una para el error de HL7 y otra para la alternativa [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.</span><span class="sxs-lookup"><span data-stu-id="1f24f-159">The error segment in a message includes two parts: one for the HL7 error and one for the alternative [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="1f24f-160">Generación de confirmación</span><span class="sxs-lookup"><span data-stu-id="1f24f-160">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-161"> admite los siguientes tipos de confirmación (ACK) para los mensajes 2.X.</span><span class="sxs-lookup"><span data-stu-id="1f24f-161"> supports the following types of acknowledgments (ACKs) for 2.X messages.</span></span> <span data-ttu-id="1f24f-162">Tanto el tipo de error de HL7 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se utiliza el tipo de error (alternativo):</span><span class="sxs-lookup"><span data-stu-id="1f24f-162">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="1f24f-163">Asignación de confirmación y del mensaje original</span><span class="sxs-lookup"><span data-stu-id="1f24f-163">Mapping original message and ACK</span></span>  
  
-   <span data-ttu-id="1f24f-164">Mensajes de confirmación originales de HL7</span><span class="sxs-lookup"><span data-stu-id="1f24f-164">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="1f24f-165">HL7 mejorado confirmaciones</span><span class="sxs-lookup"><span data-stu-id="1f24f-165">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="1f24f-166">Acepte la confirmación y la aplicación acepte</span><span class="sxs-lookup"><span data-stu-id="1f24f-166">Commit Accept and Application Accept</span></span>  
  
-   <span data-ttu-id="1f24f-167">Confirmación de proxy/estático</span><span class="sxs-lookup"><span data-stu-id="1f24f-167">Static/proxy ACK</span></span>  
  
     <span data-ttu-id="1f24f-168">Confirmación o NAK</span><span class="sxs-lookup"><span data-stu-id="1f24f-168">ACK or NAK</span></span>  
  
## <a name="property-promotion"></a><span data-ttu-id="1f24f-169">Promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="1f24f-169">Property Promotion</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f24f-170"> admite la promoción de las siguientes propiedades 2.X:</span><span class="sxs-lookup"><span data-stu-id="1f24f-170"> supports promoting the following 2.X properties:</span></span>  
  
-   <span data-ttu-id="1f24f-171">Esquema de propiedad</span><span class="sxs-lookup"><span data-stu-id="1f24f-171">Property schema</span></span>  
  
-   <span data-ttu-id="1f24f-172">Esquema de encabezado de MSH</span><span class="sxs-lookup"><span data-stu-id="1f24f-172">MSH-header schema</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f24f-173">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f24f-173">In This Section</span></span>  
  
-   [<span data-ttu-id="1f24f-174">Determinación del esquema en el desensamblador HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="1f24f-174">Schema Determination in the HL7 2.X Disassembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [<span data-ttu-id="1f24f-175">Determinación del esquema en el ensamblador HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="1f24f-175">Schema Determination in the HL7 2.X Assembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f24f-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f24f-176">See Also</span></span>  
 <span data-ttu-id="1f24f-177">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="1f24f-177">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 <span data-ttu-id="1f24f-178">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="1f24f-178">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="1f24f-179">Uso de esquemas HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="1f24f-179">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)