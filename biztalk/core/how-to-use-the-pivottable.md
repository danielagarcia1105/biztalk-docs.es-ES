---
title: Cómo utilizar la tabla dinámica | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed416f7a04392804c4c031a69940c4229eabe99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256660"
---
# <a name="how-to-use-the-pivottable"></a>Uso de la tabla dinámica
Si ha definido una vista de BAM que incluye dimensiones y medidas, debe actualizar una o más tablas dinámicas asociadas.  
  
 Un informe de tabla dinámica en Excel es una tabla interactiva que permite combinar y comparar grandes cantidades de datos fácilmente. Puede rotar los valores de sus filas y columnas para ver distintos resúmenes de los datos mostrados. Una tabla dinámica también permite realizar cálculos sobre los datos, como promedios o recuentos de agregados.  
  
 Para usar la tabla dinámica una vez que la ha creado, siga los pasos de este procedimiento. Para obtener más información sobre cómo usar tablas dinámicas, consulte la documentación de Microsoft Excel.  
  
> [!NOTE]
>  Cuando se crea una tabla dinámica de agregación en tiempo real, ésta puede contener un máximo de 14 niveles de dimensión.  
  
> [!IMPORTANT]
>  Si define varias tablas dinámicas en la hoja de cálculo de Excel, es posible que las tablas resultantes crezcan y se superpongan cuando la actividad obtenga un conjunto de datos de gran tamaño. En este caso, recibirá el mensaje "Un informe de tabla dinámica no puede superponerse a otro informe de PowerPivot" al actualizar los datos. Puede corregir este error agregando más columnas o filas entre las tablas dinámicas con el fin de permitir que las tablas aumenten su tamaño sin superponerse.  
  
### <a name="to-use-the-pivottable"></a>Procedimiento para usar la tabla dinámica  
  
1.  Cree una vista de BAM para usarla con una tabla dinámica. Para obtener más información acerca de cómo crear una vista de SAE, vea [definir una vista de actividad de negocio](../core/defining-a-bam-view.md)  
  
2.  Mediante el **lista de campos de tabla dinámica**, arrastrar y colocar dimensiones disponibles uno o más en las áreas de fila y columna de la plantilla de tabla dinámica.  
  
3.  Mediante el **lista de campos de tabla dinámica**, arrastrar y colocar uno o más medidas disponibles en el área de elementos de datos de la plantilla de tabla dinámica.  
  
     A medida que actualice la tabla, observará que se rellena con datos de ejemplo. Esto le ayudará a decidir cómo configurarla.  
  
4.  Mediante el **tabla dinámica** barra de herramientas, asociar un gráfico a la tabla dinámica.  
  
5.  Guarde el libro de Excel.