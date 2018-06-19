---
title: Diseño de la página de Portal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal
- Portal page [BAM portal]
ms.assetid: 0d8833b7-dd2f-475c-a890-e925ee47d219
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5569021698eb856d7584a2510a27d69f092f37a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231532"
---
# <a name="bam-portal-page-layout"></a>Diseño de la página del portal de BAM
La página del portal de BAM se presenta en los tres marcos siguientes:  
  
-   Pancarta  
  
-   Mis vistas  
  
-   Contenido  
  
## <a name="banner"></a>Pancarta  
 El **pancarta** marco se encuentra en la parte superior de la página del portal. El marco Titular contiene información de marca, como el nombre y el logotipo de la compañía, vínculos a la Ayuda de esa página de la interfaz de usuario (UI) y a títulos de página. Puede personalizar la marca para que se ajuste a las necesidades de la organización. Para obtener más información acerca de cómo personalizar la información de marca en el titular, consulte [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md).  
  
## <a name="my-views"></a>Mis vistas  
 El **Mis vistas** marco está en el lado izquierdo de la página del portal. y muestra a los usuarios todas las vistas de las que se le han concedido permisos. Los usuarios puede expandir cualquier vista para ver las características disponibles para ella. Si no se muestra ninguna vista, es posible que no se haya creado ninguna vista (tarea que realiza normalmente un analista de negocios) o que no se hayan concedido los permisos al usuario (tarea que realiza normalmente un administrador).  
  
 En cada vista puede realizar tres tareas:  
  
-   **Búsqueda de actividad**: le permite crear consultas y alertas basadas en una actividad.  
  
-   **Las agregaciones**: le permite ver los datos agregados y crear alertas basadas en los totales en el gráfico de tabla dinámica.  
  
-   **Administrador de alertas**: le permite crear, editar, ver y suscribirse a alertas.  
  
> [!NOTE]
>  C uando selecciona el Administrador de alertas del marco Mis vistas, solo podrá editar una alerta existente. Para crear alertas nuevas, debe ir a la página Administrador de alertas desde la página Búsqueda de actividad o Agregaciones.  
  
## <a name="content"></a>Contenido  
 El **contenido** marco está en el lado derecho de la página del portal. La página de contenido contiene la información que presenta cada una de las tareas Mis vistas (Búsqueda de actividad, Agregaciones y Administración de alertas). Cuando selecciona una tarea, el marco Contenido cambia para reflejar las funciones asociadas a ella.  
  
## <a name="see-also"></a>Vea también  
 [Búsqueda de actividad en el Portal de BAM página](../core/activity-search-on-the-bam-portal-page.md)   
 [Las agregaciones en el Portal de BAM página](../core/aggregations-on-the-bam-portal-page.md)   
 [Alert Manager en el Portal de BAM de página](../core/alert-manager-on-the-bam-portal-page.md)   
 [Portal de BAM](../core/bam-portal.md)