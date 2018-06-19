---
title: Functoids en cascada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Cascading
- Cascading functoids
ms.assetid: 03c46e7b-be1c-475e-b68b-f9d1d7732fce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5e9cfcad2432eb83c8a251147bac76b20db0bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231012"
---
# <a name="cascading-functoids"></a>Functoids en cascada
Se dice que los functoids están en cascada cuando un functoid está vinculado a otro functoid antes de estar vinculado a un registro o campo del esquema de destino. Por ejemplo, puede crear functoids en cascada en los que dos cadenas concatenadas produzcan una tercera cadena engarzada en un campo del esquema de destino.  
  
 Cuando cree functoids en cascada, puede hacer múltiples transformaciones consecutivas en la página de cuadrícula. Aunque no existe límite en el número de functoids que pueden crearse en cascada en una página, utilice esta posibilidad con prudencia. Las cascadas complejas pueden aumentar el tiempo necesario para transformar un mensaje de instancia de entrada en un mensaje de instancia de salida, lo que reduce significativamente el rendimiento en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 [Functoids en asignaciones](../core/functoids-in-maps.md)   
 [Utilizar Functoids para crear asignaciones más complejas.](../core/using-functoids-to-create-more-complex-mappings.md)