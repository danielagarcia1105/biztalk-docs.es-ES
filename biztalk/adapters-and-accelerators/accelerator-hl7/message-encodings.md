---
title: "Codificación de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36063416e1c5d1f30c9cb9c26056299f0b926a50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-encodings"></a><span data-ttu-id="6e707-102">Codificaciones de mensaje</span><span class="sxs-lookup"><span data-stu-id="6e707-102">Message Encodings</span></span>
<span data-ttu-id="6e707-103">No es suficiente para definir la semántica de mensaje para HL7 sean útiles.</span><span class="sxs-lookup"><span data-stu-id="6e707-103">It is not sufficient to define message semantics in order for HL7 to be useful.</span></span> <span data-ttu-id="6e707-104">Una vez que se ha determinado el contenido del mensaje, el estándar tiene que explicar cómo representar el contenido en una interfaz real.</span><span class="sxs-lookup"><span data-stu-id="6e707-104">Once message content has been determined, the standard has to explain how to represent that content in an actual interface.</span></span> <span data-ttu-id="6e707-105">Es decir, debe haber especificado "codificación de mensajes".</span><span class="sxs-lookup"><span data-stu-id="6e707-105">That is to say, there must be a specified "message encoding".</span></span> <span data-ttu-id="6e707-106">HL7 versión 2 admite dos formatos de codificación de mensajes, una codificación basado en delimitadores personalizada y una codificación XML.</span><span class="sxs-lookup"><span data-stu-id="6e707-106">HL7 Version 2 supports two forms of message encoding, a custom delimiter-based encoding, and an XML encoding.</span></span>  
  
 <span data-ttu-id="6e707-107">HL7 eligió la original basado en delimitadores codificación para reducir el tamaño de mensajes tanto como sea posibles.</span><span class="sxs-lookup"><span data-stu-id="6e707-107">HL7 chose the original delimiter-based encoding to reduce the size of messages as much as possible.</span></span> <span data-ttu-id="6e707-108">Por ejemplo, si se compara una estructura de datos en el que los delimitadores separan los elementos a una estructura que cada elemento se coloca en un conjunto fijo de posiciones, la estructura basado en delimitadores es mucho más barata si) mensajes no contienen algunos elementos y b) algunos elementos no llenar todo el espacio permitido.</span><span class="sxs-lookup"><span data-stu-id="6e707-108">For example, if you compare a data structure in which delimiters separate elements to a structure that positions each element in a fixed set of positions, the delimiter-based structure is far more economical if a) messages do not contain some elements, and b) some elements do not fill all the space allowed.</span></span> <span data-ttu-id="6e707-109">La única sobrecarga en las estructuras basadas en delimitador es los delimitadores por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="6e707-109">The only overhead in delimiter-based structures is the delimiters themselves.</span></span>  
  
 <span data-ttu-id="6e707-110">La codificación original de HL7 define cinco delimitadores, que cada mensaje se declara dentro del segmento de MSH.</span><span class="sxs-lookup"><span data-stu-id="6e707-110">The original HL7 encoding defines five delimiters, which each message declares within the MSH segment.</span></span> <span data-ttu-id="6e707-111">Éstas indican:</span><span class="sxs-lookup"><span data-stu-id="6e707-111">These indicate:</span></span>  
  
-   <span data-ttu-id="6e707-112">Segmentos</span><span class="sxs-lookup"><span data-stu-id="6e707-112">Segments</span></span>  
  
-   <span data-ttu-id="6e707-113">Campos</span><span class="sxs-lookup"><span data-stu-id="6e707-113">Fields</span></span>  
  
-   <span data-ttu-id="6e707-114">Components</span><span class="sxs-lookup"><span data-stu-id="6e707-114">Components</span></span>  
  
-   <span data-ttu-id="6e707-115">Subcomponentes</span><span class="sxs-lookup"><span data-stu-id="6e707-115">Subcomponents</span></span>  
  
-   <span data-ttu-id="6e707-116">Repetición (de un campo, componente o subcomponente)</span><span class="sxs-lookup"><span data-stu-id="6e707-116">Repetition (of a field, component, or subcomponent)</span></span>  
  
 <span data-ttu-id="6e707-117">Tenga en cuenta que puesto que los delimitadores son un aspecto fundamental de la codificación, debe definirlos en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="6e707-117">Note that since delimiters are a fundamental aspect of the encoding, you must define them first.</span></span> <span data-ttu-id="6e707-118">Una de las consecuencias es que no puede haber ningún subdirectorio sub-delimitador.</span><span class="sxs-lookup"><span data-stu-id="6e707-118">One result of this is that there can be no sub-sub-delimiter.</span></span> <span data-ttu-id="6e707-119">A veces, esta limitación tiene efectos indeseable en el diseño de nuevos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="6e707-119">At times, this limitation has unfortunate effects upon the design of new data types.</span></span>  
  
 <span data-ttu-id="6e707-120">En junio de 2003, HL7 publicado HL7 versión 2, la sintaxis de codificación de XML, la versión 1.</span><span class="sxs-lookup"><span data-stu-id="6e707-120">In June 2003, HL7 published HL7 Version 2, XML Encoding Syntax, Release 1.</span></span> <span data-ttu-id="6e707-121">Este estándar define reglas de codificación alternativas para los mensajes de HL7 versión 2.3.1 y 2.4 y proporciona un mecanismo para determinar las reglas de codificación alternativas para HL7 posteriores versiones 2.X.</span><span class="sxs-lookup"><span data-stu-id="6e707-121">This standard defines alternate encoding rules for HL7 Version 2.3.1 and 2.4 messages, and provides a mechanism for determining alternate encoding rules for subsequent HL7 2.X versions.</span></span> <span data-ttu-id="6e707-122">En esencia, este nuevo estándar define las etiquetas del elemento XML de la versión 2.3.1 y mensajes abstractos V2.4, segmentos, campos y tipos de datos y crea las reglas para definir las etiquetas necesarias para las nuevas estructuras creadas para versiones posteriores de la versión 2 estándares.</span><span class="sxs-lookup"><span data-stu-id="6e707-122">In essence, this new standard defines XML element tags for the Version 2.3.1 and V2.4 abstract messages, segments, fields, and data types, and creates rules for defining the tags needed for any new structures created for subsequent versions of the Version 2 standard.</span></span> <span data-ttu-id="6e707-123">El proceso de definición de esta norma dio lugar a una serie de mejoras en las versiones 2.4 y 2.5.</span><span class="sxs-lookup"><span data-stu-id="6e707-123">The process of defining this standard led to a series of improvements in versions 2.4 and 2.5.</span></span> <span data-ttu-id="6e707-124">Esto se deba a que la creación de etiquetas XML ha provocado la necesidad de abordar ciertas ambigüedades enfoque en el estándar subyacente.</span><span class="sxs-lookup"><span data-stu-id="6e707-124">This happened because creation of XML tags led to the need to address some longstanding ambiguities in the underlying standard.</span></span> <span data-ttu-id="6e707-125">As a result, se crearon los códigos de estructura de mensaje) bien definido para indicar las variaciones en los mensajes abstractas asociados con los eventos de desencadenador, b) repetir grupos de segmentos con un mensaje abstracto formalmente se identificaron y con nombre y c) localmente tipo de datos definido, CM se reemplazó por tipos más específicos.</span><span class="sxs-lookup"><span data-stu-id="6e707-125">As a result, a) well-defined message structure codes were created to indicate variations in the abstract messages associated with trigger events, b) repeating groups of segments with an abstract message were formally identified and named, and c) the locally defined data type, CM was replaced with more specific types.</span></span>  
  
 <span data-ttu-id="6e707-126">Por ejemplo, el siguiente es un mensaje de confirmación simple utilizando el formato delimitado por la canalización tradicional:</span><span class="sxs-lookup"><span data-stu-id="6e707-126">For example, the following is a simple acknowledgment message using the traditional pipe delimited format:</span></span>  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 <span data-ttu-id="6e707-127">Por el contrario, el siguiente es el mismo mensaje que se representa como un documento XML:</span><span class="sxs-lookup"><span data-stu-id="6e707-127">By contrast, the following is the same message represented as an XML document:</span></span>  
  
```  
<ACK  
xmlns="urn:hl7-org:v2xml"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="urn:hl7-org:v2xml ACK.xsd">  
   <MSH>  
      <MSH.1>|</MSH.1>  
      <MSH.2>^~\&</MSH.2>  
      <MSH.3>  
         <HD.1>LAB</HD.1>  
      </MSH.3>  
      <MSH.4>  
         <HD.1>767543</HD.1>  
      </MSH.4>  
      <MSH.5>  
         <HD.1>ADT</HD.1>  
      </MSH.5>  
      <MSH.6>  
         <HD.1>767543</HD.1>  
      </MSH.6>  
      <MSH.7>  
         <TS.1>199003141304-0500</TS.1>  
      </MSH.7>  
      <MSH.9>  
         <MSG.1>ACK</MSG.1>  
         <MSG.3>ACK</MSG.3>  
      </MSH.9>  
      <MSH.10>XX3657</MSH.10>  
      <MSH.11>  
         <PT.1>P</PT.1>  
      </MSH.11>  
      <MSH.12>  
         <VID.1>2.4</VID.1>  
      </MSH.12>  
   </MSH>  
   <MSA>  
      <MSA.1>AR</MSA.1>  
      <MSA.2>ZZ9380</MSA.2>  
   </MSA>  
   <ERR>  
      <ERR.1>  
         <ELD.1>PID</ELD.1>  
         <ELD.2>1</ELD.2>  
         <ELD.3>16</ELD.3>  
         <ELD.4>  
            <CE.1>103</CE.1>  
            <CE.2>Table value not found</CE.2>  
            <CE.3>HL70357</CE.3>  
         </ELD.4>  
      </ERR.1>  
   </ERR>  
</ACK>  
```  
  
 <span data-ttu-id="6e707-128">Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="6e707-128">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="6e707-129">Compatibilidad de delimitado por canalización y codificación de XML.</span><span class="sxs-lookup"><span data-stu-id="6e707-129">Support of pipe delimited and XML encoding.</span></span>  
  
-   <span data-ttu-id="6e707-130">Compatibilidad de traducción entre XML y la canalización había delimitada codificaciones.</span><span class="sxs-lookup"><span data-stu-id="6e707-130">Support of translation between XML and pipe delimited encodings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e707-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e707-131">See Also</span></span>  
 <span data-ttu-id="6e707-132">[Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6e707-132">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="6e707-133">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="6e707-133">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="6e707-134">Utilizar esquemas 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="6e707-134">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)