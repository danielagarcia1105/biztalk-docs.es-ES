---
title: Compatibilidad con EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04cd9c14b9c3663bdf332155cc9824e1681ca7a6
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710299"
---
# <a name="edi-support-in-biztalk-server"></a><span data-ttu-id="d487c-102">Compatibilidad con EDI en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d487c-102">EDI Support in BizTalk Server</span></span>
<span data-ttu-id="d487c-103">EDI está integrada en BizTalk Server y es un componente opcional al instalar y configurar BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d487c-103">EDI is built-in to BizTalk Server, and is an optional component when you install and configure BizTalk Server.</span></span> 
  
## <a name="feature-set-comparison-chart"></a><span data-ttu-id="d487c-104">Comparación de conjunto de características</span><span class="sxs-lookup"><span data-stu-id="d487c-104">Feature Set Comparison Chart</span></span>  
 <span data-ttu-id="d487c-105">La siguiente tabla muestra la compatibilidad EDI que se incluyen con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d487c-105">The following table shows the EDI support included with BizTalk Server.</span></span>
  
|<span data-ttu-id="d487c-106">Característica</span><span class="sxs-lookup"><span data-stu-id="d487c-106">Feature</span></span>|<span data-ttu-id="d487c-107">Comentario</span><span class="sxs-lookup"><span data-stu-id="d487c-107">Comment</span></span>|  
|---|---|
|<span data-ttu-id="d487c-108">Modificación del segmento ISA en el conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="d487c-108">ISA    Segment modification at transaction set</span></span>| <span data-ttu-id="d487c-109">Crear acuerdos específicos de conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="d487c-109">Create TransactionSet-specific agreements</span></span>|  
|<span data-ttu-id="d487c-110">ISA11: Estados Unidos u otros estándares</span><span class="sxs-lookup"><span data-stu-id="d487c-110">ISA11:    US or other standard type</span></span>| |  
|<span data-ttu-id="d487c-111">ISA12: Versión de Control de intercambio</span><span class="sxs-lookup"><span data-stu-id="d487c-111">ISA12:    Interchange Control Version</span></span>| |  
|<span data-ttu-id="d487c-112">ISA13: Número de Control de intercambio (aumento del número)</span><span class="sxs-lookup"><span data-stu-id="d487c-112">ISA13:    Interchange Control Number (incrementing number)</span></span>| |  
|<span data-ttu-id="d487c-113">ISA15: Prueba o producción</span><span class="sxs-lookup"><span data-stu-id="d487c-113">ISA15:    Test or Production</span></span>| |  
|<span data-ttu-id="d487c-114">Modificación del segmento GS en el nivel de documento o transacción</span><span class="sxs-lookup"><span data-stu-id="d487c-114">GS    Segment modification at document/transaction level</span></span>| |  
|<span data-ttu-id="d487c-115">GS remitente/receptor de GS permitido sea distinto a ISA</span><span class="sxs-lookup"><span data-stu-id="d487c-115">GS    sender/receiver IDs allowed to be different than ISA</span></span>| |  
|<span data-ttu-id="d487c-116">Identificadores de documento de entrada distinto de ISA y GS de salida</span><span class="sxs-lookup"><span data-stu-id="d487c-116">Inbound    Document IDs different than ISA & GS Outbound IDs</span></span>| |  
|<span data-ttu-id="d487c-117">GS01: Capacidad para cambiar el tipo de documento</span><span class="sxs-lookup"><span data-stu-id="d487c-117">GS01:    Ability to change type of document</span></span>| |  
|<span data-ttu-id="d487c-118">GS04: Fecha (posibilidad de cambiar el formato)</span><span class="sxs-lookup"><span data-stu-id="d487c-118">GS04:    Date (Ability to change format)</span></span>|<span data-ttu-id="d487c-119">Contiene la interfaz de usuario para seleccionar formatos como SSAAMMDD y AAMMDD</span><span class="sxs-lookup"><span data-stu-id="d487c-119">Contains UI to select format as CCYYMMDD and YYMMDD</span></span>|  
|<span data-ttu-id="d487c-120">GS05: Hora (posibilidad de cambiar el formato)</span><span class="sxs-lookup"><span data-stu-id="d487c-120">GS05:    Time (Ability to change format)</span></span>|<span data-ttu-id="d487c-121">Contiene la interfaz de usuario para seleccionar formatos como HHMM, HHMMSS y HHMMSSdd</span><span class="sxs-lookup"><span data-stu-id="d487c-121">Contains UI to select format as HHMM, HHMMSS, and HHMMSSdd</span></span>|  
|<span data-ttu-id="d487c-122">GS06: Cambiar el número de control</span><span class="sxs-lookup"><span data-stu-id="d487c-122">GS06:    Change the control number</span></span>| |  
|<span data-ttu-id="d487c-123">GS07: Agencia código</span><span class="sxs-lookup"><span data-stu-id="d487c-123">GS07:    Agency Code</span></span>| |  
|<span data-ttu-id="d487c-124">GS08: Posibilidad de colocarlo en versiones estándar</span><span class="sxs-lookup"><span data-stu-id="d487c-124">GS08:    Able to put in standards version</span></span>| |  
|<span data-ttu-id="d487c-125">Capacidad de reemplazar el sobre EDI en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d487c-125">Ability to override EDI envelope at runtime</span></span>| |  
|<span data-ttu-id="d487c-126">Esquemas EDI personalizados</span><span class="sxs-lookup"><span data-stu-id="d487c-126">Custom    EDI Schemas</span></span>| |  
|<span data-ttu-id="d487c-127">Organización/configuración de entidades</span><span class="sxs-lookup"><span data-stu-id="d487c-127">Organization/Party Setting</span></span>|<span data-ttu-id="d487c-128">Crear entidad independiente y contratos.</span><span class="sxs-lookup"><span data-stu-id="d487c-128">Create separate party and agreements.</span></span> <span data-ttu-id="d487c-129">Crear acuerdos a partir de plantillas.</span><span class="sxs-lookup"><span data-stu-id="d487c-129">Also create agreements based off templates.</span></span>|  
|<span data-ttu-id="d487c-130">Enrutamiento a través de la definición de documento de documentos EDI</span><span class="sxs-lookup"><span data-stu-id="d487c-130">EDI    document routing via document definition</span></span>| |  
|<span data-ttu-id="d487c-131">Confirmaciones 997 automáticas a socios comerciales</span><span class="sxs-lookup"><span data-stu-id="d487c-131">Automatic 997’s to trading partners</span></span>|<span data-ttu-id="d487c-132">Configuración específica para perfiles de negocio</span><span class="sxs-lookup"><span data-stu-id="d487c-132">Configuration specific to business profiles</span></span>|  
|<span data-ttu-id="d487c-133">Confiable de mensajería a través de 997 de salida EDI</span><span class="sxs-lookup"><span data-stu-id="d487c-133">Outbound    EDI reliable messaging via 997’s</span></span>| |  
|<span data-ttu-id="d487c-134">Compatibilidad con EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d487c-134">EDIFACT    Support</span></span>|<span data-ttu-id="d487c-135">Admite D93 a D05 según ISO 9735 v4.1</span><span class="sxs-lookup"><span data-stu-id="d487c-135">Supports D93 to D05 per ISO 9735 v4.1</span></span>|  
|<span data-ttu-id="d487c-136">Admitir X12</span><span class="sxs-lookup"><span data-stu-id="d487c-136">X12    Support</span></span>|<span data-ttu-id="d487c-137">2040 a 5030</span><span class="sxs-lookup"><span data-stu-id="d487c-137">2040 to 5030</span></span>|  
|<span data-ttu-id="d487c-138">Compatibilidad con HIPAA</span><span class="sxs-lookup"><span data-stu-id="d487c-138">HIPAA support</span></span>| <span data-ttu-id="d487c-139">Acelerador de Microsoft BizTalk para HIPAA (BTAHIPAA) como parte de la funcionalidad nativa de EDI</span><span class="sxs-lookup"><span data-stu-id="d487c-139">Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) as  part of native EDI functionality</span></span>|  
|<span data-ttu-id="d487c-140">Posibilidad de quitar enumeradores/listas de códigos</span><span class="sxs-lookup"><span data-stu-id="d487c-140">Ability to remove enumerators/codelists</span></span>|<span data-ttu-id="d487c-141">Utilice el Editor de Visual Studio/BizTalk</span><span class="sxs-lookup"><span data-stu-id="d487c-141">Use Visual Studio/BizTalk Editor</span></span>|  
|<span data-ttu-id="d487c-142">AS2 Envío y recepción</span><span class="sxs-lookup"><span data-stu-id="d487c-142">AS2    Send/Receive</span></span>| <span data-ttu-id="d487c-143">AS2 es el certificado Drummond para la compatibilidad con varios archivos adjuntos, la compatibilidad con la conservación de nombres de archivo y la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="d487c-143">AS2 is Drummond Certified for multi-file attachment support, file name preservation support and interoperability.</span></span>|  
|<span data-ttu-id="d487c-144">Conservación de nombre de archivo de AS2</span><span class="sxs-lookup"><span data-stu-id="d487c-144">AS2 file name preservation</span></span>| |  
|<span data-ttu-id="d487c-145">Mensajería confiable de AS2</span><span class="sxs-lookup"><span data-stu-id="d487c-145">AS2 reliable messaging</span></span>| |  
|<span data-ttu-id="d487c-146">Procesamiento por lotes (acumulación de varios tipos de transacciones en una única transacción)</span><span class="sxs-lookup"><span data-stu-id="d487c-146">Outbound    Batching (accumulating multiple transaction types in a single transaction)</span></span>|<span data-ttu-id="d487c-147">Admite varias configuraciones de lote para cada perfil de negocio</span><span class="sxs-lookup"><span data-stu-id="d487c-147">Supports multiple batch configurations for each business profile</span></span>|  
|<span data-ttu-id="d487c-148">Entrada de procesamiento por lotes: intercambio XML (conservar un intercambio "por lotes" entrante) o el XML de conjunto de transacciones basado en las opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="d487c-148">Inbound    Batching – Interchange XML (preserving an incoming ‘batched’ interchange) or Transaction Set XML based off configuration options</span></span>|<span data-ttu-id="d487c-149">También admite la entrada-anulando, es decir, división de intercambios en Xml de conjunto de transacciones individual</span><span class="sxs-lookup"><span data-stu-id="d487c-149">Also supports inbound-debatching, i.e., splitting interchange into individual Transaction Set Xml</span></span>|  
|<span data-ttu-id="d487c-150">Intercambio y conjunto de transacciones generación y validación en tiempo de diseño en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d487c-150">Interchange    and Transaction Set Generation and Validation in Design Time in Visual Studio</span></span>| |  
|<span data-ttu-id="d487c-151">Conciliación y generación de TA1 (confirmación técnica)</span><span class="sxs-lookup"><span data-stu-id="d487c-151">TA1    (Technical ACK) Generation and Reconciliation</span></span>| |  
|<span data-ttu-id="d487c-152">Marcas de validación XSD y EDI opcional</span><span class="sxs-lookup"><span data-stu-id="d487c-152">Optional    EDI and XSD Validation flags</span></span>| |  
|<span data-ttu-id="d487c-153">Formato de documento/definición en nivel GS</span><span class="sxs-lookup"><span data-stu-id="d487c-153">Document    format/definition at GS level</span></span>| |  
  
## <a name="see-also"></a><span data-ttu-id="d487c-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="d487c-154">See Also</span></span>  
 <span data-ttu-id="d487c-155">[Compatibilidad con los estándares EDI](../core/edi-standards-support.md) </span><span class="sxs-lookup"><span data-stu-id="d487c-155">[EDI Standards Support](../core/edi-standards-support.md) </span></span>  
 <span data-ttu-id="d487c-156">[Compatibilidad con esquema de documento EDI](../core/edi-document-schema-support.md) </span><span class="sxs-lookup"><span data-stu-id="d487c-156">[EDI Document Schema Support](../core/edi-document-schema-support.md) </span></span>  
 [<span data-ttu-id="d487c-157">Compatibilidad de juegos de caracteres de EDI</span><span class="sxs-lookup"><span data-stu-id="d487c-157">EDI Character Set Support</span></span>](../core/edi-character-set-support.md)