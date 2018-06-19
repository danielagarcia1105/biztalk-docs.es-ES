---
title: Mediante el Explorador de directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Policy Explorer
- policies, Policy Explorer
- business rules, Policy Explorer
- Policy Explorer [Business Rule Composer]
ms.assetid: 249b1b72-ba84-4695-ba2b-16f081710b20
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66b88618f10bf204701e6fcd68d7d95007966c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288348"
---
# <a name="using-policy-explorer"></a>Mediante el Explorador de directivas
Puede utilizar el Explorador de directivas para administrar directivas y reglas en el almacén de reglas. Puede crear, modificar y eliminar directivas y reglas, así como probar, publicar, implementar y anular la implementación de directivas.  
  
 En la siguiente tabla se describen los comandos del Explorador de directivas que pueden utilizarse en el proceso de desarrollo de nuevas directivas y reglas.  
  
|Use|Para|  
|--------------|----------------|  
|**Agregar nueva directiva**|Crear una directiva nueva (conjunto de reglas).|  
|**Agregar nueva versión**|Crear una versión nueva vacía de la directiva seleccionada. Puede copiar reglas de otras versiones y pegarlas en la versión nueva.|  
|**Copiar (versión de directiva)**|Copiar la versión de directiva seleccionada en el Portapapeles.|  
|**Copiar (regla)**|Copiar la regla seleccionada en el Portapapeles.|  
|**Cortar (regla)**|Copiar la regla seleccionada en el Portapapeles y borrarla.|  
|**Pegar (versión de directiva)**|Pega una versión de directiva y su contenido en la directiva seleccionada.|  
|**Pegar (regla)**|Pegar una regla en la versión de directiva seleccionada.|  
|**Eliminar (versión de directiva)**|Eliminar la versión de directiva seleccionada.|  
|**Eliminar (regla)**|Eliminar la regla seleccionada.|  
|**Eliminar**|Eliminar la directiva seleccionada y todas sus versiones.|  
|**Agregar nueva regla**|Crear una regla nueva en la versión de directiva seleccionada.|  
|**Guardar**|Guardar todos los cambios realizados en la versión seleccionada y sus reglas.|  
|**Publicar**|Publicar la versión de directiva seleccionada. Tenga en cuenta que no puede modificar directamente una versión publicada. Puede copiarla y pegarla en una versión nueva en la directiva.|  
|**Volver a cargar**|Volver a cargar la versión de la directiva seleccionada y sus reglas, con la opción de descartar cualquier cambio actual realizado en esta versión y restaurar el contenido del almacén de reglas.|  
|**Implementación**|Implementar una versión de la directiva publicada. Debe implementar una versión de directiva para ponerla a disposición de las aplicaciones basadas en reglas.|  
|**Anular la implementación**|Anular la implementación de una versión de directiva. Cuando se haya anulado la implementación de una versión, ésta dejará de disponible para las aplicaciones basadas en reglas.|  
|**Probar directiva**|Probar la versión de directiva seleccionada antes de la implementación.|  
  
## <a name="properties-window"></a>Ventana Propiedades  
 En la tabla siguiente se describen las propiedades de una versión de directiva.  
  
|Propiedad|Valor|  
|--------------|-----------|  
|**Nombre**|Nombre de la directiva.<br /><br /> Solo puede cambiar este valor cambiando el **nombre** propiedad de la directiva (no la versión de directiva).|  
|**Almacenes de datos**|Información acerca del administrador de almacenes de datos para la versión de directiva.|  
|**Profundidad de bucle de ejecución máximo**|Profundidad máxima del algoritmo de encadenamiento directo antes de que se origine una excepción de bucle de ejecución.<br /><br /> El número de bucles predeterminado es 65536.|  
|**Duración de traducción**|Máxima cantidad de tiempo para traducir las reglas antes de que se origine una excepción de tiempo de espera de traducción.<br /><br /> El valor predeterminado es 60000 milisegundos.|  
|**Translator**|Información acerca del traductor utilizado para traducir las reglas.|  
|**Versión actual**|Versión de la directiva actualmente seleccionada en el Explorador de directivas.|  
|**Descripción de la versión**|Descripción de la versión en uso.|  
  
 En la tabla siguiente se describen las propiedades de una regla.  
  
|Propiedad|Valor|  
|--------------|-----------|  
|**Activo**|Indica si la regla está habilitada o deshabilitada|  
|**Nombre**|Nombre de la regla.|  
|**Prioridad**|Prioridad de la regla dentro de la directiva. Cuando mayor es el índice, mayor es la prioridad de la regla. Las acciones de prioridad más alta se activarán primero.<br /><br /> El valor predeterminado es 0 y representa la prioridad media.|