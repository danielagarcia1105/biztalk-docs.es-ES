---
title: "Vinculación de registro a registro | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6abc3d27ad3ee2f135e3ff5c8c1749fcae5f4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="record-to-record-linking"></a>Vinculación de registro a registro

## <a name="overview"></a>Información general
En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede usar el Asignador de BizTalk para crear varios vínculos entre partes similares de los esquemas de origen y de destino al mismo tiempo. En versiones anteriores de BizTalk Server, tenía que crear esos vínculos individualmente, uno por uno. Existen dos tipos diferenciados de vinculación de registro a registro, cada una de ellas es apropiada para escenarios diferentes en función del grado de similitud de las estructuras de los registros del esquema de origen y de destino que se vinculen, como se indica a continuación  
  
-   **Vinculación de estructura.** Utilice la vinculación de estructura, cuando la estructura de los registros que se vinculan en los esquemas de origen y de destino sea igual o muy similar.  
  
-   **Vinculación de coincidencia de nombre.** Utilice una vinculación de coincidencia de nombres cuando la estructura de los registros que se vinculan en los esquemas de origen y de destino sea bastante similar, y tengan coincidencia de nombres de registros y campos, pero con más excepciones estructurales de las aceptables con la vinculación de estructura.  
  
    > [!NOTE]
    >  Vinculación de registro a registro se aplica únicamente cuando se configura mediante la vinculación de valor-copia el **vínculos de origen** propiedad.  
  
## <a name="record-to-record-linking-structure-links"></a>Vinculación de registro a registro: Vínculos de estructura  
 Utilice la vinculación de estructura, cuando la estructura de los registros que desee vincular en los esquemas de origen y de destino sea igual o prácticamente igual.  
  
 Si la estructura de los esquemas es idéntica, solo necesitará agregar un enlace en el nodo raíz de cada esquema. En el menú contextual, seleccione el modo de vinculación deseado.  
  
 Si la estructura de algunos registros de los esquemas es idéntica, solo necesitará agregar un vínculo entre esos registros de cada esquema. En el menú contextual, seleccione el modo de vinculación deseado.  
  
 Para obtener información acerca de cómo configurar el registro de registro de vinculación, vea vinculación como mediante la vinculación de estructura o de coincidencia de nombres [automáticamente registros de vínculo](../core/how-to-link-records-automatically.md).  
  
> [!NOTE]
>  Los vínculos de estructura son el tipo predeterminado en la vinculación de registro a registro.  
  
## <a name="record-to-record-linking-name-matching-links"></a>Vinculación de registro a registro: Coincidencia de nombres vínculos  
 Utilice la vinculación de coincidencia de nombres, cuando la estructura de los registros que desee vincular en los esquemas de origen y de destino sea muy similar, pero no exactamente igual. Por ejemplo, el esquema de origen y de destino podría tener más registros o campos subordinados dentro de los nodos que se van a vincular que el otro esquema.  
  
 Para crear un vínculo de coincidencia de nombres entre partes de los esquemas de origen y de destino que tengan estructuras casi coincidentes, incluidos los esquemas enteros si procede, cree un vínculo con origen en un nodo principal de la subjerarquía y finalice en otro nodo principal de la subjerarquía. En el menú contextual, seleccione el modo de modo deseado. Después de vincular los nodos, se crean automáticamente los vínculos de todos los registros y campos subordinados de los esquemas de origen y de destino que se llaman igual y tienen la misma subestructura.  
  
 Para obtener información acerca de cómo configurar el registro de registro de vinculación, vea vinculación como mediante la vinculación de estructura o de coincidencia de nombres [automáticamente registros de vínculo](../core/how-to-link-records-automatically.md).  
  
## <a name="see-also"></a>Vea también  
 [Vincular registros automáticamente](../core/how-to-link-records-automatically.md)   
 [Editar propiedades de vínculo](../core/how-to-edit-link-properties.md)