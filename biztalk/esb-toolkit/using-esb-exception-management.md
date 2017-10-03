---
title: "Mediante la administración de excepciones de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec20c447b184c2fdadf87f62f37f576f5100d08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-esb-exception-management"></a>Uso de administración de excepciones de ESB
Errores y excepciones pueden producirse en un intervalo de contextos y durante una serie de fases de procesamiento diferentes en un ESB. Esta sección proporciona información sobre el control de excepciones y describe cómo publicar detalles a través del Portal de administración de ESB.  
  
## <a name="overview"></a>Información general  
 Hay muchas maneras de controlar las excepciones en un [!INCLUDE[prague](../includes/prague-md.md)] solución, incluido el uso de marcos de trabajo, como la biblioteca de información empresarial. Sin embargo, cuando se desarrolla con ESB y BizTalk Server, se trabaja en un entorno basado en el mensaje. Todo el contenido de una solución de BizTalk está orientado a mensajes, y los programadores de BizTalk pensar en un modo orientado a mensajes. Por lo tanto, la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implementa un enfoque orientado a mensajes para el control de excepciones.  
  
 El marco de trabajo de administración de excepciones de ESB sigue un patrón de diseño que proporciona un enfoque flexible para la supervisión de excepciones y permite que las respuestas de error que se origine desde fuera de la solución, quizás en el nivel de unidad de negocio.  
  
 Los temas siguientes describen el marco de trabajo de administración de excepciones de ESB con más detalle:  
  
-   [Diseño de la estructura de administración de la excepción de ESB](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [Los componentes del marco de administración de excepciones](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [Mediante el marco de administración de excepciones](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [Crear controladores de excepción personalizada](../esb-toolkit/creating-custom-exception-handlers.md)