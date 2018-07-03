---
title: Sobres de mensajes XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f4b60dfbc128baead6b0a1ad38d319ba7b6e8fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972413"
---
# <a name="xml-message-envelopes"></a>Sobres de mensajes XML
Los sobres XML cumplen dos objetivos dentro de los mensajes de instancia XML enviados y recibidos por Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- Los sobres XML pueden contener datos que complementen a los datos de los documentos XML. Estos datos se pueden promocionar en el contexto del mensaje con el desensamblador XML para proporcionar un acceso más sencillo desde varios componentes de BizTalk Server. Para los mensajes de instancia XML de salida, el ensamblador XML puede degradar valores del contexto del mensaje en un sobre para su inclusión en la transmisión del mensaje de instancia.  
  
- Los sobres XML se pueden usar para combinar varios documentos XML en un único mensaje de instancia XML válido. Si no hay un sobre para incluir los distintos documentos dentro de una etiqueta raíz, un mensaje de instancia XML que contenga varios documentos no será calificado como XML con formato correcto.  
  
  Un sobre XML típico (en negrita) contiene datos y una etiqueta para delimitar el documento o los documentos XML (fuente normal) que contiene.  
  
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
  
 Aunque es menos común, pero no obstante válido, no es necesario que un sobre XML (en negrita) contenga datos o etiquetas para delimitar los documentos XML (fuente normal) que contiene.  
  
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
  
 En tales casos, el sobre XML consta únicamente de las etiquetas de sobre de inicio y de fin.  
  
## <a name="see-also"></a>Vea también  
 [Sobres de mensajes XML anidados](../core/nested-xml-message-envelopes.md)   
 [Estructura de un mensaje XML](../core/structure-of-an-xml-message.md)   
 [Cómo crear esquemas para sobres](../core/how-to-create-schemas-for-envelopes.md)