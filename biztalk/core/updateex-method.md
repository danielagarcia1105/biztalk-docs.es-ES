---
title: "Método UpdateEx | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: UpdateEx method
ms.assetid: 2fa9c9cc-fd01-4765-8c31-facac188a19d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a6a64c6709eb9806612518c551372ba45d1a454
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="updateex-method"></a>Método UpdateEx
Usa para actualizar propiedades basadas en los parámetros de clave de entrada (clave1, clave2... claven). Al usar `UpdateEx`, no se pueden eliminar los elementos de una colección. Un método independiente facilita la eliminación. Para obtener más información, consulte [método DeleteOnly](../core/deleteonly-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
UpdateEx (key1, key2, ... keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Description|  
|---------------|-----------------|  
|`key`|Conjunto de parámetros que debe existir en la base de datos del servidor; de lo contrario se produce un error. Estas claves corresponden al conjunto de Obtener claves definido para la interfaz de componentes concreta.|  
|`correctionMode`|Una marca booleana. Si se establece en verdadero, permite las modificaciones a las interfaces de componentes con elementos con fecha de vigencia actualizando los valores de los campos o bien insertando nuevos elementos en una recopilación. Específicamente, permite la modificación de los elementos que tienen EFFDT anterior a la fecha de vigencia actual. Sin esta marca establecida en TRUE, cualquier modificación a estos elementos origina la devolución de un error desde el servidor PeopleSoft.<br /><br /> El argumento `correctionMode` solo se expone para las interfaces de componente que contengan elementos con fecha efectiva. En caso contrario, no se muestra como parte del argumento.<br /><br /> Debe evitar configurar `correctionMode` en TRUE en un entorno de producción. (También se recomienda esto desde PeopleSoft.) No deben modificarse los eventos que ya han tenido lugar según determine la anterior clave EFFDT. Esto permite la creación de una pista de auditoría. La marca `correctionMode` de `UpdateEx` permite la omisión de este mecanismo de seguridad. La práctica recomendada es que los eventos del pasado se desactiven configurando un campo en el elemento y agregando (y no eliminando) el elemento actualizado.|  
|`interactiveMode`|Marca usada para el tratamiento de errores.<br /><br /> Al obtener acceso a las propiedades de una interfaz de componentes, el adaptador de BizTalk para PeopleSoft Enterprise usa API proporcionadas por PeopleSoft que leen y escriben en los campos individuales de la interfaz de componente; no obstante, estos cambios no se propagan al servidor de PeopleSoft de uno en uno. En su lugar, psjoa.jar (con el que el adaptador de BizTalk para PeopleSoft Enterprise interactúa) empaqueta todos los cambios en un único paquete y los envía al servidor. Si alguna de las actualizaciones individuales produce un error, se devuelve un error genérico, que no ubica el error real. Con el modo interactivo establecido en TRUE, cada actualización de campo se envía al servidor individualmente. Esto tiene un impacto sustancial en el rendimiento, pero proporciona información del error específico si se genera un error en la actualización (por ejemplo, si se usa un valor no válido para configurar un campo).<br /><br /> `interactiveMode` proporciona el máximo rendimiento y proporciona informes de errores en el nivel de actualización de campos. Para usar correctamente esta característica, se recomienda que realice llamadas normales con `interactiveMode` definido en FALSE. No debe haber ningún impacto en el rendimiento. Si se devuelve un error, se puede recuperar la misma llamada con la marca `interactiveMode` establecida en TRUE. Cuando se produce un error en la llamada, el servidor devuelve un mensaje de error más preciso.|  
  
### <a name="remarks"></a>Comentarios  
 Cuando se llama a esta función, las propiedades del registro correspondientes a las claves se reemplazan por las propiedades del parámetro de entrada. Todas las recopilaciones con los registros originales se eliminan o reemplazan por las del parámetro de entrada. No es necesario que coincidan los tamaños de estas recopilaciones porque el procedimiento en `UpdateEx` es eliminar todos los elementos de la colección existente de y, a continuación, insertar los dados.  
  
 Si las propiedades de la interfaz de componentes contiene elementos con fecha de vigencia, el parámetro de propiedades debe contener todos los elementos con fecha de vigencia futura, pues se sustituye la lista original. Esto proporciona el mecanismo necesario para agregar y eliminar elementos con fecha de vigencia futura; no obstante, si las propiedades también contienen elementos con fecha de vigencia pasada, se devolverá un error, pues los elementos con fecha de vigencia pasada no se pueden modificar. Si también se incluye el elemento con fecha de vigencia actual, se omite. Esto permite al cliente para llamar a `Get()` con el `getHistoryItems` parámetro establecido en False y modificar los elementos con fecha de vigencia futura o agregar nuevos elementos de fecha de vigencia futuros y pasar la estructura como parámetro para el `UpdateEx()` función.  
  
 Si la interfaz de componentes no tiene clave, como sucede si solo puede existir una instancia, el método `UpdateEx()` presenta la forma:  
  
```  
UpdateEx(correctionMode, interactiveMode, properties)  
```  
  
> [!NOTE]
>  Se proporciona el método `UpdateEx()` del adaptador de BizTalk para PeopleSoft Enterprise si las funciones `Get` y `Save` de PeopleSoft están habilitadas en la interfaz de componentes  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)