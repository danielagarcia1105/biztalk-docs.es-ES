---
title: Cómo resolver errores y advertencias de asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2983a53bb47aa66d1564772d0f8e033132e5a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254884"
---
# <a name="how-to-resolve-map-warnings-and-errors"></a>Cómo resolver errores y advertencias de asignaciones
Cuando compila una asignación, se pueden producir errores y advertencias como resultado del proceso de compilación.  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a>Resolver errores y advertencias al generar un mapa  
  
1.  Si hay errores de vínculos y functoids, en la **lista de errores** ventana, haga doble clic en cualquier descripción.  
  
     Se resalta el vínculo, functoid o nodo de esquema asociado con el error. Resuelva el problema.  
  
2.  Revise el **descripción** área en el **lista de errores** ventana para determinar si hay errores adicionales.  
  
3.  Haga clic en el **salida** pestaña de ventana para ver información adicional de mensaje de advertencia y error.  
  
4.  Después de haber resuelto todos los problemas, haga clic en el nombre de archivo de asignación en el Explorador de soluciones y, a continuación, haga clic en **comprobar asignación** o **generar solución**, pueda tener.  
  
    > [!NOTE]
    >  Si aparece una advertencia, el problema puede existir en varias páginas de cuadrícula. Por ejemplo, tiene la página de cuadrícula 1 con un registro (denominado **elemento**) en el árbol de esquema de origen vinculado a un registro (denominado **número**) en el árbol de esquema de destino. En la página de cuadrícula 2 tiene un registro (denominado **producto**) en el árbol de esquema de origen vinculado a la misma **número** registros en el árbol de esquema de destino. En este escenario, se genera un mensaje de advertencia que indica que tiene varias entradas para el mismo registro. Sin embargo si se muestra una página de cuadrícula 1, verá solo una entrada en el **número** registro. 
  
## <a name="see-also"></a>Vea también  
 [Compilar y probar las asignaciones](../core/compiling-and-testing-maps.md)   
 [Errores del asignador de BizTalk](../core/biztalk-mapper-errors.md)   
 [Solucionar problemas de asignaciones](../core/troubleshooting-maps.md)