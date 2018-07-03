---
title: Cómo agregar Functoids de copia masiva a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cff63fc-8f34-4bd0-8501-a8401bde6349
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52d79dc07c884d284fe4f6985453b86bb91b0660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022146"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a>Cómo agregar functoids de copia masiva a una asignación
El **copia masiva** functoid permite que las asignaciones usen esquemas que incluyen **cualquier** y **anyAttribute** elementos. Estos elementos son, fundamentalmente, caracteres comodín proporcionados en el lenguaje de definición de esquemas XML para coincidir con estructuras o conjuntos de atributos desconocidos.  
  
 Para obtener información conceptual sobre la **copia masiva** functoid, consulte [Functoid de copia masiva](../core/mass-copy-functoid.md).  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de copia masiva a una asignación y configurarlo  
  
1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  
  
    Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2. Arrastre el **copia masiva** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.  
  
   > [!NOTE]
   >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3. Para establecer el parámetro de entrada para el **copia masiva** functoid, crear un vínculo de entrada arrastrando un registro desde el esquema de origen el **copia masiva** functoid, o bien arrastrando el **copia masiva** functoid a un registro en el esquema de origen.  
  
4. Para utilizar el parámetro de salida desde el **copia masiva** functoid, crear un vínculo de salida arrastrando el **copia masiva** functoid a un registro en el esquema de destino o arrastrando un registro en el esquema de destino el **copia masiva** functoid.  
  
   > [!NOTE]
   >  A diferencia de otros functoids, no se puede usar la salida de la **copia masiva** functoid como entrada para otro functoid.  
  
> [!NOTE]
>  Puede insertar y configurar el **copia masiva** functoid al vincular dos registros directamente. Para obtener más información, vea la sección "para vincular mediante un functoid de copia masiva" en [cómo vincular registros automáticamente](../core/how-to-link-records-automatically.md).  
  
## <a name="see-also"></a>Vea también  
 [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)