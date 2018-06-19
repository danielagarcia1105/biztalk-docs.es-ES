---
title: Coincidencia de nodos de esquema en un mapa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e2ce880489ca49b0b55d2e6f45b9e887d719a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253940"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a>Coincidencia de nodos de esquema en una asignación
Si los esquemas de origen o destino son complejos, puede resultar difícil asignar los elementos. El asignador de BizTalk presenta la **coincidencia indicativa** característica, que le permite asignar elementos de esquema complejos sugiriendo las mejores coincidencias. Este tema proporciona información acerca de cómo realizar esta operación.  
  
> [!NOTE]
>  El Asignador de BizTalk sugiere posibles coincidencias para un nodo de esquema. Esta característica es compatible actualmente solo para nombres en inglés.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que el Asignador de BizTalk esté en ejecución.  
  
### <a name="to-match-relevant-schema-nodes"></a>Procedimiento para hacer coincidir nodos de esquemas relevantes  
  
1.  Seleccione y haga clic en el elemento de esquema para el que necesite conocer las mejores coincidencias y, a continuación, haga clic en **indicar coincidencias**. El Asignador de BizTalk destaca las mejores coincidencias (siete como máximo), con las óptimas seleccionadas.  
  
     Como alternativa, puede seleccionar **indicar coincidencias** desde el menú BizTalk o presione MAYÚS + BARRA ESPACIADORA.  
  
     En la siguiente figura se muestran coincidencias sugeridas para el nodo seleccionado en el esquema de destino.  
  
     ![Asignación sugestiva](../core/media/suggestive-mapping.gif "Suggestive_Mapping")  
  
    > [!NOTE]
    >  Mantenga presionada la tecla MAYÚS para desplazarse por las coincidencias sugeridas.  
  
2.  Ahora, puede hacer lo siguiente:  
  
    -   Presione INTRO para confirmar la coincidencia resaltada (la mejor posible).  
  
    -   Use las teclas ARRIBA/ABAJO para desplazarse por las coincidencias resaltadas por orden de preferencia.  
  
        > [!NOTE]
        >  Presione la tecla ABAJO para pasar a la coincidencia siguiente; la tecla ARRIBA resalta la mejor coincidencia anterior.  
  
    -   Presione la tecla INICIO para volver a la coincidencia superior.  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)