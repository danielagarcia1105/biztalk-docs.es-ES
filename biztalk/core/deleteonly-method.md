---
title: "Método DeleteOnly | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3982c67b4c2eb572a57a4ad602b1d302f9b53ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deleteonly-method"></a>Método DeleteOnly
Permite eliminar elementos de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Description|  
|---------------|-----------------|  
|`key`|Es un conjunto de parámetros que se debe proporcionar. Este conjunto de claves debe existir en la base de datos del servidor o se produce un error. Estas claves corresponden al conjunto de Obtener claves definido para la interfaz de componentes concreta.|  
|`correctionMode`|Una marca booleana. Cuando se establece en true, permite la eliminación de elementos con fecha de vigencia pasada, de una colección. Específicamente, permite la eliminación de elementos que tienen un valor de EFFDT anterior a la fecha de vigencia actual. Sin esta marca establecida en TRUE, cualquier modificación a estos elementos origina la devolución de un error desde el servidor PeopleSoft. **Nota:** el `correctionMode` argumento solo se expone para las interfaces de componente que contienen elementos con fecha de vigencia. De lo contrario, no aparece como parte del argumento.|  
|`interactiveMode`|Se usa para el control de errores.<br /><br /> Cuando se obtiene acceso a las propiedades de una interfaz de componentes, BizTalk Adapter para PeopleSoft Enterprise usa las API proporcionadas por PeopleSoft, que leen y escriben campos individuales de la interfaz de componentes; sin embargo, estos cambios no se propagan al servidor PeopleSoft uno a uno. En su lugar, psjoa.jar (con la que el adaptador de BizTalk para PeopleSoft Enterprise interactúa) empaqueta todos los cambios y envía los cambios al servidor en un solo paquete. Si alguna de las actualizaciones individuales produce un error, se devuelve un error genérico, que no ubica el error real. Con el modo interactivo establecido en TRUE, cada actualización de campo se envía al servidor individualmente. Esto tiene un impacto sustancial en el rendimiento, pero proporciona información del error específico si se genera un error en la actualización (por ejemplo, si se usa un valor no válido para configurar un campo).<br /><br /> El parámetro `interactiveMode` proporciona el rendimiento máximo y el informe de errores en el nivel de actualizaciones de campo. Para usar correctamente esta característica, se recomienda que realice llamadas normales con `interactiveMode` definido en FALSE. No debe haber ningún impacto en el rendimiento. Si se devuelve un error, se puede recuperar la misma llamada con la marca de interactiveMode establecida en TRUE. Cuando se produce un error en la llamada, el servidor devuelve un mensaje de error más preciso.|  
|`properties`|Contiene un subconjunto de la estructura que existe en el servidor. Todos los elementos que son hojas se eliminan.|  
  
## <a name="remarks"></a>Comentarios  
 Las propiedades tienen el mismo tipo de datos que los métodos `CreateEx` o `UpdateEx` de esta interfaz de componentes; sin embargo, únicamente los valores de clave son importantes. Se omiten los valores que no son claves. Los valores de clave deben coincidir con los del servidor, de lo contrario se produce una excepción.  
  
 A continuación, se muestra el uso de los valores de clave. Si una colección contiene los elementos:  
  
-   item0  
  
-   item1  
  
-   Item2  
  
-   Item3  
  
 Puede eliminar item1 e item3 proporcionando las claves de item1 e item3 en las propiedades:  
  
-   item1  
  
-   Item3  
  
 Después de la llamada, el servidor tiene los elementos restantes de la colección:  
  
-   item0  
  
-   Item2  
  
 El segundo ejemplo muestra los elementos que contienen otras colecciones:  
  
-   item0  
  
    -   item0a  
  
-   item1  
  
    -   item1a  
  
    -   item1b  
  
    -   item1c  
  
-   Item2  
  
    -   item2a  
  
    -   item2b  
  
 Puede eliminar item1b y todos los item2 proporcionando las claves a item1b e item2:  
  
-   item1  
  
    -   item1b  
  
-   Item2  
  
 Si suministra una subcolección vacía para item2, lo convierte en hoja y se elimina toda la subramificación. Después de la llamada, el servidor tiene los elementos restantes:  
  
-   item0  
  
    -   item0a  
  
-   item1  
  
    -   item1a  
  
    -   item1c  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)