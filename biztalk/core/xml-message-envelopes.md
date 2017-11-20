---
title: Sobres de mensajes XML | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3adb33866a3e6fdaee387934d2edededaab08aac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xml-message-envelopes"></a><span data-ttu-id="f94f8-102">Sobres de mensajes XML</span><span class="sxs-lookup"><span data-stu-id="f94f8-102">XML Message Envelopes</span></span>
<span data-ttu-id="f94f8-103">Los sobres XML cumplen dos objetivos dentro de los mensajes de instancia XML enviados y recibidos por Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f94f8-103">XML envelopes serve two purposes within XML instance messages sent and received by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="f94f8-104">Los sobres XML pueden contener datos que complementen a los datos de los documentos XML.</span><span class="sxs-lookup"><span data-stu-id="f94f8-104">XML envelopes can contain data that supplements the data within the XML documents.</span></span> <span data-ttu-id="f94f8-105">Estos datos se pueden promocionar en el contexto del mensaje con el desensamblador XML para proporcionar un acceso más sencillo desde varios componentes de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f94f8-105">This data can be promoted into the message context by the XML disassembler to provide easier access from a variety of BizTalk Server components.</span></span> <span data-ttu-id="f94f8-106">Para los mensajes de instancia XML de salida, el ensamblador XML puede degradar valores del contexto del mensaje en un sobre para su inclusión en la transmisión del mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="f94f8-106">For outbound XML instance messages, the XML assembler can demote values from the message context into an envelope for inclusion in the instance message transmission.</span></span>  
  
-   <span data-ttu-id="f94f8-107">Los sobres XML se pueden usar para combinar varios documentos XML en un único mensaje de instancia XML válido.</span><span class="sxs-lookup"><span data-stu-id="f94f8-107">XML envelopes can be used to combine multiple XML documents into a single, valid XML instance message.</span></span> <span data-ttu-id="f94f8-108">Si no hay un sobre para incluir los distintos documentos dentro de una etiqueta raíz, un mensaje de instancia XML que contenga varios documentos no será calificado como XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="f94f8-108">Without an envelope to wrap multiple documents within a single root tag, an XML instance message containing multiple documents would not qualify as well-formed XML.</span></span>  
  
 <span data-ttu-id="f94f8-109">Un sobre XML típico (en negrita) contiene datos y una etiqueta para delimitar el documento o los documentos XML (fuente normal) que contiene.</span><span class="sxs-lookup"><span data-stu-id="f94f8-109">A typical XML envelope (shown in bold type) contains both data and a tag used to delimit the one or more XML documents (shown in regular font) that it contains.</span></span>  
  
```  
  
  <envelope fieldAttrib1="..." fieldAttrib2="..." ...>     <fieldElem1>...</fieldElem1>     <fieldElem2>...</fieldElem2>     ...     <body>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</body>    ...</envelope>  
```  
  
 <span data-ttu-id="f94f8-110">Aunque es menos común, pero no obstante válido, no es necesario que un sobre XML (en negrita) contenga datos o etiquetas para delimitar los documentos XML (fuente normal) que contiene.</span><span class="sxs-lookup"><span data-stu-id="f94f8-110">Less common, but still valid, an XML envelope (shown in bold type) need not contain any data or a tag for delimiting the XML documents (shown in regular type) that it contains.</span></span>  
  
```  
  
      <envelope>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</envelope>  
```  
  
 <span data-ttu-id="f94f8-111">En tales casos, el sobre XML consta únicamente de las etiquetas de sobre de inicio y de fin.</span><span class="sxs-lookup"><span data-stu-id="f94f8-111">In such cases, the XML envelope consists of nothing other than the starting and ending envelope tags.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94f8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f94f8-112">See Also</span></span>  
 <span data-ttu-id="f94f8-113">[Sobres de mensajes XML anidados](../core/nested-xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="f94f8-113">[Nested XML Message Envelopes](../core/nested-xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="f94f8-114">[Estructura de un mensaje XML](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="f94f8-114">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="f94f8-115">Cómo crear esquemas de sobres</span><span class="sxs-lookup"><span data-stu-id="f94f8-115">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)