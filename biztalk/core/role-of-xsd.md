---
title: Rol de XSD | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fe08f6b-563f-4bae-a5be-551e487b2a6d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad2f99b60de5ebb2a3cd7e102a2f3f7b787d1ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268580"
---
# <a name="role-of-xsd"></a>Rol de XSD
El lenguaje de definición de esquemas XML (XSD) proporciona la sintaxis subyacente de los esquemas de mensaje definidos en BizTalk. Aunque las vistas de árbol del Editor de BizTalk y el Asignador de BizTalk utilizan una jerarquía gráfica específica de BizTalk para los nodos de registro y de campo (entre otros tipos de nodos), cada uno con su propio conjunto de propiedades, dichas jerarquías se crean y mantienen como XSD. El Editor de BizTalk proporciona una vista XSD de solo lectura en la que se puede ver la definición XSD creada cuando se agregan o quitan varios nodos de la representación gráfica del esquema en la vista de árbol y cuando se modifican los valores de las propiedades asociadas con esos nodos. Aunque por lo general no es necesario conocer los detalles de XSD para crear correctamente esquemas sencillos con el Editor de BizTalk, si analiza los cambios de XSD que aparecen al realizar modificaciones en la jerarquía del esquema en la vista de árbol, aprenderá a usar el lenguaje XSD.  
  
 La característica de anotación de esquema de XSD, con el amplio conjunto de anotaciones definidas por BizTalk Server, permite ampliar de un modo eficaz la definición XSD para que sea compatible con la semántica necesaria para representar los mensajes que no son XML, como los archivos sin formato.  
  
## <a name="see-also"></a>Vea también  
 [Recursos XSD en Internet](../core/xsd-resources-on-the-web.md)   
 [Acerca de los esquemas](../core/about-schemas.md)