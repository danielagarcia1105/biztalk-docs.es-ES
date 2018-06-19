---
title: Restringido intervalos de caracteres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74f1399aaa828d5c23c2600ebabeb7063a982447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268292"
---
# <a name="restricted-character-ranges"></a>Intervalos de caracteres restringidos

## <a name="overview"></a>Información general
Al crear un esquema para los mensajes de archivo sin formato, puede dirigir [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para bloquear un determinado carácter o un intervalo de caracteres desde la que se incluye en los mensajes salientes. Para ello, en el Editor de BizTalk, abra un esquema que vaya a usar como esquema de destino. Seleccione el **esquema** nodo y el uso del **caracteres restringidos** propiedad para abrir el **caracteres restringidos** cuadro de diálogo. Escriba el carácter de intervalos que desea que se incluyan en los mensajes enviados por BizTalk Server y, a continuación, haga clic en **Aceptar**. Cada vez que BizTalk Server intenta procesar un carácter especificado en el **caracteres restringidos** cuadro de diálogo de un esquema de destino de procesamiento se detiene y un mensaje de error se genera.  
  
> [!NOTE]
>  En BizTalk Server, la restricción de intervalos de caracteres es una función de Extensión de archivo sin formato y, como tal, no es aplicable a los mensajes XML. Las extensiones que se pueden ofrecer en el futuro para los distintos tipos de mensajes pueden ser distintas en cuanto al modo de implementar la restricción de los intervalos de caracteres para los formatos de mensajes compatibles.  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones al crear sin formato de archivo esquemas de mensaje](../core/considerations-when-creating-flat-file-message-schemas.md)   
-  **Caracteres restringidos (propiedad de nodo de esquemas de archivo sin formato**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]