---
title: Interdependencias entre las propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed5b75e-db1c-43d4-a287-fc4cd1c529f5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15e1a02d82d294c63a33c0682e77585a7934b8ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268460"
---
# <a name="property-interdependencies"></a>Interdependencias entre las propiedades

## <a name="overview"></a>Información general
Cuando use el Editor de BizTalk y específicamente el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades, para cambiar los valores de propiedades, observará que hay una amplia interdependencias entre las propiedades. A veces, la configuración concreta de una propiedad provocará que otras propiedades se borren automáticamente, se habiliten o deshabiliten, o incluso que aparezcan o no se muestren en absoluto en la ventana Propiedades. Estas interdependencias son demasiado numerosas para tratarlas una a una. 

Sin embargo, en la siguiente lista se proporcionan algunos ejemplos comunes con los que se podrá hacer una idea de cómo funcionan:  
  
-   Al establecer las propiedades de un **elemento de campo** nodo o **atributo de campo** nodo para el que un tipo de datos se deriva de un tipo simple mediante el mecanismo de restricción, toda la nueva categoría de propiedades está disponible: **restricción**. Además, las propiedades de esta nueva categoría se habilitan o deshabilitan según si el tipo de datos base es de tipo cadena o numérico. Para obtener más información acerca de esta forma de derivación de tipo simple, vea [derivación Simple de tipo mediante el mecanismo de restricción](../core/simple-type-derivation-using-the-restriction-mechanism.md).  
  
-   Al establecer las propiedades de un **elemento de campo** nodo o **atributo de campo** nodo para el que un tipo de datos se deriva de un tipo simple mediante el uso de la lista o un mecanismo de unión, el **Base Tipo de datos** propiedad se cambia a la **tipo de elemento** propiedad o el **tipos de miembro** propiedad, respectivamente. En el último caso, la lista desplegable correspondiente se modifica para incluir casillas de verificación, lo que permite seleccionar varios tipos. Para obtener más información acerca de estas formas de derivación de tipo simple, vea [derivación Simple de tipo mediante el mecanismo de lista](../core/simple-type-derivation-using-the-list-mechanism.md) y [derivación Simple de tipo mediante el mecanismo de unión](../core/simple-type-derivation-using-the-union-mechanism.md).  
  
-   Para exponer las propiedades asociadas a esquemas de archivo sin formato, debe establecer el **extensiones de Editor de esquemas** propiedad de la **esquema** nodo para incluir la **extensión de archivo sin formato** . Las propiedades personalizadas asociadas con otras extensiones de editor, como la extensión EDI, se exponen de la misma manera: Si elige la extensión correspondiente con el **extensiones de Editor de esquemas** propiedad.  
  
 Esta lista incluye ejemplos cuyo fin es ilustrar los tipos de interdependencias entre propiedades que verá al trabajar en la ventana Propiedades, pero no pretende ser una lista exhaustiva.  
  
## <a name="see-also"></a>Vea también  
-  [Propiedades de nodo](../core/node-properties.md)   
-  Las siguientes propiedades[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
    -  Lista alfabética de propiedades de nodo
    -  Propiedades de nodo de todos los esquemas 
    -  Extensiones de editor de esquemas