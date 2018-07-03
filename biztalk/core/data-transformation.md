---
title: Transformación de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, data translation
- data translation, about data translation
- data transformation, about data transformation
- maps, data transformation
- data transformation, maps
- data translation, maps
ms.assetid: a6aa5e9a-8d9c-478d-8f69-f9b16ed1a18c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4366e37d206902ec3aff5e016c02c4bd721da5b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015958"
---
# <a name="data-transformation"></a>Transformación de datos
Asignar datos se fundamenta en la transformación de datos.  
  
 La transformación de datos es el proceso de creación de una correspondencia entre registros y campos de un esquema de origen y registros y campos (a menudo diferentes) en un esquema de destino. Un ejemplo de transformación de datos es asignar la información de direcciones de envío y facturación de un pedido a una factura. Éste es el tipo de asignación más básico. La transformación de datos también puede aplicarse a operaciones como:  
  
- Calcular el promedio de datos desde un registro de bucle y enviar el resultado a un solo campo del esquema de destino.  
  
- Convertir datos de caracteres en su formato equivalente ASCII.  
  
- Sumar o restar datos de uno o más registros y colocar el resultado en un solo campo del esquema de destino.  
  
  Si desea traducir datos de un formato a otro, debería usar una canalización. Esto puede ser útil para resolver problemas de integración de aplicaciones de negocio, porque traduce un tipo de mensaje dado en formatos alternativos que los sistemas existentes requieren, pero no puede hacerse mediante una asignación.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Creación de mapas con el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)