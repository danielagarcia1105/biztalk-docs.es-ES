---
title: "Cómo configurar conjuntos de correlaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52bcb0216fc24e14107c7632df97671b64f2ac1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-sets"></a>Cómo configurar conjuntos de correlaciones
Para configurar un conjunto de correlaciones, puede seleccionar un tipo de correlación existente, crear un tipo de correlación nuevo o modificar un tipo de correlación existente.  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>Para asignar un tipo de correlación a un conjunto de correlaciones  
  
-   Seleccione un tipo de correlación existente.  
  
     \-O bien -  
  
     Haga clic en el nuevo tipo de correlación y seleccione **configurar las propiedades de correlación**.  
  
     \-O bien -  
  
     Haga clic en el botón de puntos suspensivos (**...** ) situado en **correlación** propiedades en el **propiedades** ventana.  
  
     El **propiedades de correlación** aparece el cuadro de diálogo. Agregue las propiedades que desee incluir en el conjunto de correlaciones. Si todavía no había ningún tipo de correlación asignado al conjunto de correlaciones, se creará un tipo de correlación nuevo.  
  
 Si ya existe un tipo de correlación para el conjunto de correlaciones, y agregar o quitar propiedades con el **propiedades de correlación** cuadro de diálogo, la correlación existente tipo que se va a modificar.  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>Para asociar actividades de envío y recepción a un conjunto de correlaciones  
  
1.  Expanda el **conjunto de correlaciones** nodo.  
  
2.  Seleccione una actividad de envío o recepción en la lista desplegable.  
  
     \-O bien -  
  
     Seleccione el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada uno **Enviar** o **recepción** forma que desee asociar con el conjunto de correlaciones.  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>Para anular la asociación de actividades de envío y recepción a un conjunto de correlaciones  
  
-   En el **Vista orquestación** ventana, expanda el nodo de conjunto de correlaciones si es necesario, haga clic en la actividad que desea quitar y, a continuación, haga clic en **eliminar**.  
  
     \-O bien -  
  
     Desactive el conjunto de correlaciones el **Inicializando conjuntos de correlaciones** propiedad o el **siguiendo conjuntos de correlaciones** propiedad en el **propiedades** ventana para cada  **Enviar** o **recepción** forma que desee desasociar el conjunto de correlaciones.  
  
## <a name="see-also"></a>Vea también  
 [Uso de filtros con la forma de mensaje de recepción](../core/using-filters-with-the-receive-message-shape.md)   
 [Usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md)