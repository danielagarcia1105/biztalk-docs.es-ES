---
title: Control de etiqueta en los registros posicionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804647b3cf43b9b6747b2e5f50e05e38313b03d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tag-handling-in-positional-records"></a>Tratamiento de los registros posicionales de las etiquetas

## <a name="overview"></a>Información general
Los registros posicionales pueden incluir una secuencia conocida de caracteres denominada etiqueta que puede usarse para eliminar la ambigüedad existente entre un tipo de registro y otro. Esto permite que el Desensamblador de archivos sin formato identificar correctamente la correspondiente **registro** nodo en el esquema que contiene la información necesaria para analizar correctamente el registro de archivo sin formato.  
  
 Puede usar el **[identificador de etiquetas** y **desplazamiento de etiquetas** propiedades entre sí para especificar la etiqueta y su posición dentro de un registro posicional. Tenga en cuenta que esto permite que la etiqueta aparezca en cualquier lugar dentro del registro posicional y que, según la configuración para la **longitud posicional** y **desplazamiento posicional** propiedades de los distintos campos el registro, la etiqueta se puede interpretar como parte de los datos asociados a uno o varios de estos campos.  
  
 El **desplazamiento posicional** propiedad también permite tratar la etiqueta por separado de los datos en el registro. Por ejemplo, si la etiqueta se produce al principio del registro y es de cuatro caracteres de longitud, podría establecer el valor de la **desplazamiento posicional** propiedad del primer campo en el registro en cuatro, con lo que se omitirá de forma eficaz el etiqueta del registro posicional cuando se convierte el valor del primer campo en el formato XML equivalente del registro.  

Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
## <a name="see-also"></a>Vea también  
 [Consideraciones del registro posicional](../core/positional-record-considerations.md)   
