---
title: No se especifica el elemento de cuerpo de mensaje de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 206cbea171b3453fed7e7db7d5c67d658fcccc10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994549"
---
# <a name="biztalk-message-body-element-not-specified"></a>Elemento de cuerpo de mensaje de BizTalk no especificado.
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                     Elemento de cuerpo de mensaje de BizTalk no especificado.                     |
  
## <a name="explanation"></a>Explicación  
 Este error indica el uso de la opción de plantilla para el mensaje saliente de WCF. Sin embargo, la expresión de plantilla no contiene el elemento de cuerpo de mensaje de BizTalk.  
  
## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que la expresión de plantilla contiene el siguiente elemento: \< **bts-msg-body xmlns = "<http://www.microsoft.com/schemas/bts2007>" encoding = "[xml&#124;base64&#124;hexadecimal&#124;string]" /**\>.