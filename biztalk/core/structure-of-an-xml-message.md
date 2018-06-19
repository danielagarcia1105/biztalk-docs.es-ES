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
# <a name="structure-of-an-xml-message"></a>Estructura de un mensaje XML
En el contexto de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un mensaje de instancia XML es una jerarquía de etiquetas XML que constituyen en cero o varios sobres XML y uno o más documentos XML válida. Por ejemplo, el siguiente mensaje de instancia XML consta de un sobre XML (en formato de fuente normal) que contiene un documento XML (en negrita).  
  
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
  
 Los sobres XML y los documentos XML que los sobres contienen se pueden combinar en mensajes de instancia XML válidos de varias formas. En el resto de la sección se describen las distintas combinaciones posibles.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Sobres de mensajes XML](../core/xml-message-envelopes.md)  
  
-   [Sobres de mensajes XML anidados](../core/nested-xml-message-envelopes.md)