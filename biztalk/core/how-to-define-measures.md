---
title: Cómo definir medidas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 536ed57c16d135153765ad1f0d8b3a208106b8b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004125"
---
# <a name="how-to-define-measures"></a>Cómo definir medidas
Una medida define cómo se calcula una actividad. Al crear una vista de BAM puede definir una medida para la actividad en ella. Por ejemplo, para una actividad de pedido puede calcular la cantidad total del pedido, el número de pedidos, la cantidad promedio de los pedidos, etc.  
  
 Las medidas de BAM admitidas incluyen:  
  
-   SUM  
  
-   Count  
  
-   Promedio  
  
-   Mínima  
  
-   Máximo  
  
> [!NOTE]
>  Por el momento la característica Agregación en tiempo real (ATR) de BAM no admite las medidas Mínimo ni Máximo. Puede utilizarlas, pero cuando marque la tabla dinámica de Excel como una ATR, Mínimo y Máximo se omitirán.  
  
### <a name="to-add-new-measures"></a>Para agregar nuevas medidas  
  
1. En el Asistente para la vista de BAM, haga clic en **siguiente** hasta que vea el **nueva vista de BAM: agregación de dimensiones y medidas** página. Haga clic en **nuevas medidas**.  
  
2. Escriba un nombre para la medida.  
  
3. En la lista desplegable, seleccione el **elemento de datos Base**.  
  
4. Haga clic en el **tipo de agregación** que desea usar. Las opciones incluyen:  
  
   -   SUM  
  
   -   Count  
  
   -   Promedio  
  
   -   Mínimo (no admitido para ATR).  
  
   -   Máximo (no admitido para ATR).  
  
5. Haga clic en **Aceptar**. Cuando termine de agregar dimensiones y medidas, haga clic en **siguiente**.  
  
6. En el **nueva vista de SAE: resumen** , revise la información relacionada con la nueva vista y, a continuación, haga clic en **siguiente**.  
  
7. Haga clic en **finalizar** para completar la **Asistente para vistas de BAM**.  
  
   Si agregó medidas y dimensiones a su vista de BAM, puede agregar esos elementos a la tabla dinámica en el libro de trabajo de Excel. Para obtener más información acerca de cómo crear una tabla dinámica, consulte [cómo usar la tabla dinámica](../core/how-to-use-the-pivottable.md).  
  
## <a name="see-also"></a>Vea también  
 [Definir dimensiones](../core/defining-dimensions.md)