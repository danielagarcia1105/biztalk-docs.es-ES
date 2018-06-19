---
title: Actualizar un esquema mediante el control de versiones en paralelo | Documentos de Microsoft
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
ms.openlocfilehash: d3d63b93f665e80f88e2d9e81b2337e7b198b3df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302244"
---
# <a name="updating-a-schema-using-side-by-side-versioning"></a>Actualizar un esquema mediante el control de versiones en paralelo
Puede realizar el control de versiones en paralelo con esquemas. Hacerlo agregando una nueva versión del esquema a un ensamblado, actualizar la versión del esquema, dejando el esquema existente (y su versión) sin modificar.  
  
 Si se incrementa una versión de esquema, debe actualizar la referencia al esquema de las instancias de canalización y los componentes de canalización que lo usan. También debe actualizar las asignaciones que hacer referencia al esquema (o crear nuevas asignaciones), así como todas las orquestaciones que se basan en el esquema.  
  
 Si anula la implementación de un esquema, la versión anterior del esquema, si está disponible, se activará.  
  
## <a name="schema-resolution-in-pipelines"></a>Resolución de esquemas en canalizaciones  
 Si se agrega a una aplicación un ensamblado que incluye un nuevo esquema con el mismo tipo de mensaje como un esquema existente en el grupo de BizTalk, se utilizará el esquema con el número de versión más reciente cuando se produce la resolución de esquema en las canalizaciones. Si un tipo de mensaje hace referencia a más de un tipo. NET, esta ambigüedad puede provocar errores de ejecución de canalización. Esto se debe a que la búsqueda de esquemas usa el tipo de mensaje, el espacio de nombres de destino y el nombre de raíz de la instancia. Este tipo de error puede producirse por canalizaciones en cualquier aplicación que utilice un esquema con el mismo tipo de mensaje como el nuevo esquema. Para obtener más información acerca de la resolución de esquemas, vea [resolución de esquemas en componentes de canalización](http://go.microsoft.com/fwlink/?LinkID=154207) (http://go.microsoft.com/fwlink/?LinkID=154207) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 El comportamiento de resolución de esquema para el desensamblador XML puede requerir cambios adicionales después de agregar una nueva versión de un esquema paralelo con una versión anterior. En algunos casos, puede que desee a las referencias de codificar de forma rígida en las propiedades del desensamblador de canalización en el Diseñador de canalizaciones a versiones específicas de los esquemas. Esto le permite evitar el comportamiento de resolución dinámica, en el que el desensamblador XML determina qué esquema cargar mediante el tipo de mensaje dinámicamente detectados en tiempo de ejecución desde el mensaje contenido XML.  
  
## <a name="updating-a-schema-in-an-orchestration"></a>Actualizar un esquema en una orquestación  
 Al cambiar el esquema asociado a varios envío y recepción formas en una orquestación, puede realizar cambios mucho más fácil estableciendo la propiedad de tipo de mensaje para el mensaje asociado a cada envío o recepción forma para el tipo de mensaje de varias partes, en lugar de Esquema. A continuación, puede establecer la propiedad Type de la parte del mensaje asociada a cada formas para que sea el mismo esquema. Por ello, puede cambiar posteriormente el esquema cambiar la propiedad de tipo para cada parte del mensaje, en lugar de tener que cambiar el tipo de mensaje para cada forma. Para obtener más información sobre cómo realizar cambios más fácil por este proceso, consulte la [8 sugerencias y trucos para la programación de BizTalk mejor](http://go.microsoft.com/fwlink/?LinkId=101594) notas del producto (http://go.microsoft.com/fwlink/?LinkId=101594).  
  
## <a name="versioning-schemas"></a>Control de versiones de esquemas  
 BizTalk Server toma un esquema de la versión más reciente del ensamblado que lo contiene. Esto significa que, si crea una nueva versión de un esquema, la nueva versión reemplaza por completo todas las versiones anteriores del esquema. Esto funciona bien cuando las transacciones duran poco. Sin embargo, las transacciones en la solución de administración de procesos empresariales son de larga duración: un pedido puede tardar un año en completarse.  
  
 Para permitir la posibilidad de usar varias versiones de un esquema en uso, cada esquema de la solución incluye un número de versión en su espacio de nombres. Canalizaciones de BizTalk determinan el tipo de mensaje de un mensaje basándose en el espacio de nombres de destino más el nombre del nodo raíz definido en el esquema. Por ejemplo, el espacio de nombres del esquema Order es el siguiente:  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 Dado que el espacio de nombres identifica el esquema y la inclusión de la hace de número de versión del espacio de nombres único para el esquema, el nuevo esquema será distinto de la versión anterior. Por tanto, se puede usar un nuevo esquema sin suplantar el esquema anterior.  
  
 Si cambia la versión de esquema puede afectar a muchas partes de la solución, por lo que esta acción debe planearse de antemano. Para obtener más información sobre el efecto de los cambios de versión de esquema, consulte [resolución de esquemas en componentes de canalización](http://go.microsoft.com/fwlink/?LinkID=154207) (http://go.microsoft.com/fwlink/?LinkID=154207) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Al cambiar la versión de esquemas en una orquestación, use los tipos de mensaje de varias partes. Esto dará lugar a una mayor flexibilidad cuando los esquemas de control de versiones. Para obtener más información acerca de las ventajas del uso de tipos de mensaje de varias partes, vea Consejo #1, "Siempre uso parte varios tipos de mensaje," en el artículo de MSDN Magazine [8 sugerencias y trucos para mejorar la programación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=101594) (http://go.microsoft.com ¿/fwlink/? LinkId = 101594).  
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas para actualizar las aplicaciones](../technical-guides/best-practices-for-updating-applications.md)