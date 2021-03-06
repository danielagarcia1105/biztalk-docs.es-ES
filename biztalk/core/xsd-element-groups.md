---
title: Grupos de elementos XSD | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT, XSLT variations
- BizTalk Mapper, XSLT variations
- maps, groups
- Choice Group node
- XSD element groups
- XSLT, warnings
ms.assetid: a6ea22cb-6066-480e-8a2a-75fade3e5970
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80b6fdd65067599ed14c37ff00507279ce9b2f47
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006693"
---
# <a name="xsd-element-groups"></a>Grupos de elementos XSD
La utilización de determinadas estructuras en un esquema puede crear variaciones en la transformación de lenguaje de hojas de estilo extensible (XSLT) que genera el Asignador de BizTalk.  
  
 Esto puede ocurrir al incluir un esquema en la asignación que defina grupos de secuencias, de elecciones o de todos los elementos. Por ejemplo, si usa un esquema que incluya un **grupo de elecciones** nodo, es posible crear un mapa que requiere dos o más de los elementos secundarios de la **grupo de elecciones** nodo aparezca en una instancia de salida Mensaje. En este caso, el Asignador de BizTalk muestra una advertencia al compilar la asignación. La advertencia le indica que solo uno de los campos requeridos que ha asignado puede llenarse en la misma iteración del bucle primario en tiempo de ejecución. El Asignador de BizTalk no le mostrará un error para indicarle que la lógica de asignación es incorrecta.  
  
 Otra situación en la que podría generar variaciones en la XSLT es cuando se cumplen las siguientes condiciones:  
  
- **El registro A** tiene un elemento secundario **B de elemento de campo**.  
  
- **Grabar un** y secundarios **B de elemento de campo** producirse una sola vez.  
  
- **El registro A** forma parte de un **grupo de elecciones** que se repite.  
  
  En esta situación, el Asignador de BizTalk genera XSLT que contenga lógica de iteración para controlar las muchas variaciones de los registros de origen que podrían producirse.  
  
> [!NOTE]
>  Deberá ser explícito con respecto a las asignaciones que impliquen a grupos. Por ejemplo, si un esquema de destino contiene un **grupo de elecciones** nodo con los nodos secundarios A y B, no es válido tener a y B simultáneamente en la misma iteración de su grupo primario. El Asignador de BizTalk no evita que cree asignaciones que no son válidas. Por lo tanto, deberá utilizar functoids lógicos para configurar asignaciones en las que A y B nunca aparezcan al mismo tiempo.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Creación de mapas con el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)