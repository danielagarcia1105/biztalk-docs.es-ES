---
title: El descodificador AS2 no pudo procesar el MDN indicó el procesamiento del mensaje de error de AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20454f1c551b6b4828c42e09f0442b83275256ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240124"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a>Error de procesamiento de descodificador AS2. MDN indicó un error de procesamiento del mensaje AS2
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|AS2DecoderMdnProcessingFailureReturned|  
|Texto del mensaje|Error de procesamiento de descodificador AS2. MDN indicó un error de procesamiento del mensaje AS2.  Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" OriginalMessageID: "\ {3\}"|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la respuesta de MDN indica que el receptor del mensaje AS2 original no pudo procesar el mensaje AS2 original.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, póngase en contacto con el receptor del mensaje AS2, determine por qué se ha producido un error en el destinatario, corrija el mensaje AS2 original y vuelva a enviarlo.