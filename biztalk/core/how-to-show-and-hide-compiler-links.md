---
title: Cómo mostrar y ocultar vínculos de compilador | Microsoft Docs
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
ms.openlocfilehash: f3c006f5de761837ec1ed0d6f983d380a76a50a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010053"
---
# <a name="how-to-show-and-hide-compiler-links"></a>Cómo mostrar y ocultar vínculos de compilador
Al compilar una asignación, el Asignador de BizTalk crea vínculos adicionales, conocidos como vínculos de compilador para contar con todos los vínculos que se necesitan en la asignación. Algunos de estos vínculos no tienen que ver con los vínculos que usted ha creado. Cuando compila, o comprueba, una asignación, la línea final de la ventana Resultados de Visual Studio le permite mostrar u ocultar estos vínculos de compilador adicionales en la ventana principal. De forma predeterminada, los vínculos de compilador aparecen como líneas discontinuas rojas.  
  
### <a name="to-show-or-hide-compiler-links"></a>Para mostrar u ocultar los vínculos de compilador  
  
1. En el Explorador de soluciones, haga clic en la asignación cuyos vínculos de compilador desea ver y, a continuación, haga clic en **comprobar asignación**.  
  
2. En la ventana Lista de errores de Visual Studio, desplácese hasta el final y haga doble clic en la línea que dice **hacer doble clic aquí para mostrar u ocultar vínculos de compilador**.  
  
    Para cambiar el estado de vista de los vínculos de compilador de mostrar a ocultar o de ocultar a mostrar, simplemente haga doble clic en la línea nuevamente.  
  
   > [!NOTE]
   >  Cuando se compilación o vuelve a generar un proyecto de BizTalk o una solución que contiene una o varias asignaciones, el mensaje **hacer doble clic aquí para mostrar u ocultar vínculos de compilador** se muestra en el **lista de errores** ventana de Visual Studio para todas las asignaciones en el proyecto o solución.  
  
   Para comprobar una asignación, debe configurar las propiedades de las instancias de entrada y de salida. Para obtener más información sobre cómo configurar estas propiedades, vea [cómo configurar la validación del mapa y los parámetros de prueba](../core/how-to-configure-map-validation-and-test-parameters.md).  
  
## <a name="see-also"></a>Vea también  
 [Uso de vínculos para especificar asignaciones de registros y campos](../core/using-links-to-specify-record-and-field-mappings.md)