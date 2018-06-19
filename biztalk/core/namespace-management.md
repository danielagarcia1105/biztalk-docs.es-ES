---
title: Administración de Namespace | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4638c47c-3cdd-43af-aa00-da98e7293503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 897ab6de3e7fddb362cb59356e6a4808d35f8f47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263740"
---
# <a name="namespace-management"></a>Administrador de espacio de nombres
El Editor de BizTalk proporciona compatibilidad para los espacios de nombres. Un espacio de nombres XML es una colección de nombres que se puede usar como nombres de elemento o atributo en un mensaje XML. El espacio de nombres califica los nombres de elemento y atributo para evitar conflictos entre los mismos nombres de elemento y atributo que se pueden definir en cualquier lugar dentro del mismo esquema.  
  
 Los espacios de nombres se identifican con un Identificador de recursos universal (URI), bien como Localizador uniforme de recursos (URL) o como Nombre de recursos uniforme (URN). También reciben un alias de prefijo normalmente corto que lleva antepuesto dos puntos (:) al nombre del elemento o del atributo) Por ejemplo, es habitual ver la siguiente declaración de espacio de nombres dentro de la **esquema** elemento en la representación XSD del esquema.  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 El prefijo es xs, que se puede ver en la representación XSD, calificar elementos tales como el **elemento** element (xs:) y el **atributo** elemento (xs: Attribute).  
  
 Cuando se crea un nuevo esquema, independientemente de si es un esquema de mensaje o un esquema de propiedad, es importante establecer el **Target Namespace** propiedad de la **esquema** nodo correctamente. Debe establecer el espacio de nombres de destino antes de que otro esquema utilice el esquema con los mecanismos import, include y redefine, así como antes de que se defina cualquier promoción de propiedades.  
  
> [!WARNING]
>  Si va a utilizar dos espacios de nombres que varíen únicamente en las mayúsculas y minúsculas, la base de datos de BizTalk Server se debe instalar con una intercalación que distinga entre mayúsculas y minúsculas. Los ejemplos de intercalaciones que distinguen mayúsculas de minúsculas incluyen intercalaciones binarias y no binarias con la distinción de mayúsculas de minúsculas habilitada. De no hacerlo, se producirán errores en la resolución de esquemas, ya que XML distingue mayúsculas de minúsculas.  
  
 Los dos siguientes espacios de nombres se agregan automáticamente como declaraciones de espacios de nombres al elemento schema de la representación del esquema en el lenguaje de definición de esquemas XML (XSD):  
  
-   xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
  
-   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
 Mientras use otros esquemas dentro del esquema que esté creando, se declararán otros espacios de nombres. Puede examinar estos espacios de nombres, así como los espacios de nombres incluidos automáticamente, en el **importaciones** cuadro de diálogo que se puede tener acceso mediante el **importaciones** propiedad de la **esquema** nodo. Para obtener más información acerca del uso de otros tipos de datos declarados en otros esquemas dentro del esquema que está creando, consulte [esquemas que usan otros esquemas](../core/schemas-that-use-other-schemas.md) y [crear esquemas que usan otros esquemas](../core/how-to-create-schemas-that-use-other-schemas.md).  
  
 Espacios de nombres asociados con esquemas de propiedades se pueden examinar en el **promocionar propiedades** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones al crear esquemas](../core/considerations-when-creating-schemas.md)