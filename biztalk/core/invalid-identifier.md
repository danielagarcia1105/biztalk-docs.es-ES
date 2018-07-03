---
title: Identificador no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f87e1e42-457f-4d04-a1d2-6b796f3fa7b7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b349991d0e0d6949754c804fcd1ebf16ea7ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012357"
---
# <a name="invalid-identifier"></a>Identificador no válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| Versión del producto |                                                        [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                         |
|    Identificador del evento     |                                                                                     0                                                                                     |
|  Origen del evento   |                                                                                     0                                                                                     |
|    Componente    |                                                                                     0                                                                                     |
|  Nombre simbólico  |                                                                                     0                                                                                     |
|  Texto del mensaje   | "{0}" no es un identificador válido. Restaurando nombre original. (Un identificador válido se compone de una letra seguida de cero o más letras o dígitos, y no puede contener espacios.) |
  
## <a name="explanation"></a>Explicación  
 Este error indica que los métodos web definidos al publicar un esquema no son un identificador .net válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Cambie el nombre de los métodos web por un identificador .net válido. Un identificador válido se compone de una letra seguida de cero o más letras o dígitos, y no puede contener espacios.