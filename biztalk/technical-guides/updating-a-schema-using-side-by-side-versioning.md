---
title: Actualización de un esquema con el control de versiones en paralelo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7360ec5-b5e9-40c7-9a7c-965fcc95ddb0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0d9d3a204641ac4bccb856e62be15cc2589786
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976421"
---
# <a name="updating-a-schema-using-side-by-side-versioning"></a>Actualización de un esquema con el control de versiones en paralelo
Puede realizar el control de versiones en paralelo con esquemas. Hacerlo agregando una nueva versión del esquema a un ensamblado, actualizar la versión del esquema, dejando el esquema existente (y su versión) sin cambios.  
  
 Si se incrementa la versión del esquema, debe actualizar la referencia al esquema para cualquier instancia y componentes de canalización que lo usan. También debe actualizar las asignaciones que hacen referencia el esquema (o creación nuevas asignaciones), así como todas las orquestaciones que se basan en el esquema.  
  
 Si anula la implementación de un esquema, la versión anterior del esquema, si está disponible, se activará.  
  
## <a name="schema-resolution-in-pipelines"></a>Resolución de esquemas en las canalizaciones  
 Si se agrega a una aplicación un ensamblado que incluye un nuevo esquema con el mismo tipo de mensaje como un esquema existente en el grupo de BizTalk, se usará el esquema con el número de versión más reciente cuando se produce la resolución de esquema en las canalizaciones. Si un tipo de mensaje hace referencia a más de un tipo. NET, esta ambigüedad puede provocar un error de ejecución de canalización. Esto se debe a que la búsqueda de esquemas usa el tipo de mensaje, el espacio de nombres de destino y el nombre de raíz de la instancia. Este tipo de error puede producirse por las canalizaciones en cualquier aplicación que usa un esquema con el mismo tipo de mensaje que el nuevo esquema. Para obtener más información acerca de la resolución de esquemas, vea [resolución de esquemas en componentes de canalización](http://go.microsoft.com/fwlink/?LinkID=154207) (<http://go.microsoft.com/fwlink/?LinkID=154207>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 El comportamiento de resolución de esquema para el desensamblador XML puede requerir cambios adicionales después de agregar una nueva versión de un esquema en paralelo con una versión anterior. En algunos casos, es posible que desee referencias de codificar de forma rígida en las propiedades de canalización del desensamblador en el Diseñador de canalizaciones a versiones específicas de los esquemas. Esto le permite evitar el comportamiento de resolución dinámica, en el que el desensamblador XML determina qué esquema cargar mediante el tipo de mensaje dinámicamente detectados en tiempo de ejecución desde el mensaje contenido XML.  
  
## <a name="updating-a-schema-in-an-orchestration"></a>Actualización de un esquema en una orquestación  
 Cuando cambia el esquema asociado con el envío de varios y las formas recepción en una orquestación, puede realizar cambios mucho más fácil estableciendo la propiedad de tipo de mensaje para el mensaje asociado con cada envío o recepción forma para el tipo de mensaje de varias partes, en lugar de Esquema. A continuación, puede establecer la propiedad Type de la parte del mensaje asociada a cada formas para que sea el mismo esquema. Al hacerlo, puede cambiar posteriormente el esquema de cambiar la propiedad de tipo para cada parte del mensaje, en lugar de tener que cambiar el tipo de mensaje para cada forma. Para obtener más información sobre cómo realizar cambios más fácil mediante este proceso, consulte el [8 sugerencias y trucos para la programación de BizTalk mejor](http://go.microsoft.com/fwlink/?LinkId=101594) notas del producto (http://go.microsoft.com/fwlink/?LinkId=101594).  
  
## <a name="versioning-schemas"></a>Control de versiones de esquemas  
 BizTalk Server toma un esquema de la versión más reciente del ensamblado que lo contiene. Esto significa que, si crea una nueva versión de un esquema, la nueva versión reemplaza totalmente todas las versiones anteriores del esquema. Esto funciona bien cuando las transacciones duran poco. Sin embargo, las transacciones en la solución de administración de procesos empresariales son de larga duración: un pedido puede tardar hasta un año para completar.  
  
 Para permitir la posibilidad de usar varias versiones de un esquema en uso, cada esquema de la solución incluye un número de versión en su espacio de nombres. Canalizaciones de BizTalk determinan el tipo de mensaje de un mensaje basándose en el espacio de nombres de destino más el nombre del nodo raíz definido en el esquema. Por ejemplo, el espacio de nombres del esquema Order es el siguiente:  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 Dado que el espacio de nombres identifica el esquema y la inclusión de la hace de número de versión del espacio de nombres único para el esquema, el nuevo esquema será distinto de la versión anterior. Por tanto, se puede usar un nuevo esquema sin suplantar el esquema anterior.  
  
 Cambiar la versión de esquema puede afectar a muchas partes de la solución, por lo que debe planearse de antemano. Para obtener más información sobre el efecto de los cambios de versión de esquema, vea [resolución de esquemas en componentes de canalización](http://go.microsoft.com/fwlink/?LinkID=154207) (<http://go.microsoft.com/fwlink/?LinkID=154207>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Al cambiar la versión de esquemas en una orquestación, use los tipos de mensaje de varias partes. Esto dará lugar a una mayor flexibilidad cuando los esquemas de control de versiones. Para obtener más información acerca de las ventajas del uso de tipos de mensaje de varias partes, vea sugerencia #1, "Siempre uso parte de varios tipos de mensaje," en el artículo de MSDN Magazine [8 sugerencias y trucos para mejorar la programación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=101594) (http://go.microsoft.com/fwlink/?LinkId=101594).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos recomendados para actualizar las aplicaciones](../technical-guides/best-practices-for-updating-applications.md)