---
title: Solución de problemas de errores | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f5af933f83f292bfae3f92f70d2c247274c159c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976861"
---
# <a name="troubleshooting-errors"></a><span data-ttu-id="fa7a5-102">Solución de problemas de errores</span><span class="sxs-lookup"><span data-stu-id="fa7a5-102">Troubleshooting Errors</span></span>
<span data-ttu-id="fa7a5-103">Esta sección tratan problemas relacionados con [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generado errores.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-103">This section addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generated errors.</span></span>  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a><span data-ttu-id="fa7a5-104">El adaptador MLLP sólo puede ejecutarse en una instancia de host</span><span class="sxs-lookup"><span data-stu-id="fa7a5-104">The MLLP adapter can run only on a single host instance</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="fa7a5-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="fa7a5-105">Symptom</span></span>  
 <span data-ttu-id="fa7a5-106">No se puede habilitar una ubicación de recepción con un tipo de transporte de MLLP y un controlador de recepción diferente a otra ubicación de recepción existente.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-106">You cannot enable a receive location with a transport type of MLLP and a different receive handler than another existing receive location.</span></span> <span data-ttu-id="fa7a5-107">Además, no se puede dar de alta e iniciar un puerto de envío con un controlador de envío diferente que el puerto de envío existente de otro.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-107">In addition, you cannot enlist and start a send port with a different send handler than another existing send port.</span></span>  
  
<span data-ttu-id="fa7a5-108">**Causa posible** : sólo se puede utilizar MLLP de una recepción controlador en un único servidor (o envío).</span><span class="sxs-lookup"><span data-stu-id="fa7a5-108">**Possible Cause** : You can only use one MLLP receive (or send) handler on a single server.</span></span> <span data-ttu-id="fa7a5-109">Además, el URI designado para la ubicación de recepción (o el puerto de envío) (el nombre de Host en las propiedades de transporte de MLLP) debe ser "localhost" o el nombre del servidor donde el host de instancia para el controlador de adaptador (envío o recepción) se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-109">In addition, the URI designated for the receive location (or send port) (the Host name in the MLLP Transport Properties) must either be "localhost" or the server name where the host instance for the receive (or send) adapter handler is running.</span></span>  
  
<span data-ttu-id="fa7a5-110">**Resolución** : designar el mismo controlador (envío o recepción) de MLLP todas las ubicaciones de recepción (o puertos de envío) en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-110">**Resolution** : Designate the same receive (or send) handler for all MLLP receive locations (or send ports) on a single server.</span></span>  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a><span data-ttu-id="fa7a5-111">Esquemas de confirmación y MSH deben agregarse a un solo proyecto</span><span class="sxs-lookup"><span data-stu-id="fa7a5-111">MSH and ACK schemas must be added to only one project</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="fa7a5-112">Síntoma</span><span class="sxs-lookup"><span data-stu-id="fa7a5-112">Symptom</span></span>  
 <span data-ttu-id="fa7a5-113">Al intentar compilar un proyecto, obtendrá uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa7a5-113">When you attempt to build a project, you get one of the following errors:</span></span>  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
<span data-ttu-id="fa7a5-114">**Causa posible** : esquemas de confirmación y el de MSH (MSH_25_GLO_DEF.xsd y ACK_24_GLO_DEF.xsd) se han implementado en varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-114">**Possible Cause** : The MSH and ACK schemas (MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd) have been deployed in multiple projects.</span></span>  
  
<span data-ttu-id="fa7a5-115">**Resolución** : asegúrese de que se han agregado a un solo proyecto MSH_25_GLO_DEF.xsd y ACK_24_GLO_DEF.xsd.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-115">**Resolution** : Ensure that MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd have been added to only one project.</span></span>  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a><span data-ttu-id="fa7a5-116">Excepción de tipo System.OutOfMemoryException ha producido un error en el registro de eventos</span><span class="sxs-lookup"><span data-stu-id="fa7a5-116">Exception of type System.OutOfMemoryException has thrown an error in the Event Log</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="fa7a5-117">Síntoma</span><span class="sxs-lookup"><span data-stu-id="fa7a5-117">Symptom</span></span>  
 <span data-ttu-id="fa7a5-118">Obtendrá el error siguiente o similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="fa7a5-118">You get the following or similar error in the Event Log:</span></span>  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
<span data-ttu-id="fa7a5-119">**Causa posible** : al procesar un gran número de mensajes, algunos [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes del motor pueden producir pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-119">**Possible Cause** : While processing a large number of messages, some [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] engine components may exhibit memory leaks.</span></span>  
  
<span data-ttu-id="fa7a5-120">**Resolución** : reiniciar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa7a5-120">**Resolution** : Restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a><span data-ttu-id="fa7a5-121">Serialización de encabezado, genera un error en el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="fa7a5-121">Header serialization generates an error in the Event Viewer</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="fa7a5-122">Síntoma</span><span class="sxs-lookup"><span data-stu-id="fa7a5-122">Symptom</span></span>  
 <span data-ttu-id="fa7a5-123">Se produce el error siguiente o similar en el registro de eventos, aunque el mensaje en la herramienta de mantenimiento y seguimiento de actividad (HAT) indica el éxito:</span><span class="sxs-lookup"><span data-stu-id="fa7a5-123">You get the following or similar error in the Event Log, even though the message in the Health and Activity Tracking (HAT) tool indicates success:</span></span>  
  
`An error happened in the header during serialization.`
  
<span data-ttu-id="fa7a5-124">**Causa posible** : el valor de transformación del encabezado de mensaje no se establece correctamente [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-124">**Possible Cause** : The message header transformation value is not set correctly in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
<span data-ttu-id="fa7a5-125">**Resolución** : asignación de MSH Compruebe los valores de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-125">**Resolution** : Verify MSH map values in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a><span data-ttu-id="fa7a5-126">Se registran errores de serializador 4133 de Id. de evento duplicada</span><span class="sxs-lookup"><span data-stu-id="fa7a5-126">Duplicate Event ID 4133 serializer errors are logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="fa7a5-127">Síntoma</span><span class="sxs-lookup"><span data-stu-id="fa7a5-127">Symptom</span></span>  
 <span data-ttu-id="fa7a5-128">Id. de evento 4133: "Error ocurrido en encabezado durante la serialización" se produce dos veces para cada instancia de un mensaje con un valor de MSH11 que no es válido.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-128">Event ID 4133 – "Error happened in header during serialization" occurs twice for every instance of a message with a MSH11 value that is not valid.</span></span>  
  
<span data-ttu-id="fa7a5-129">**Causa posible** : se produjo un error al procesar dos confirmaciones (confirmación y confirmaciones de aplicación) sin errores duplicados en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-129">**Possible Cause** : An error occurred while processing two acknowledgments (Commit and Application ACKs) without duplicate errors in the Event Log.</span></span> <span data-ttu-id="fa7a5-130">En su lugar, recibirá una 4133 de Id. de evento para cada una de las dos confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-130">Instead, you receive one Event ID 4133 for each of the two ACKs.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="fa7a5-131"> crea una entrada de registro para cada confirmación genera.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-131"> creates a log entry for each ACK it generates.</span></span>  
  
<span data-ttu-id="fa7a5-132">**Resolución** : asegúrese de que los mensajes tienen un campo MSH11 correctamente con formato y rellenado.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-132">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH11 field.</span></span>  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a><span data-ttu-id="fa7a5-133">Enviar canalización genera un error al usar el adaptador MLLP de 2 vías</span><span class="sxs-lookup"><span data-stu-id="fa7a5-133">Send pipeline generates an error when using the 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="fa7a5-134">Síntoma</span><span class="sxs-lookup"><span data-stu-id="fa7a5-134">Symptom</span></span>  
 <span data-ttu-id="fa7a5-135">Obtendrá el error siguiente o similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="fa7a5-135">You get the following or similar error in the Event Log:</span></span>  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "Microsoft.Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
<span data-ttu-id="fa7a5-136">**Causa posible** : la aplicación receptora no responde con una confirmación y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se espera una respuesta de la aplicación receptora.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-136">**Possible Cause** : The receiving application does not respond with an Acknowledgment and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is expecting a response from the receiving application.</span></span>  
  
<span data-ttu-id="fa7a5-137">**Resolución** : Esto es así por diseño, y puede omitir el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="fa7a5-137">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7a5-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa7a5-138">See Also</span></span>  
 [<span data-ttu-id="fa7a5-139">Solución de problemas y problemas conocidos en HL7</span><span class="sxs-lookup"><span data-stu-id="fa7a5-139">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)