---
title: Se encontró un error de BTS MIME al intentar descodificar un mensaje AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 096696f4420150cdd53f8fe561460d243c1bb018
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005077"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a>Error de BTS MIME al intentar descodificar un mensaje AS2
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de BizTalk Server|  
|Componente|Motor AS2|  
|Nombre simbólico|-|  
|Texto del mensaje|Error de BTS MIME al intentar descodificar un mensaje AS2.  AS2-de: {0}, AS2-a: {1}, MessageId: {2}, Error: {3}|  
  
## <a name="explanation"></a>Explicación  
 Este error aparece al usar el componente MIME de BizTalk para gestionar parte del procesamiento de MIME.  
  
## <a name="user-action"></a>Acción del usuario  
 El mensaje de error completo proporciona la información sobre el problema detectado por el componente MIME. Consulte la información de error MIME de BTS para diagnosticar el problema (Esto es porque los componentes de AS2 usan los componentes de MIME de BizTalk para parte del procesamiento de MIME).