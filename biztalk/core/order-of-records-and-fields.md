---
title: Orden de los registros y campos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, sorting
- XSLT, sorting
ms.assetid: 7fa9b5cd-73bc-496f-a081-4a45da3afe42
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826d46fef73400a5d54e2d1154a1647af85294e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="order-of-records-and-fields"></a>Orden de los registros y de los campos
Las transformaciones del lenguaje de hojas de estilo extensible (XSLT), tal y como las utiliza el Asignador de BizTalk, no garantizan el orden de salida de los elementos y atributos de salida. Esto se debe a que el Asignador de BizTalk genera XSLT examinando la estructura del esquema de destino y, a continuación, propagando los elementos a través de las páginas de cuadrícula para extraer valores de la estructura del esquema de origen. Por ejemplo, si desea crear un archivo de salida en el que figure el registro BillTo Address antes que el registro ShipTo Address, debe asegurarse de que BillTo Address precede al registro ShipTo Address en el esquema de destino.  
  
> [!IMPORTANT]
>  El orden en que los elementos y atributos aparecen en un mensaje de instancia de salida depende del orden de los registros y campos del esquema de destino correspondiente.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)