---
title: Esquemas de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8009fba7-85f0-4795-9284-5b4e94b3fc72
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674a862b3966088bb1d75dd17ceacd47c30bdda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246052"
---
# <a name="flat-file-schemas"></a>Esquemas de archivo sin formato

## <a name="purpose-of-flat-file-schemas"></a>Propósito de esquemas de archivo sin formato
Los esquemas de archivo sin formato tienen dos finalidades. Definen todas las características iguales de registros y campos (incluida la estructura) como esquemas XML y proporcionan un mecanismo para definir todas las características de archivo sin formato que se necesitan para traducir un mensaje de instancia de archivo sin formato en un mensaje de instancia XML equivalente (o viceversa). La primera finalidad es más útil si se utiliza el esquema de archivo sin formato dentro del Asignador de BizTalk para definir una transformación de los mensajes de instancia de archivo sin formato que se ajustan al esquema en una estructura de destino diferente. La estructura de destino, definida mediante el esquema de destino en el Asignador de BizTalk, puede o no estar regida por un esquema de mensaje de archivo sin formato (puede ser un esquema XML).  
  
 La segunda finalidad, la de traducción entre el formato de archivo sin formato del documento y el formato XML equivalente, usa un amplio conjunto de información que se agrega al esquema del lenguaje de definición de esquemas XML (XSD) mediante la sintaxis de anotación. Desde la perspectiva de XSD, esta información es superflua en términos de utilidad para validar un mensaje de instancia XML con el esquema que rige su estructura. Sin embargo, la sintaxis de anotación XSD proporciona un mecanismo conveniente para almacenar información de estructura de archivo sin formato en el esquema XSD en una variedad de distintos ámbitos, desde información de esquema almacenada como anotaciones en el **esquema** elemento a la información que es específica de un registro o campo concreto, almacenada como anotaciones en la correspondiente **elemento** o **atributo** elemento.  
  
 Otra característica diferenciadora de los esquemas de archivo sin formato con respecto a los esquemas XML es el hecho de que los mensajes de instancia no se pueden comparar con los esquemas que los rigen según el contenido. En lugar de ello, es necesario especificar el conjunto estático de esquemas que usará el desensamblador de archivos sin formato en tiempo de ejecución.  
  
 Para ver las propiedades de nodo adicionales asociadas con las características de archivos planos, debe especificar el **extensión de archivo sin formato** mediante el uso de la **extensiones de Editor de esquemas** propiedad de la **Esquema** nodo. No aparecen de forma predeterminada.  
  
 Para obtener información detallada acerca de las propiedades de nodo que son específicas de los esquemas de archivo sin formato, vea la **propiedades de nodo adicionales para esquemas de archivo sin formato** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
 [Diferentes tipos de esquemas de BizTalk](../core/different-types-of-biztalk-schemas.md)