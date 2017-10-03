---
title: "Cómo establecer una alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, creating
- Query Builder [BAM portal], creating alerts
- queries [BAM], aggregations
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal], aggregation alerts
- queries [BAM], alerts
- aggregations, alerts
ms.assetid: 8745d2c6-5bc0-4d7a-8c17-361535f5c6e6
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774fbab86c1da1389b813f621c89f38cf0aa7656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-an-alert"></a>Cómo establecer una alerta
Para establecer una alerta, puede adjuntarla a una búsqueda de actividad, o llegar hasta ella por medio de una agregación.  
  
> [!NOTE]
>  Antes de establecer una alerta en una consulta, deberá ejecutar la consulta y evaluar si las duraciones de ciclo de alerta son apropiadas para el proceso que se está controlando. Si la duración de ciclo es demasiado breve, es posible que se produzca una condición de alerta de manera transitoria y que, como consecuencia, el sistema de alerta no pueda detectarla.  
  
> [!NOTE]
>  Si hace clic en el botón Atrás durante estos procedimientos, puede recibir el siguiente mensaje: "Advertencia: la página ha caducado." Para volver al contenido anterior, presione F5. (Es posible que tenga que presionar F5 varias veces.)  
  
> [!NOTE]
>  Al crear la primera alerta de una vista, no se mostrarán datos para dicha alerta. La definición de una alerta no recopila los datos de alerta correspondientes al marco de tiempo anterior a la creación de la alerta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Debe tener una vista implementada.  
  
-   Asimismo, debe existir una búsqueda de actividad para una alerta de instancia.  
  
-   Debe existir una agregación rellenada para una alerta de agregación.  
  
### <a name="to-set-an-alert-on-an-activity-search"></a>Para establecer una alerta en una búsqueda de actividad  
  
1.  En el **Mis vistas** de marco, haga clic en una vista para expandir la lista de tareas para la vista.  
  
2.  Haga clic en el **búsqueda de actividad** tarea en la vista que ha expandido.  
  
3.  Cree o abra una búsqueda de actividad. Para obtener información acerca de cómo hacerlo, consulte [cómo crear una consulta de búsqueda de actividad](../core/how-to-create-a-query-in-activity-search.md).  
  
4.  En el marco de contenido del portal de BAM, haga clic en el **establecer alerta** botón. El marco de contenido se cargará con la plantilla de creación de alerta.  
  
5.  En el **nombre** texto, escriba un nombre descriptivo para la alerta.  
  
    > [!NOTE]
    >  Los nombres están limitados a 100 caracteres y no puede contener los siguientes caracteres: ~! @# $% ^&amp;* ();  Si usa alguno de estos caracteres en un nombre, aparece un contorno de líneas rojas discontinuo alrededor del campo de texto que indica que debe corregirlo para completar la acción.  
  
6.  Si no desea habilitar la alerta en este momento, desactive la **alerta habilitada** casilla de verificación.  
  
7.  En el **mensaje** texto, escriba el mensaje que se envía cuando se desencadene la alerta.  
  
8.  Desde el **prioridad** lista desplegable, elija el nivel de prioridad para esta alerta. El valor de prioridad indica la gravedad del problema para el que se ha establecido la alerta.  
  
9. En el **propietarios** cuadro de texto, escriba el alias de los propietarios de esta alerta. Use signos de punto y coma para separar los nombres de varios usuarios.  
  
10. En el **alerta seguridad** área, active la casilla de verificación para permitir que otros usuarios vean esta alerta y suscribirse a él.  
  
    > [!NOTE]
    >  Puede cambiar la seguridad de alertas de privada a pública (y viceversa) en cualquier momento. La presencia de suscriptores en la alerta no afectará a esta acción. Sin embargo, al cambiar la seguridad de alertas de pública a privada, deberá tener en cuenta si existen suscriptores a la alerta. Si existen suscriptores a la alerta, éstos no podrán editar su suscripción cuando la alerta pase a ser privada.  
  
11. En la esquina superior derecha de la **detalles de la alerta** área, haga clic en el **guardar alerta** botón.  
  
### <a name="to-set-an-alert-on-an-aggregation"></a>Para establecer una alerta en una agregación  
  
1.  En el **Mis vistas** de marco, haga clic en una vista para expandir la lista de tareas para la vista.  
  
2.  Haga clic en el **agregaciones** de tareas en **Mis vistas** debajo de la vista expande.  
  
3.  En el marco de contenido del portal de BAM, haga clic con el botón secundario en una celda de la columna de totales del informe de tabla dinámica. Se abrirá un menú contextual con funciones disponibles para llevarse a cabo en el total de agregaciones.  
  
    > [!NOTE]
    >  Puede establecer una alerta en un componente específico del total de agregaciones expandiendo el elemento de línea en cuestión. Puede expandir los niveles sucesivos de esta forma, hasta alcanzar el nivel en el que desea establecer la alerta.  
  
4.  En la parte superior del menú contextual, haga clic en **crear alertas**. El marco de contenido se cargará con la plantilla de creación de alerta.  
  
5.  En el **nombre** texto, escriba un nombre descriptivo para la alerta.  
  
    > [!NOTE]
    >  Los nombres están limitados a 100 caracteres y no puede contener los siguientes caracteres: ~! @# $% ^&amp;* ();  Si usa alguno de estos caracteres en un nombre, aparece un contorno de líneas rojas discontinuo alrededor del campo de texto que indica que debe corregirlo para completar la acción.  
  
6.  Si no desea habilitar la alerta en este momento, desactive la **alerta habilitada** casilla de verificación.  
  
7.  En el **mensaje** texto, escriba el mensaje que se envía cuando se desencadene la alerta.  
  
8.  Desde el **prioridad** lista desplegable, elija el nivel de prioridad para esta alerta. El valor de prioridad indica la gravedad del problema para el que se ha establecido la alerta.  
  
9. En el **propietarios** cuadro de texto, escriba el alias de los propietarios de esta alerta. Use signos de punto y coma para separar los nombres de varios usuarios.  
  
10. En el **umbral** área, seleccione una condición de comparación de la **recuento** lista desplegable.  
  
11. En el **duración** texto cuadro, escriba el número de unidades de tiempo en las que se mide el umbral.  
  
12. Desde el **duración** lista desplegable, seleccione la unidad de tiempo.  
  
13. En el **alerta seguridad** área, active la casilla de verificación para permitir que otros usuarios vean esta alerta y suscribirse a él.  
  
    > [!NOTE]
    >  Puede cambiar la seguridad de alertas de privada a pública (y viceversa) en cualquier momento. La presencia de suscriptores en la alerta no afectará a esta acción. Sin embargo, al cambiar la seguridad de alertas de pública a privada, deberá tener en cuenta si existen suscriptores a la alerta. Si existen suscriptores a la alerta, éstos no podrán editar su suscripción cuando la alerta pase a ser privada.  
  
14. En la esquina superior derecha de la **detalles de la alerta** área, haga clic en el **guardar alerta** botón.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear una consulta de búsqueda de actividad](../core/how-to-create-a-query-in-activity-search.md)