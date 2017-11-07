---
title: "Asignación de TIBCO Rendezvous de mensajes | Documentos de Microsoft"
description: "Campos de mensajes y asignación de mensaje a XML en el adaptador de BizTalk para TIBCO Rendezvous"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb80ea4f908aa50dc32755c333aa3ccf2ea4db91
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="feeb0-103">Asignación de mensajes en TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="feeb0-103">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="feeb0-104">Los mensajes de TIBCO Rendezvous constan de información de encabezado y un conjunto de campos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="feeb0-104">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="feeb0-105">La información de encabezado se asigna directamente a propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="feeb0-105">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="feeb0-106">Elementos del campo de mensaje</span><span class="sxs-lookup"><span data-stu-id="feeb0-106">Message Field Elements</span></span>  
 <span data-ttu-id="feeb0-107">Un campo de mensaje se compone de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="feeb0-107">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="feeb0-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="feeb0-108">Element</span></span>|<span data-ttu-id="feeb0-109">Description</span><span class="sxs-lookup"><span data-stu-id="feeb0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="feeb0-110">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="feeb0-110">**Name**</span></span>|<span data-ttu-id="feeb0-111">Cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="feeb0-111">Character string.</span></span> <span data-ttu-id="feeb0-112">No tiene que ser única en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="feeb0-112">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="feeb0-113">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="feeb0-113">**Identifier**</span></span>|<span data-ttu-id="feeb0-114">Entero corto.</span><span class="sxs-lookup"><span data-stu-id="feeb0-114">Short integer.</span></span> <span data-ttu-id="feeb0-115">Único en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="feeb0-115">Unique in a message.</span></span> <span data-ttu-id="feeb0-116">Implícitamente limita el número de campos de mensajes y 65535.</span><span class="sxs-lookup"><span data-stu-id="feeb0-116">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="feeb0-117">El ámbito del identificador es el mensaje (o submensaje).</span><span class="sxs-lookup"><span data-stu-id="feeb0-117">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="feeb0-118">Se puede usar el mismo identificador en dos submensajes, que son a su vez parte de un mensaje de contenido.</span><span class="sxs-lookup"><span data-stu-id="feeb0-118">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="feeb0-119">**Valor**</span><span class="sxs-lookup"><span data-stu-id="feeb0-119">**Value**</span></span>|<span data-ttu-id="feeb0-120">Los datos del campo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="feeb0-120">The message field data.</span></span>|  
|<span data-ttu-id="feeb0-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="feeb0-121">**Count**</span></span>|<span data-ttu-id="feeb0-122">Número de elementos (en caso de una matriz)</span><span class="sxs-lookup"><span data-stu-id="feeb0-122">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="feeb0-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="feeb0-123">**Type**</span></span>|<span data-ttu-id="feeb0-124">Tipo del campo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="feeb0-124">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="feeb0-125">Proceso de asignación</span><span class="sxs-lookup"><span data-stu-id="feeb0-125">Mapping Process</span></span>  
 <span data-ttu-id="feeb0-126">Los mensajes estructurados de TIBCO Rendezvous se asignan a elementos de XML de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="feeb0-126">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="feeb0-127">**Nombre** se utiliza como el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="feeb0-127">**Name** is used as the element name.</span></span> <span data-ttu-id="feeb0-128">El nombre de campo de TIBCO Rendezvous puede contener caracteres que no son válidos para su uso en nombres de elementos de XML.</span><span class="sxs-lookup"><span data-stu-id="feeb0-128">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="feeb0-129">El adaptador genera asignaciones de caracteres válidos entre mensajes estructurados de XML y TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="feeb0-129">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="feeb0-130">**Identificador** se coloca en un atributo 'id'.</span><span class="sxs-lookup"><span data-stu-id="feeb0-130">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="feeb0-131">**Valor** contiene una representación de cadena que es el cuerpo del elemento.</span><span class="sxs-lookup"><span data-stu-id="feeb0-131">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="feeb0-132">**Recuento de** se omite.</span><span class="sxs-lookup"><span data-stu-id="feeb0-132">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="feeb0-133">**Tipo** información se coloca en un atributo xsi: Type para el elemento generado.</span><span class="sxs-lookup"><span data-stu-id="feeb0-133">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="feeb0-134">Para obtener más información, consulte [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span><span class="sxs-lookup"><span data-stu-id="feeb0-134">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feeb0-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="feeb0-135">See Also</span></span>  
 <span data-ttu-id="feeb0-136">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="feeb0-136">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="feeb0-137">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="feeb0-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)