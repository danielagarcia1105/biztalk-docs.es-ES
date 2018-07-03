---
title: Esquemas de origen y destino | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- destination schemas
- source schemas, maps
- XML schemas, defining
- destination schemas, about destination schemas
- schemas, destination
- destination schemas, maps
- maps, source schemas
- schemas, Root Reference property
- Root Reference property, modifying
- source schemas
- modifying, Root Reference property
- maps, Root Reference property
- source schemas, about source schemas
- schemas, maps
- maps, schema requirements
- schemas, requirements
- schemas, source schemas
- maps, destination schemas
- Root Reference property
ms.assetid: 8c805854-9fa1-4ce3-938d-a2e61ba17fa1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcbb3e36122af0bae4809435b8cc1d74b46ea1ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011373"
---
# <a name="source-and-destination-schemas"></a>Esquemas de origen y de destino.
Cada asignación de BizTalk utiliza dos esquemas: un esquema de origen y un esquema de destino. El esquema de origen define la estructura de los mensajes de instancia desde los que está tomando datos. El esquema de destino define la estructura de los mensajes de instancia que produce la asignación. Por ejemplo, si desea asignar la información de envío y facturación de un pedido a una factura, necesita un esquema para definir pedidos en el esquema de origen y un esquema que defina facturas en el esquema de destino.  
  
 Los esquemas utilizados en las asignaciones de BizTalk deben cumplir las siguientes condiciones:  
  
- Los esquemas de origen y de destino tienen que ser una parte del proyecto de BizTalk en uso, o deberá incluir una referencia a esos esquemas en el ensamblado, de modo que se pueda obtener acceso a ellos en tiempo de ejecución.  
  
- Los esquemas utilizados en el Asignador de BizTalk deben estar basados en el lenguaje de definición de esquemas XML (XSD). El Editor de BizTalk proporciona una manera sencilla de crear esos esquemas. Para obtener más información acerca de cómo crear esquemas con el Editor de BizTalk, consulte [crear esquemas utilizando BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md). Consulte también [crear esquemas](../core/creating-schemas.md).  
  
  En el Editor de BizTalk, puede crear esquemas con múltiples nodos raíz. No obstante, si utiliza un esquema con múltiples nodos raíz en una asignación de BizTalk, deberá elegir cuál de ellos (con la subestructura correspondiente) utilizar en la asignación. Los esquemas tienen un **referencia raíz** propiedad que identifica la raíz que es el principal. Si un esquema tiene múltiples raíces y la **referencia raíz** propiedad se establece cuando el esquema se abre por primera vez como el origen o el esquema de destino, utiliza el asignador de BizTalk la raíz especificada. Si un esquema tiene múltiples raíces y la **referencia raíz** no está establecida la propiedad, el asignador de BizTalk le solicita que elija una raíz.  
  
  Si cambia el **referencia raíz** propiedad de un esquema ya utilizado en una asignación, el asignador de BizTalk no percibe el cambio y continúa usando la raíz especificada originalmente. Si desea generar diferentes asignaciones mediante diferentes raíces del mismo esquema, es mejor no establecer el **referencia raíz** propiedad. De este modo, siempre que se utilice el esquema para una nueva asignación, deberá elegir la raíz explícitamente.  
  
  Si modifica un esquema tras incluirlo en una asignación, podrían dañarse los vínculos dentro de esta asignación.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Creación de mapas con el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)