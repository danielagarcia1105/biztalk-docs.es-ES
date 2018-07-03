---
title: Directivas de compilador y los vínculos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compilier directives
- maps, compiling
- BizTalk Mapper, compiler directives
- links [maps], compiling
ms.assetid: 1655e10c-af98-4100-849d-b8214f93cfe9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38e00b7d20e6fd0aff4f6af72377e301a812b8fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992005"
---
# <a name="compiler-directives-and-links"></a>Vínculos y directivas de compilador
Puede configurar las dos siguientes directivas de compilador vínculo por vínculo:  
  
- Qué datos del mensaje de instancia de entrada se recuperan y copian como valor de elemento o atributo correspondiente en el mensaje de instancia de salida.  
  
  > [!NOTE]
  >  Estos datos incluyen la opción de copiar el propio nombre del elemento o atributo, en vez de cualquier valor asociado con ellos. Generalmente, los nombres de elemento o atributo no se consideran como una parte de los datos transmitidos en un mensaje de instancia XML.  
  
- Cómo llevar a cabo la coincidencia de nodos entre los esquemas de origen y de destino.  
  
  En esta sección se proporciona un explicación detallada de las opciones disponibles para estas directivas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración de transformación de datos](../core/data-transformation-configuration.md)  
  
-   [Coincidencia del nivel jerárquico de nodos](../core/node-hierarchy-level-matching.md)