---
title: "Vínculos en asignaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32d2a9ef07cf2d79037d7983e49b26c6cfe5e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="links-in-maps"></a>Vínculos en asignaciones
Los vínculos especifican la función básica de copiar datos de un elemento o atributo de un mensaje de instancia de entrada en un elemento o atributo de una instancia de salida. Los vínculos entre registros y campos en los esquemas de origen y de destino se crean en tiempo de diseño. De esta forma, se impulsa la creación, en tiempo de ejecución, de un mensaje de instancia de salida que se ajusta al esquema de destino desde un mensaje de instancia de entrada que se ajusta al esquema de origen.  
  
 El Asignador de BizTalk admite vínculos de uno a uno y de uno a muchos. Por ejemplo, un vínculo puede conectar un registro o campo único del esquema de origen con un registro o campo único del esquema de destino. Un vínculo también puede conectar un registro o campo único del esquema de origen con múltiples registros o campos del esquema de destino.  
  
 Los vínculos también pueden conectar varios registros o campos del esquema de origen con un functoid que, a continuación, se conecta con uno o varios registros o campos únicos del esquema de destino. En general, los vínculos directos desde varios registros o campos de origen hasta un registro o campo de destino único no son válidos y generan una advertencia. Una excepción a esto es el **bucle** functoid. Para obtener más información sobre la **bucle** functoid, consulte [Functoid de bucle de](../core/looping-functoid.md).  
  
 En los temas de esta sección se describen conceptos relativos a la creación y el trabajo con vínculos en el Asignador de BizTalk.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tipos de vínculos](../core/types-of-links.md)  
  
-   [Crear vínculos](../core/creating-links.md)  
  
-   [Configuración de vínculos](../core/configuring-links.md)  
  
-   [Vinculación de registro a registro](../core/record-to-record-linking.md)  
  
-   [Vínculos a y desde el elemento Any y anyAttribute nodos](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [Vínculos y directivas de compilador](../core/compiler-directives-and-links.md)