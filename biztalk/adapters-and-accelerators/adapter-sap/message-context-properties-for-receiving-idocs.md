---
title: Propiedades de contexto del mensaje para recibir IDOC | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca289e37cac15972e75c69d7ad20928b72911963
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-for-receiving-idocs"></a><span data-ttu-id="147cc-102">Propiedades de contexto de mensaje para recibir IDOC</span><span class="sxs-lookup"><span data-stu-id="147cc-102">Message Context Properties for Receiving IDOCs</span></span>
<span data-ttu-id="147cc-103">Para recibir un IDOC mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="147cc-103">For receiving an IDOC using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
 <span data-ttu-id="147cc-104">**Propiedades de registro de Control de IDOC.**</span><span class="sxs-lookup"><span data-stu-id="147cc-104">**IDOC Control Record properties.**</span></span>  
  
-   <span data-ttu-id="147cc-105">**TABNAM** -nombre de la estructura de tabla</span><span class="sxs-lookup"><span data-stu-id="147cc-105">**TABNAM** - Name of table structure</span></span>  
  
-   <span data-ttu-id="147cc-106">**MANDT** -cliente</span><span class="sxs-lookup"><span data-stu-id="147cc-106">**MANDT** - Client</span></span>  
  
-   <span data-ttu-id="147cc-107">**DOCNUM** -número IDOC</span><span class="sxs-lookup"><span data-stu-id="147cc-107">**DOCNUM** - IDOC number</span></span>  
  
-   <span data-ttu-id="147cc-108">**DOCREL** -versión SAP para IDOC</span><span class="sxs-lookup"><span data-stu-id="147cc-108">**DOCREL** - SAP Release for IDOC</span></span>  
  
-   <span data-ttu-id="147cc-109">**ESTADO** -estado de IDOC</span><span class="sxs-lookup"><span data-stu-id="147cc-109">**STATUS** - Status of IDOC</span></span>  
  
-   <span data-ttu-id="147cc-110">**DIRECTA** -dirección</span><span class="sxs-lookup"><span data-stu-id="147cc-110">**DIRECT** - Direction</span></span>  
  
-   <span data-ttu-id="147cc-111">**OUTMOD** -modo de salida</span><span class="sxs-lookup"><span data-stu-id="147cc-111">**OUTMOD** - Output mode</span></span>  
  
-   <span data-ttu-id="147cc-112">**EXPRESARSE** : reemplazo en el procesamiento de entrada</span><span class="sxs-lookup"><span data-stu-id="147cc-112">**EXPRSS** - Overriding in inbound processing</span></span>  
  
-   <span data-ttu-id="147cc-113">**PRUEBA** -indicador de prueba</span><span class="sxs-lookup"><span data-stu-id="147cc-113">**TEST** - Test flag</span></span>  
  
-   <span data-ttu-id="147cc-114">**IDOCTYP** -nombre del tipo básico</span><span class="sxs-lookup"><span data-stu-id="147cc-114">**IDOCTYP** - Name of basic type</span></span>  
  
-   <span data-ttu-id="147cc-115">**CIMTYP** -extensión (definida por el cliente)</span><span class="sxs-lookup"><span data-stu-id="147cc-115">**CIMTYP** - Extension (defined by customer)</span></span>  
  
-   <span data-ttu-id="147cc-116">**MESTYP** -tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="147cc-116">**MESTYP** - Message type</span></span>  
  
-   <span data-ttu-id="147cc-117">**MESCOD** -código del mensaje</span><span class="sxs-lookup"><span data-stu-id="147cc-117">**MESCOD** - Message code</span></span>  
  
-   <span data-ttu-id="147cc-118">**MESFCT** -Message (función)</span><span class="sxs-lookup"><span data-stu-id="147cc-118">**MESFCT** - Message function</span></span>  
  
-   <span data-ttu-id="147cc-119">**STD** -marca estándar, EDI</span><span class="sxs-lookup"><span data-stu-id="147cc-119">**STD** - EDI standard, flag</span></span>  
  
-   <span data-ttu-id="147cc-120">**STDVRS** -EDI estándar, versión y lanzamiento</span><span class="sxs-lookup"><span data-stu-id="147cc-120">**STDVRS** - EDI standard, version and release</span></span>  
  
-   <span data-ttu-id="147cc-121">**STDMES** -tipo de mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="147cc-121">**STDMES** - EDI message type</span></span>  
  
-   <span data-ttu-id="147cc-122">**SNDPOR** -puerto de remitente (sistema de SAP, subsistema externo)</span><span class="sxs-lookup"><span data-stu-id="147cc-122">**SNDPOR** - Sender port (SAP System, external subsystem)</span></span>  
  
-   <span data-ttu-id="147cc-123">**SNDPRT** -tipo de remitente de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="147cc-123">**SNDPRT** - Partner type of sender</span></span>  
  
-   <span data-ttu-id="147cc-124">**SNDPFC** -función de remitente de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="147cc-124">**SNDPFC** - Partner Function of Sender</span></span>  
  
-   <span data-ttu-id="147cc-125">**SNDPRN** -número de remitente de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="147cc-125">**SNDPRN** - Partner Number of Sender</span></span>  
  
-   <span data-ttu-id="147cc-126">**SNDSAD** -dirección de remitente (SADR)</span><span class="sxs-lookup"><span data-stu-id="147cc-126">**SNDSAD** - Sender address (SADR)</span></span>  
  
-   <span data-ttu-id="147cc-127">**SNDLAD** -dirección lógica del remitente</span><span class="sxs-lookup"><span data-stu-id="147cc-127">**SNDLAD** - Logical address of sender</span></span>  
  
-   <span data-ttu-id="147cc-128">**RCVPOR** -de puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="147cc-128">**RCVPOR** - Receiver port</span></span>  
  
-   <span data-ttu-id="147cc-129">**RCVPRT** -tipo de socio comercial del receptor</span><span class="sxs-lookup"><span data-stu-id="147cc-129">**RCVPRT** - Partner Type of receiver</span></span>  
  
-   <span data-ttu-id="147cc-130">**RCVPFC** -función del destinatario de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="147cc-130">**RCVPFC** - Partner function of recipient</span></span>  
  
-   <span data-ttu-id="147cc-131">**RCVPRN** -número de destinatario de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="147cc-131">**RCVPRN** - Partner number of recipient</span></span>  
  
-   <span data-ttu-id="147cc-132">**RCVSAD** -dirección de destinatario (SADR)</span><span class="sxs-lookup"><span data-stu-id="147cc-132">**RCVSAD** - Recipient address (SADR)</span></span>  
  
-   <span data-ttu-id="147cc-133">**RCVLAD** -dirección lógica del destinatario</span><span class="sxs-lookup"><span data-stu-id="147cc-133">**RCVLAD** - Logical address of recipient</span></span>  
  
-   <span data-ttu-id="147cc-134">**CREDAT** : creado en</span><span class="sxs-lookup"><span data-stu-id="147cc-134">**CREDAT** - Created on</span></span>  
  
-   <span data-ttu-id="147cc-135">**CRETIM** -hora de creación</span><span class="sxs-lookup"><span data-stu-id="147cc-135">**CRETIM** - Time Created</span></span>  
  
-   <span data-ttu-id="147cc-136">**REFINT** -archivo de transmisión (intercambio de EDI)</span><span class="sxs-lookup"><span data-stu-id="147cc-136">**REFINT** - Transmission file (EDI Interchange)</span></span>  
  
-   <span data-ttu-id="147cc-137">**REFGRP** -grupo de mensajes (grupo de mensajes de EDI)</span><span class="sxs-lookup"><span data-stu-id="147cc-137">**REFGRP** - Message group (EDI Message Group)</span></span>  
  
-   <span data-ttu-id="147cc-138">**REFMES** -EDI (mensaje)</span><span class="sxs-lookup"><span data-stu-id="147cc-138">**REFMES** - Message (EDI Message)</span></span>  
  
-   <span data-ttu-id="147cc-139">**ARCKEY** - Key para el archivo de mensaje externo</span><span class="sxs-lookup"><span data-stu-id="147cc-139">**ARCKEY** - Key for external message archive</span></span>  
  
-   <span data-ttu-id="147cc-140">**SERIE** -serialización</span><span class="sxs-lookup"><span data-stu-id="147cc-140">**SERIAL** - Serialization</span></span>  
  
-   <span data-ttu-id="147cc-141">**DOCTYP** -tipo IDOC (Esto solo está disponible en EDI_DC.</span><span class="sxs-lookup"><span data-stu-id="147cc-141">**DOCTYP** - IDOC type (This is available in EDI_DC only.</span></span> <span data-ttu-id="147cc-142">Debe estar presente en la propiedad de contexto, pero debe promocionar solo para la versión 2 idoc)</span><span class="sxs-lookup"><span data-stu-id="147cc-142">Should be present in the context property but should be promoted for Version 2 IDOCs only)</span></span>  
  
 <span data-ttu-id="147cc-143">**TID** : representa el TID enviado por el sistema SAP para las llamadas TRFC entrantes.</span><span class="sxs-lookup"><span data-stu-id="147cc-143">**TID** – Represents the TID sent by the SAP system for the incoming TRFC call.</span></span>  
  
 <span data-ttu-id="147cc-144">**GUID** : representa el GUID que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="147cc-144">**GUID** – Represents the GUID which the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses internally.</span></span> <span data-ttu-id="147cc-145">Esto tiene una asignación unívoca con el TID que se recibió desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="147cc-145">This has a one-to-one mapping with the TID which was received from the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147cc-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="147cc-146">See Also</span></span>  
 [<span data-ttu-id="147cc-147">Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="147cc-147">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)