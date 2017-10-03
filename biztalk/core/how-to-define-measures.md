---
title: "Cómo definir medidas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56fea736baaec3f259fc8831a7256e28eaabc9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-measures"></a>Cómo definir medidas
Una medida define cómo se calcula una actividad. Al crear una vista de BAM puede definir una medida para la actividad en ella. Por ejemplo, para una actividad de pedido puede calcular la cantidad total del pedido, el número de pedidos, la cantidad promedio de los pedidos, etc.  
  
 Las medidas de BAM admitidas incluyen:  
  
-   Sum  
  
-   Count  
  
-   Promedio  
  
-   Mínima  
  
-   Máximo  
  
> [!NOTE]
>  Por el momento la característica Agregación en tiempo real (ATR) de BAM no admite las medidas Mínimo ni Máximo. Puede utilizarlas, pero cuando marque la tabla dinámica de Excel como una ATR, Mínimo y Máximo se omitirán.  
  
### <a name="to-add-new-measures"></a>Para agregar nuevas medidas  
  
1.  En el Asistente para la vista de BAM, haga clic en **siguiente** hasta que vea el **nueva vista de SAE: agregación dimensiones y medidas** página. Haga clic en **nuevas medidas**.  
  
2.  Escriba un nombre para la medida.  
  
3.  En la lista desplegable, seleccione la **elemento de datos Base**.  
  
4.  Haga clic en el **tipo de agregación** que desea usar. Las opciones incluyen:  
  
    -   Sum  
  
    -   Count  
  
    -   Promedio  
  
    -   Mínimo (no admitido para ATR).  
  
    -   Máximo (no admitido para ATR).  
  
5.  Haga clic en **Aceptar**. Cuando termine de agregar dimensiones y medidas, haga clic en **siguiente**.  
  
6.  En el **nueva vista de SAE: resumen** página, revise la información relacionada con la nueva vista y, a continuación, haga clic en **siguiente**.  
  
7.  Haga clic en **finalizar** para completar la **Asistente para vistas de BAM**.  
  
 Si agregó medidas y dimensiones a su vista de BAM, puede agregar esos elementos a la tabla dinámica en el libro de trabajo de Excel. Para obtener más información acerca de cómo crear una tabla dinámica, consulte [cómo utilizar la tabla dinámica](../core/how-to-use-the-pivottable.md).  
  
## <a name="see-also"></a>Vea también  
 [Definir dimensiones](../core/defining-dimensions.md)