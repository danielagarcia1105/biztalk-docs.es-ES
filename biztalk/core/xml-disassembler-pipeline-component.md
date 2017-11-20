---
title: "Componente de canalización de desensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3346cdbfeed14e933039d7866e174c833f17212e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-pipeline-component"></a><span data-ttu-id="1325b-102">Componente de canalización del desensamblador de XML</span><span class="sxs-lookup"><span data-stu-id="1325b-102">XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="1325b-103">El componente de canalización de desensamblador XML combina el análisis y desensamblado en un componente.</span><span class="sxs-lookup"><span data-stu-id="1325b-103">The XML Disassembler pipeline component combines XML parsing and disassembling into one component.</span></span> <span data-ttu-id="1325b-104">Sus funciones principales son:</span><span class="sxs-lookup"><span data-stu-id="1325b-104">Its primary functions are:</span></span>  
  
-   <span data-ttu-id="1325b-105">Quitar sobres.</span><span class="sxs-lookup"><span data-stu-id="1325b-105">Removing envelopes.</span></span>  
  
-   <span data-ttu-id="1325b-106">Desensamblar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="1325b-106">Disassembling the interchange.</span></span>  
  
-   <span data-ttu-id="1325b-107">Promover las propiedades de contenido desde los niveles de documentos individuales y de intercambio hasta el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1325b-107">Promoting the content properties from interchange and individual document levels on to the message context.</span></span>  
  
 <span data-ttu-id="1325b-108">Las siguientes acciones tienen lugar en el componente de desensamblador XML después de recibir un sobre:</span><span class="sxs-lookup"><span data-stu-id="1325b-108">The following actions occur in the XML Disassembler component after receiving an envelope:</span></span>  
  
1.  <span data-ttu-id="1325b-109">El desensamblador analiza el sobre utilizando los esquemas del sobre asociados estáticamente con el componente en tiempo de diseño o dinámicamente al determinar los esquemas de sobres a partir del tipo de mensaje en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1325b-109">The disassembler parses the envelope by using the envelope schemas statically associated with the component at design time or dynamically by determining envelope schemas from the message type at run time.</span></span> <span data-ttu-id="1325b-110">El esquema se utiliza para comprobar la estructura del sobre durante su análisis.</span><span class="sxs-lookup"><span data-stu-id="1325b-110">The schema is used to verify the structure of the envelope during envelope parsing.</span></span> <span data-ttu-id="1325b-111">Si no se define la estructura del sobre, se encuentra de forma recursiva gracias a la utilización del espacio de nombres y nombre base del nodo raíz para buscar los esquemas.</span><span class="sxs-lookup"><span data-stu-id="1325b-111">If envelope structure is not defined, it is found recursively by using the root node's namespace and base name to look up the schemas.</span></span>  
  
2.  <span data-ttu-id="1325b-112">El componente del desensamblador analiza todos los documentos que hay dentro del sobre.</span><span class="sxs-lookup"><span data-stu-id="1325b-112">The disassembler component parses each document within the envelope.</span></span> <span data-ttu-id="1325b-113">Para cada documento, se crea un objeto de mensaje de BizTalk con su propio contexto donde se copian todas las propiedades promovidas del sobre y del documento en sí.</span><span class="sxs-lookup"><span data-stu-id="1325b-113">For each document, the BizTalk message object is created with its own context where all the properties promoted from the envelope and from the document itself get copied.</span></span> <span data-ttu-id="1325b-114">El componente saca las propiedades del contenido del sobre y las instancias de mensaje mediante los XPaths predefinidos y codificados como anotaciones en los esquemas XSD asociados con el sobre y el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1325b-114">The component pulls the content properties from the envelope and message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the envelope and message.</span></span> <span data-ttu-id="1325b-115">Los esquemas de sobres así como los de los documentos individuales están asociados con el componente de desensamblador en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="1325b-115">The envelope schemas as well as the individual document schemas are associated with the disassembler component in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="1325b-116">El desensamblador XML sólo procesa datos en la parte del cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1325b-116">The XML Disassembler only processes data in the body part of the message.</span></span> <span data-ttu-id="1325b-117">Por lo tanto, sólo se pueden promover las propiedades de la parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="1325b-117">Thus, only properties from body part can be promoted.</span></span> <span data-ttu-id="1325b-118">Los valores datetime de los campos asociados con las propiedades que se pueden promover se convierten a UTC cuando se produce una promoción de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1325b-118">Datetime values from the fields associated with the promotable properties get converted to UTC when property promotion occurs.</span></span> <span data-ttu-id="1325b-119">Las partes que no sean del cuerpo se copian en el mensaje de salida sin ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="1325b-119">Non-body parts are copied to the output message unchanged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1325b-120">El componente de canalización de desensamblador XML fuerza la conversión actual de todas las propiedades datetime a UTC antes de alcanzar el almacén de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1325b-120">The XML Disassembler pipeline component currently forces conversion of all datetime properties to UTC before they reach the message store.</span></span> <span data-ttu-id="1325b-121">BizTalk Server utiliza un tipo datetime de SQL internamente, el cual no tiene información sobre la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="1325b-121">BizTalk Server uses an SQL datetime type internally, which does not have information about the time zone.</span></span> <span data-ttu-id="1325b-122">Si genera una propiedad datetime en una orquestación y, a continuación, intenta utilizarla para correlación con mensajes posteriores, es posible que no funcione correctamente, porque el componente de canalización del desensamblador XML la convertirá en respuesta a UTC y Microsoft SQL Server no tendrá posibilidad de identificar los campos de tiempo original y de respuesta porque son idénticos.</span><span class="sxs-lookup"><span data-stu-id="1325b-122">If you generate a datetime property in an orchestration, and then try to use it for correlation with subsequent messages, it may not work correctly, because the XML Disassembler pipeline component will convert it on response into UTC, and Microsoft SQL Server will have no way to identify the original and response time fields as identical.</span></span> <span data-ttu-id="1325b-123">De forma similar, puede encontrar discrepancias al visualizar los datos de seguimiento de instancias de servicio y eventos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1325b-123">Similarly, you may encounter discrepancies when viewing message event and service instance tracking data.</span></span>  
  
 <span data-ttu-id="1325b-124">Para obtener información acerca de cómo configurar el componente de canalización de desensamblador XML, vea [cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="1325b-124">For information about configuring the XML Disassembler pipeline component, see [How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1325b-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1325b-125">In This Section</span></span>  
  
-   [<span data-ttu-id="1325b-126">Elementos Set de información XML en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1325b-126">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="1325b-127">Mensajes desconocidos en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1325b-127">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="1325b-128">Validación de documentos en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1325b-128">Document Validation in the XML Disassembler Pipeline Component</span></span>](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="1325b-129">Obligatoriedad de estructura del documento en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1325b-129">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="1325b-130">Codificación de caracteres en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1325b-130">Character Encoding in XML Disassembler Pipeline Component</span></span>](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="1325b-131">Tutorial: Utilizar sobres XML (básicos)</span><span class="sxs-lookup"><span data-stu-id="1325b-131">Walkthrough: Using XML Envelopes (Basic)</span></span>](../core/walkthrough-using-xml-envelopes-basic.md)