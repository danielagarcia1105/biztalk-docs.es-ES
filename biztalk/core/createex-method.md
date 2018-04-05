---
title: Método CreateEx | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateEx method
ms.assetid: b62bbe25-b24d-42a7-a44c-c83521a6f0a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b163bfbe7811c37208297aa0a61bfe91cabacde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="createex-method"></a>Método CreateEx
Crea un nuevo registro con un conjunto de claves únicas y propiedades especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Description|  
|---------------|-----------------|  
|`Key in/out parameter`|Parámetros de clave individual (clave1, clave2, ... claven), que se deben suministrar.<br /><br /> Este conjunto de claves no debe existir en la base de datos del servidor, es decir, deben de ser únicas.<br /><br /> Estas claves corresponden al conjunto de claves CreateEx definido para la interfaz de componentes concreta.|  
|`interactiveMode`|Control de errores.<br /><br /> Cuando se obtiene acceso a las propiedades de una interfaz de componentes, Microsoft BizTalk Adapter para PeopleSoft Enterprise usa las API proporcionadas por PeopleSoft, que leen y escriben campos individuales de la interfaz de componentes; sin embargo, estos cambios no se propagan al servidor PeopleSoft uno a uno. En su lugar, psjoa.jar (con la que el adaptador de BizTalk para PeopleSoft Enterprise interactúa) empaqueta todos los cambios y envía los cambios al servidor en un solo paquete.<br /><br /> Si alguna de las actualizaciones individuales produce un error, se devuelve un error genérico, que no ubica el error real. Con el modo interactivo establecido en TRUE, cada actualización de campo se envía al servidor individualmente. Esto tiene un impacto sustancial en el rendimiento, pero proporciona información del error específico si se genera un error en la actualización (por ejemplo, si se usa un valor no válido para configurar un campo).<br /><br /> interactiveMode proporciona el rendimiento máximo y ofrece un informe de errores en el nivel de actualización de campos. Para usar esta característica correctamente, se recomienda realizar llamadas normales con interactiveMode establecido en FALSE. No debe haber ningún impacto en el rendimiento. Si se devuelve un error, se puede recuperar la misma llamada con la marca de interactiveMode establecida en TRUE. Cuando se produce un error en la llamada, el servidor devuelve un mensaje de error más preciso.|  
|`properties`|Estructura que contiene todas las propiedades de la interfaz de componentes. Cuando se llama al método `CreateEx`, estas propiedades se insertan en el registro creado con la o las claves especificadas.|  
  
## <a name="remarks"></a>Comentarios  
 En algunas situaciones, es una práctica común llamar a `CreateEx()` sin un conjunto de claves explícitas, pero la función `CreateEx` devuelve las claves. Este comportamiento es compatible con PeopleCode que se desencadena en el servidor. Por ejemplo, para crear un pedido, el cliente puede no conocer cuál es el siguiente número de PO disponible. Mediante la especificación de NEXT como clave de número de PO, la llamada desencadena PeopleCode, que determina el siguiente número de PO disponible. Esta información se debe devolver al cliente que llama con los parámetros de clave de entrada y salida.  
  
> [!NOTE]
>  Para que este mecanismo funcione, la clave debe ser también una propiedad en el nivel 0. En caso contrario, se devuelve la clave original.  
  
 Se proporciona el método `CreateEx()` de BizTalk Adapter para PeopleSoft Enterprise si las funciones de crear y guardar de PeopleSoft están habilitadas en la interfaz de componentes.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)