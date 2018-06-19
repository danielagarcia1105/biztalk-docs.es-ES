---
title: Estructura de un mensaje XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bba81-2f2b-41f3-b8b2-c2fb9c15ea5a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f35e48e90ffb089342c268b7b6a45069e2f9869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278484"
---
# <a name="structure-of-an-xml-message"></a><span data-ttu-id="a2387-102">Estructura de un mensaje XML</span><span class="sxs-lookup"><span data-stu-id="a2387-102">Structure of an XML Message</span></span>
<span data-ttu-id="a2387-103">En el contexto de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un mensaje de instancia XML es una jerarquía de etiquetas XML que constituyen en cero o varios sobres XML y uno o más documentos XML válida.</span><span class="sxs-lookup"><span data-stu-id="a2387-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], an XML instance message is a valid hierarchy of XML tags that together constitute zero or more XML envelopes and one or more XML documents.</span></span> <span data-ttu-id="a2387-104">Por ejemplo, el siguiente mensaje de instancia XML consta de un sobre XML (en formato de fuente normal) que contiene un documento XML (en negrita).</span><span class="sxs-lookup"><span data-stu-id="a2387-104">For example, the following XML instance message consists of a single XML envelope (in regular font) that contains a single XML document (shown in bold type).</span></span>  
  
```  
<ns0:envelope xmlns:ns0="http://myEnvelopeNamespaceURI.org">  
    <header>  
        <firstName>John</firstName>  
        <lastName>Scott</lastName>  
    </header>  
    <body>  
        <ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">            <message>Hello</message>        </ns1:document>  
    </body>  
</ns0:envelope>  
```  
  
 <span data-ttu-id="a2387-105">Los sobres XML y los documentos XML que los sobres contienen se pueden combinar en mensajes de instancia XML válidos de varias formas.</span><span class="sxs-lookup"><span data-stu-id="a2387-105">XML envelopes and the XML documents that they contain can be combined into valid XML instance messages in several different ways.</span></span> <span data-ttu-id="a2387-106">En el resto de la sección se describen las distintas combinaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="a2387-106">The remainder of this section describes these different combinations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2387-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a2387-107">In This Section</span></span>  
  
-   [<span data-ttu-id="a2387-108">Sobres de mensajes XML</span><span class="sxs-lookup"><span data-stu-id="a2387-108">XML Message Envelopes</span></span>](../core/xml-message-envelopes.md)  
  
-   [<span data-ttu-id="a2387-109">Sobres de mensajes XML anidados</span><span class="sxs-lookup"><span data-stu-id="a2387-109">Nested XML Message Envelopes</span></span>](../core/nested-xml-message-envelopes.md)