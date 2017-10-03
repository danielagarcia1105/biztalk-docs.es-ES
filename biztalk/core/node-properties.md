---
title: Propiedades del nodo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d41f0f3b0fe0b302a763629b8777669b54f6cc86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="node-properties"></a>Propiedades de los nodos

## <a name="overview"></a>Información general
En el Editor de BizTalk, las propiedades de los nodos se examinan y establecen en la ventana Propiedades de Visual Studio. A medida que selecciona distintos tipos de nodos en la vista de árbol de esquema, se muestran conjuntos diferentes de propiedades en la ventana Propiedades. Como es estándar en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], estas propiedades se pueden mostrar en categorías o alfabéticamente sin ninguna indicación de sus categorías. Utilice los botones estándar situados cerca de la parte superior de la ventana Propiedades para alternar esta configuración.  
  
 Las propiedades de los nodos, especialmente si tienen establecidos valores distintos de los valores predeterminados, se representan por lo general en el lenguaje de definición de esquemas XML (XSD) como atributos y valores de atributo asociados con el elemento correspondiente. Por ejemplo, cuando se establecen propiedades para el **Min Occurs** y **Max Occurs** utiliza propiedades, que están disponibles para varios tipos de nodos, los valores que se establecen como los valores de la **minOccurs** y **maxOccurs** atributos, respectivamente, asociados con el elemento que representa el nodo para el que el **Min Occurs** y **máx. Se produce** se establecen propiedades.  

## <a name="property-types"></a>Tipos de propiedades
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] material de referencia contiene una sección de referencia de las propiedades de los distintos tipos de nodo, organizadas por categoría y por orden alfabético. A continuación resume las propiedades asociadas a cada tipo de nodo:  
  
-   Propiedades del nodo Esquema en el Asignador de BizTalk
  
-   Propiedades del nodo Registro
  
-   Propiedades del nodo Elemento de campo
  
-   Propiedades del nodo Atributo de campo
  
-   Propiedades del nodo Grupo de secuencias
  
-   Propiedades del nodo Grupo de elecciones 
  
-   Propiedades del nodo Todos los grupos
  
-   Propiedades del nodo Grupo de atributos
  
-   Propiedades del nodo Cualquier elemento
  
-   Propiedades del nodo Cualquier atributo
  
-   Propiedades del nodo equivalente
  
-   Propiedades del nodo secundario equivalente

Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 **Propiedades de nodo: Lista alfabética** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contiene todos los temas de referencia individual para cada propiedad de nodo, algunos de los cuales se aplican a distintos tipos de nodos. Los temas individuales de referencia están clasificados según si son propiedades básicas aplicables a todos los tipos de esquema o si son propiedades especializadas asociadas a una extensión del editor de esquemas, como la extensión de archivo sin formato. Dentro de estas categorías, aparecen ordenadas de forma alfabética.  
  
 Editor de BizTalk utiliza la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades para que pueda examinar y establecer las propiedades de los nodos del árbol de esquema. Esta sección describen algunas características del trabajo con las propiedades de la ventana Propiedades, incluidas algunas consideraciones especiales para el **nombre de nodo** propiedad y una explicación de las interdependencias entre las propiedades, y obtener información acerca de las longitudes máximas permitidas en determinadas propiedades o tipos de propiedades.  
  
 El resto de la sección proporciona información adicional acerca de propiedades de nodo especiales concretas, así como otra información que se aplica normalmente a las propiedades de nodo.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Propiedad Node Name](../core/node-name-property.md)  
  
-   [Interdependencias entre las propiedades](../core/property-interdependencies.md)  
  
-   [Propiedades adicionales del archivo sin formato](../core/additional-flat-file-properties.md)