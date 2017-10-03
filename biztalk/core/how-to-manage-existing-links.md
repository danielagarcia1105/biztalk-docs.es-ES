---
title: "Cómo administrar vínculos existentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e61bc8c7fbf015eba28666c63dbeabf57a39e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-existing-links"></a>Cómo administrar vínculos existentes
A veces puede que necesite cambiar el origen o el destino de un vínculo, asignar o cambiar su nombre o bien eliminar un vínculo. En este tema se proporcionan instrucciones detalladas para llevar a cabo estas operaciones de tipos de vínculo.  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a>Para modificar el origen o el destino de un vínculo  
  
1.  En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.  
  
     Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.  
  
2.  Arrastre cualquier extremo del vínculo al nuevo nodo de esquema o functoid con el que desea conectarlo.  
  
     Cuando arrastre el extremo, el cursor se convertirá en una cruz. Si selecciona un nodo de esquema o functoid (u otro objeto) que no puede aceptar el vínculo, el cursor se convierte en un círculo con una barra diagonal.  
  
    > [!IMPORTANT]
    >  Si hay dos o más vínculos de entrada conectados con un functoid y redirige uno o más de estos vínculos de entrada a otros nodos del esquema de origen o a otros functoids, el orden de los parámetros de entrada al functoid original puede que no se conserve. Use la **configurar \<Functoid > Functoid** cuadro de diálogo para revisar el orden resultante de los parámetros de entrada y para reordenarlos si fuera necesario. Para obtener más información acerca de la reorganización de los parámetros de entrada de un functoid, consulte [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md).  
  
### <a name="to-setedit-the-label-of-a-link"></a>Para configurar o editar la etiqueta de un vínculo  
  
1.  En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.  
  
     Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.  
  
2.  En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, proporcione un nombre (nuevo) para el vínculo mediante el **etiqueta** propiedad.  
  
### <a name="to-delete-a-link"></a>Para eliminar un vínculo  
  
1.  En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.  
  
     Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.  
  
2.  En el **editar** menú, haga clic en **eliminar**.  
  
     También puede presionar la tecla SUPR o haga clic en el vínculo y haga clic en **eliminar** en el menú contextual.  
  
    > [!NOTE]
    >  Puede seleccionar de forma masiva varios functoids o vínculos y eliminarlos en una única operación. Puede deshacer o rehacer la eliminación masiva de vínculos o functoids. Para obtener más información acerca de cómo deshacer y rehacer las operaciones, vea [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md)