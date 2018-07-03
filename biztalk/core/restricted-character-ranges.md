---
title: Restringe los intervalos de caracteres | Microsoft Docs
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
ms.openlocfilehash: eb09e0447938c1b394a786293f487de70268cb2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006381"
---
# <a name="restricted-character-ranges"></a>Intervalos de caracteres restringidos

## <a name="overview"></a>Información general
Al crear un esquema para los mensajes de archivo sin formato, puede dirigir [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para bloquear un determinado carácter o un intervalo de caracteres que se incluyan en los mensajes salientes. Para ello, en el Editor de BizTalk, abra un esquema que vaya a usar como esquema de destino. Seleccione el **esquema** nodo y el uso del **caracteres restringidos** propiedad para abrir el **caracteres restringidos** cuadro de diálogo. Escriba el carácter de intervalos que desea que se incluyan en los mensajes enviados por BizTalk Server y, a continuación, haga clic en **Aceptar**. Cada vez que BizTalk Server intenta procesar un carácter especificado en el **caracteres restringidos** cuadro de diálogo de un esquema de destino de procesamiento se detiene y un mensaje de error se genera.  

> [!NOTE]
>  En BizTalk Server, la restricción de intervalos de caracteres es una función de Extensión de archivo sin formato y, como tal, no es aplicable a los mensajes XML. Las extensiones que se pueden ofrecer en el futuro para los distintos tipos de mensajes pueden ser distintas en cuanto al modo de implementar la restricción de los intervalos de caracteres para los formatos de mensajes compatibles.  

## <a name="see-also"></a>Vea también  
- [Consideraciones al crear esquemas de mensajes de archivo sin formato](../core/considerations-when-creating-flat-file-message-schemas.md)   
- **Caracteres restringidos (propiedad de nodo de esquemas de archivo sin formato** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
