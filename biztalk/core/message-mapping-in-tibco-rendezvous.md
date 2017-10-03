---
title: "Asignación de TIBCO Rendezvous de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, mapping
- message mapping
- message field elements
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5b3559067dbb998240a3fc814d890701e2591c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="e5f1a-102">Asignación de mensajes en TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="e5f1a-102">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="e5f1a-103">Los mensajes de TIBCO Rendezvous constan de información de encabezado y un conjunto de campos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-103">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="e5f1a-104">La información de encabezado se asigna directamente a propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-104">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="e5f1a-105">Elementos del campo de mensaje</span><span class="sxs-lookup"><span data-stu-id="e5f1a-105">Message Field Elements</span></span>  
 <span data-ttu-id="e5f1a-106">Un campo de mensaje se compone de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e5f1a-106">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="e5f1a-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5f1a-107">Element</span></span>|<span data-ttu-id="e5f1a-108">Description</span><span class="sxs-lookup"><span data-stu-id="e5f1a-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5f1a-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e5f1a-109">**Name**</span></span>|<span data-ttu-id="e5f1a-110">Cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-110">Character string.</span></span> <span data-ttu-id="e5f1a-111">No tiene que ser única en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-111">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="e5f1a-112">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="e5f1a-112">**Identifier**</span></span>|<span data-ttu-id="e5f1a-113">Entero corto.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-113">Short integer.</span></span> <span data-ttu-id="e5f1a-114">Único en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-114">Unique in a message.</span></span> <span data-ttu-id="e5f1a-115">Implícitamente limita el número de campos de mensajes y 65535.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-115">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="e5f1a-116">El ámbito del identificador es el mensaje (o submensaje).</span><span class="sxs-lookup"><span data-stu-id="e5f1a-116">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="e5f1a-117">Se puede usar el mismo identificador en dos submensajes, que son a su vez parte de un mensaje de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-117">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="e5f1a-118">**Valor**</span><span class="sxs-lookup"><span data-stu-id="e5f1a-118">**Value**</span></span>|<span data-ttu-id="e5f1a-119">Los datos del campo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-119">The message field data.</span></span>|  
|<span data-ttu-id="e5f1a-120">**Count**</span><span class="sxs-lookup"><span data-stu-id="e5f1a-120">**Count**</span></span>|<span data-ttu-id="e5f1a-121">Número de elementos (en caso de una matriz)</span><span class="sxs-lookup"><span data-stu-id="e5f1a-121">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="e5f1a-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e5f1a-122">**Type**</span></span>|<span data-ttu-id="e5f1a-123">Tipo del campo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-123">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="e5f1a-124">Proceso de asignación</span><span class="sxs-lookup"><span data-stu-id="e5f1a-124">Mapping Process</span></span>  
 <span data-ttu-id="e5f1a-125">Los mensajes estructurados de TIBCO Rendezvous se asignan a elementos de XML de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f1a-125">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="e5f1a-126">**Nombre** se utiliza como el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-126">**Name** is used as the element name.</span></span> <span data-ttu-id="e5f1a-127">El nombre de campo de TIBCO Rendezvous puede contener caracteres que no son válidos para su uso en nombres de elementos de XML.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-127">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="e5f1a-128">El adaptador genera asignaciones de caracteres válidos entre mensajes estructurados de XML y TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-128">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="e5f1a-129">**Identificador** se coloca en un atributo 'id'.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-129">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="e5f1a-130">**Valor** contiene una representación de cadena que es el cuerpo del elemento.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-130">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="e5f1a-131">**Recuento de** se omite.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-131">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="e5f1a-132">**Tipo** información se coloca en un atributo xsi: Type para el elemento generado.</span><span class="sxs-lookup"><span data-stu-id="e5f1a-132">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="e5f1a-133">Para obtener más información, consulte [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span><span class="sxs-lookup"><span data-stu-id="e5f1a-133">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f1a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5f1a-134">See Also</span></span>  
 <span data-ttu-id="e5f1a-135">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="e5f1a-135">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="e5f1a-136">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="e5f1a-136">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)