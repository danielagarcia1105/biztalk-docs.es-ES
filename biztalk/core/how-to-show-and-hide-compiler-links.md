---
title: Cómo mostrar y ocultar los vínculos de compilador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66bfd9de-c4d2-46ee-854f-cf7c7cd07368
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66d9b9ee8901ea2d93a73fd227a0ac1623e25669
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255548"
---
# <a name="how-to-show-and-hide-compiler-links"></a>Cómo mostrar y ocultar vínculos de compilador
Al compilar una asignación, el Asignador de BizTalk crea vínculos adicionales, conocidos como vínculos de compilador para contar con todos los vínculos que se necesitan en la asignación. Algunos de estos vínculos no tienen que ver con los vínculos que usted ha creado. Cuando compila, o comprueba, una asignación, la línea final de la ventana Resultados de Visual Studio le permite mostrar u ocultar estos vínculos de compilador adicionales en la ventana principal. De forma predeterminada, los vínculos de compilador aparecen como líneas discontinuas rojas.  
  
### <a name="to-show-or-hide-compiler-links"></a>Para mostrar u ocultar los vínculos de compilador  
  
1.  En el Explorador de soluciones, haga clic en la asignación cuyos vínculos de compilador que desea ver y, a continuación, haga clic en **comprobar asignación**.  
  
2.  En la ventana Lista de errores de Visual Studio, desplácese hasta el final y haga doble clic en la línea que dice **hacer doble clic aquí para mostrar u ocultar los vínculos de compilador**.  
  
     Para cambiar el estado de vista de los vínculos de compilador de mostrar a ocultar o de ocultar a mostrar, simplemente haga doble clic en la línea nuevamente.  
  
    > [!NOTE]
    >  Cuando se compilación o vuelve a generar un proyecto de BizTalk o una solución que contiene una o varias asignaciones, el mensaje **hacer doble clic aquí para mostrar u ocultar los vínculos de compilador** se muestra en el **lista de errores** ventana de Visual Studio para todas las asignaciones del proyecto o solución.  
  
 Para comprobar una asignación, debe configurar las propiedades de las instancias de entrada y de salida. Para obtener más información acerca de cómo configurar estas propiedades, vea [cómo configurar la validación del mapa y los parámetros de prueba](../core/how-to-configure-map-validation-and-test-parameters.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md)