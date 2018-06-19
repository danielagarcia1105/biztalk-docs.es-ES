---
title: Las rutas de acceso de bucle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, paths
- maps, conditional looping
ms.assetid: 4612dc2d-2c39-427d-88ac-65f9e85873c7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69e7d1c092ee5ca34b8c2ef3f309eff6c44b271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262156"
---
# <a name="loop-paths"></a>Rutas de bucle
Un elemento en un esquema está en bucle si su propiedad Max Occurs es mayor que 1. Una ruta de acceso de bucle se produce cuando se dibuja un vínculo entre un elemento de bucle del esquema de origen y un elemento de bucle del esquema de destino.  
  
## <a name="configuring-a-loop-path"></a>Configurar una ruta de bucle  
 El asignador de BizTalk controla automáticamente los registros de bucle cuando se crea una ruta de acceso de bucle.  
  
 Puede configurar una ruta de bucle en una asignación vinculando un campo de un registro de bucle del esquema de origen con un campo de un registro de bucle del esquema de destino. La ilustración siguiente muestra una asignación que copia solo registros de encuestas de comida a una lista de direcciones maestra.  
  
 ![Mapa que ilustra el uso de una ruta de acceso de bucle. ] (../core/media/correct-loop-path-map.gif "correct_loop_path_map")  
Asignación de ruta de acceso  
  
## <a name="multiple-loop-paths"></a>Varias rutas de bucle  
 En una asignación se produce una ruta de bucle múltiple al vincular campos incluidos en dos o más registros de bucle con campos incluidos en un registro de bucle simple. En la siguiente ilustración se muestra cómo se intentan combinar direcciones recopiladas de dos encuestas diferentes en una única lista de direcciones maestra.  
  
 ![Asignación con varias rutas de bucle](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")  
Asignación con varias rutas de bucle (incorrecto)  
  
 Esta asignación no producirá los resultados esperados. Cuando el Asignador encuentra varias rutas de bucle durante la compilación, genera una advertencia y selecciona la primera ruta de bucle de forma predeterminada. Para combinar las dos direcciones diferentes en una lista de direcciones maestra única, utilice un **bucle** functoid tal como se muestra en la asignación siguiente.  
  
 ![Mapa que ilustra el uso del functoid de bucle. ] (../core/media/loopingfunctoid.gif "loopingfunctoid")  
Asignación con functoid de bucle (correcto)  
  
 El **bucle** functoid debe usarse en lugar de varias rutas de bucle en los escenarios siguientes:  
  
1.  Cuándo el Asignador no genera el resultado deseado en un escenario de varias rutas de bucle.  
  
2.  Para combinar varias estructuras de repetición en un mensaje de instancia de entrada en una única estructura de repetición en el mensaje de instancia de salida.  
  
3.  Para convertir un esquema sin formato en un esquema jerárquico asignando un único registro a múltiples registros. Ésta es una operación común para convertir esquemas sin formato en catálogos de Microsoft Commerce Server.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids a una asignación de bucle](../core/how-to-add-looping-functoids-to-a-map.md)   
 [Functoid de bucle](../core/looping-functoid.md)