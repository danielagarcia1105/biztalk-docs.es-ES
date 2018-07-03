---
title: Cómo configurar conjuntos de correlaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, send activities
- correlation sets, assigning correlation types
- correlation types, correlation sets
- correlation sets, receive activities
- configuring, correlation sets
- correlation sets, configuring
- correlation types, assigning
ms.assetid: 060bf2ba-c173-4dca-a8c4-4c5341e5ceaa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c56d7f319023bb0379050452253c65634929c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968861"
---
# <a name="how-to-configure-correlation-sets"></a>Cómo configurar conjuntos de correlaciones
Para configurar un conjunto de correlaciones, puede seleccionar un tipo de correlación existente, crear un tipo de correlación nuevo o modificar un tipo de correlación existente.  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>Para asignar un tipo de correlación a un conjunto de correlaciones  
  
- Seleccione un tipo de correlación existente.  
  
   \- O bien  
  
   Haga clic en el nuevo tipo de correlación y seleccione **configurar las propiedades de correlación**.  
  
   \- O bien  
  
   Haga clic en el botón de puntos suspensivos (**...** ) situado en **correlación** propiedades en el **propiedades** ventana.  
  
   El **las propiedades de correlación** aparezca el cuadro de diálogo. Agregue las propiedades que desee incluir en el conjunto de correlaciones. Si todavía no había ningún tipo de correlación asignado al conjunto de correlaciones, se creará un tipo de correlación nuevo.  
  
  Si ya existe un tipo de correlación para el conjunto de correlaciones y agregar o quitar propiedades con el **las propiedades de correlación** cuadro de diálogo, la correlación existente se modificará el tipo.  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>Para asociar actividades de envío y recepción a un conjunto de correlaciones  
  
1.  Expanda el **conjunto de correlaciones** nodo.  
  
2.  Seleccione una actividad de envío o recepción en la lista desplegable.  
  
     \- O bien  
  
     Seleccione el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada uno **Enviar** o **recepción** forma que desee asociar con el conjunto de correlaciones.  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>Para anular la asociación de actividades de envío y recepción a un conjunto de correlaciones  
  
-   En el **Vista orquestación** ventana, expanda el nodo de conjunto de correlaciones si es necesario, haga clic en la actividad que desea quitar y, a continuación, haga clic en **eliminar**.  
  
     \- O bien  
  
     Desactive el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada  **Enviar** o **recepción** forma que desee desasociar del conjunto de correlaciones.  
  
## <a name="see-also"></a>Vea también  
 [Uso de filtros con la forma recibir mensaje](../core/using-filters-with-the-receive-message-shape.md)   
 [Uso de correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md)