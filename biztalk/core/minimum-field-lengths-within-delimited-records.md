---
title: Longitudes de los campos dentro de los registros delimitados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 992ffbc6a2e0568bc000413bf90b3c92012d4d59
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983317"
---
# <a name="minimum-field-lengths-within-delimited-records"></a>Longitudes de los campos dentro de los registros delimitados
Por definición, los campos de los registros posicionales están definidos para tener longitudes exactas específicas. Los campos de los registros delimitados también pueden estar definidos para tener una longitud mínima. Esta característica se define por la **[longitud mínima con carácter controlador** propiedad de **elemento de campo** y **atributo de campo** nodos.  

 Cuando se proporciona un valor distinto de cero para el **longitud mínima con carácter controlador** propiedad, el ensamblador de archivo sin formato determinará si el número de caracteres de datos asociado con el campo es menor que la configuración de la **Longitud mínima con carácter controlador** propiedad, se usará el carácter controlador relevante para compensar la diferencia.  

 Los caracteres controladores se agregarán antes o después de los caracteres de datos según la configuración de la **justificación** propiedad para el campo. Cuando el **justificación** propiedad está establecida en **izquierda**, se agregarán los caracteres controladores necesarios para cubrir la longitud mínima después de los caracteres de datos. Cuando el **justificación** propiedad está establecida en **derecha**, se agregarán los caracteres controladores necesarios para cubrir la longitud mínima antes de los caracteres de datos.  

 Cuando se proporciona un valor distinto de cero para el **longitud mínima con carácter controlador** propiedad, el Desensamblador de archivos sin formato examinará el principio o al final (según la configuración de la **justificación** propiedad) de el valor del campo para la presencia del carácter controlador relevante y, si está presente, los caracteres controladores se descartarán y no aparecen en el mensaje XML equivalente que se está construyendo.  

## <a name="see-also"></a>Vea también  
- [Consideraciones sobre campos](../core/field-considerations.md)   
- **Justificación (propiedad de nodo de esquemas de archivo sin formato)** y **longitud mínima con carácter controlador (propiedad de nodo de esquemas de archivo sin formato)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
