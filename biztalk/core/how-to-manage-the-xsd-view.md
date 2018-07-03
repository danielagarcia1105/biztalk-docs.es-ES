---
title: Cómo administrar la vista XSD | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3245ebf0-6128-47b4-8e88-ea06ececbc15
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e38707d25355b8ee46a653971b459f1f799614b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004221"
---
# <a name="how-to-manage-the-xsd-view"></a>Cómo administrar la vista XSD
Las tareas de administración con respecto a la vista XSD se pueden dividir en tres categorías: cambiar su tamaño, cambiar el color de fondo y la fuente y cambiar las características de actualización.  
  
 La última categoría, relativa a las características de actualización, es más útil cuando se trabaja con esquemas grandes, donde el uso de una característica de actualización automática puede ocasionar retrasos no deseados. En dichos casos, puede deshabilitar la actualización automática (continua) y, en su lugar, actualizar manualmente la vista XSD cuando sea necesario.  
  
 En este tema se proporcionan instrucciones paso a paso para estas tareas.  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a>Para hacer que la vista XSD sea más alta o más baja  
  
1. Mueva el puntero del mouse hasta el borde inferior de la ventana de edición principal de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la que se presenta la vista XSD y la vista de árbol de esquema de forma adyacente, hasta que el cursor cambie al icono de cambio de tamaño vertical de la ventana estándar.  
  
2. Haga clic y mantenga presionado el botón primario del mouse y arrastre el borde de la ventana hacia arriba o hacia abajo.  
  
    Ha cambiado el tamaño vertical de la vista XSD al cambiar el tamaño vertical de toda la ventana de edición principal.  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a>Para hacer que la vista XSD sea más ancha o más estrecha  
  
1. Mueva el puntero del mouse hasta el divisor de panel en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] la ventana de edición principal, que divide la vista XSD desde la vista de árbol de esquema, hasta que el cursor cambia a horizontal, el icono de cambio de tamaño de ventana estándar.  
  
2. Haga clic y mantenga presionado el botón primario del mouse y arrastre el borde del panel hacia la izquierda (más ancho) o hacia la derecha (más estrecho).  
  
    Ha cambiado el tamaño horizontal de la vista XSD al cambiar la parte de la ventana de edición principal que se dedica a la vista XSD con respecto a la vista de árbol de esquema.  
  
    También puede hacer que la vista XSD sea más ancha o estrecha al cambiar el tamaño horizontal de toda la ventana de edición principal.  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a>Para cambiar el color de fondo o la fuente utilizados por la vista XSD  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.  
  
2. En el **opciones** cuadro de diálogo, haga clic en la carpeta Editor de BizTalk y, si es necesario, expanda el **Mostrar esquema** categoría, haga clic en el signo más (+) icono.  
  
3. Cambiar el color de fondo o la fuente mediante el selector de colores de la lista desplegable o **fuente** cuadro de diálogo asociado con el **Color de fondo de vista XSD** y **fuente de vista XSD** las propiedades, respectivamente.  
  
    Acceso a la **fuente** cuadro de diálogo mediante el uso de los puntos suspensivos (**...** ) situado en el extremo derecho de la **fuente de vista XSD** cuadro del valor de propiedad.  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a>Para activar y desactivar la actualización automática de la vista XSD  
  
-   En el Editor de BizTalk, a continuación el **XSD** , haga clic **desactivar actualización automática** o **Activar actualización automática**.  
  
     Cuando la actualización automática está desactivada, la vista XSD está en blanco.  
  
    > [!IMPORTANT]
    >  De forma predeterminada, la actualización automática está activada. A medida que los esquemas se vayan haciendo más grandes, será importante que desactive la característica de actualización automática y que actualice el esquema de forma manual cuando lo necesite.  
  
### <a name="to-manually-refresh-the-xsd-view"></a>Para actualizar manualmente la vista XSD  
  
-   En el **BizTalk** menú, haga clic en **actualizar XSD**.  
  
     La vista XSD se actualiza para reflejar cualquier cambio realizado en el árbol de esquema.  
  
    > [!NOTE]
    >  También manualmente, puede actualizar la vista XSD haciendo **actualizar XSD** en el menú contextual asociado a cada nodo del árbol de esquema, o haga clic en el **actualizar** vínculo siguiente el **XSD** ficha en la vista XSD.  
  
## <a name="see-also"></a>Vea también  
 [Usar el Editor de BizTalk](../core/using-biztalk-editor.md)