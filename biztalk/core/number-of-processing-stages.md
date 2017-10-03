---
title: "Número de fases de procesamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f61c5c348e54ea096c921cb6fc63f0db339dbf4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-processing-stages"></a>Número de fases de procesamiento
La solución separa el proceso de pedido en fases, de modo que se pueda modificar el proceso (al sustituir fases) sin interrumpir los pedidos de larga duración. Para obtener más información acerca de cómo se dividió el proceso en fases, vea "Dividir procesos empresariales" en [algunos principios de diseño de la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).  
  
 La versión actual de la solución sólo contiene dos etapas de procesamiento. No obstante, podría incluir muchas más. Un mayor número de fases proporciona más puntos en los que se pueden controlar las versiones del proceso y seguir trabajando en la versión más reciente de una fase de procesamiento. Sin embargo, cada fase agrega una sobrecarga de mensajes de coordinación adicionales que pasan por la base de datos de cuadro de mensajes, lo que aumenta el tiempo de procesamiento. Debe supervisar el rendimiento de la solución para determinar si el número de fases es excesivo.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)