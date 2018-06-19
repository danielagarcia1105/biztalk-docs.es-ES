---
title: Contar posiciones en Bytes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cdb7bbf1f0d6af04f0cc28ed1bdb7477b259de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264036"
---
# <a name="position-counting-in-bytes"></a>Contar posiciones en Bytes

## <a name="overview"></a>Información general

Puede usar el **contar posiciones en Bytes** propiedad de la **esquema** nodo: 

* Especificar cómo los valores especifique para la **longitud posicional** y **desplazamiento posicional** se interpretan las propiedades de los campos de los registros posicionales
* Especificar cómo los valores especifique para la **desplazamiento de etiquetas** se interpreta la propiedad de los propios registros posicionales

De forma predeterminada, estos valores se interpretan como un número de caracteres. Pero cuando el **contar posiciones en Bytes** propiedad está establecida en **True**, estos valores se interpretan como un número de bytes.  
  
 Establecer el **contar posiciones en Bytes** propiedad **True** se podría es necesario cuando se trabaja con juegos de caracteres multibyte establecer datos (MNCS o DBCS), o cuando los mensajes de archivo sin formato se originan en SAP, grandes sistemas, o otros sistemas que puedan contar posiciones en bytes.  
  
 El proceso de contar las longitudes de los campos en bytes puede ser complejo si el número de bytes utilizados para codificar los caracteres es variable y puede originar algunos problemas con respecto a la determinación de los límites de campo. Cuando el desensamblador de archivos sin formato analiza un archivo sin formato en estas situaciones, intenta tomar las decisiones de análisis adecuadas según el conocimiento que tiene de la codificación de caracteres en uso.  
  
 Un ejemplo de problema de este tipo de decisión de análisis está relacionado con el tratamiento de los bytes iniciales en las codificaciones de caracteres MBCS. Los bytes iniciales son valores de byte muy conocidos que se utilizan para iniciar las codificaciones de caracteres multibyte y nunca deben aparecer de forma aislada. Al especificar la longitud de los campos mediante bytes en lugar de caracteres, pueden surgir situaciones en las que el último byte de un campo se considere un byte inicial, que no puede constituir un carácter por sí mismo. En tales casos, el desensamblador de archivos sin formato tratará el carácter que aparece justo antes del byte inicial como el último carácter del campo anterior y empezará a analizar el siguiente campo a partir del byte inicial.  

Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
## <a name="see-also"></a>Vea también  
 [Consideraciones del registro posicional](../core/positional-record-considerations.md)   
