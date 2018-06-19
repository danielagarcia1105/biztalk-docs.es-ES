---
title: 'Paso 4: Crear el mapa | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fcbce54a488cb687ad0fb2c7a1931243c8cd882
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973986"
---
# <a name="step-4-create-the-map"></a>Paso 4: Crear la asignación
![Paso 4 de 5](../core/media/step-4of5.gif "Step_4of5")  
  
 **Tiempo en completarse:** 6 minutos  
  
 **Objetivo:** en este paso, se creará una asignación que transforma el mensaje de solicitud en un mensaje RequestDecline.  
  
 **Propósito:** la asignación garantiza que el número de Id. de solicitud y el total general se incluyen en el mensaje de rechazo de solicitud devuelve al sistema de inventario de almacén. El Asignador de BizTalk se emplea para vincular los campos de un mensaje entrante a los campos definidos en el mensaje saliente. Este proceso resulta necesario porque los dos mensajes no tienen la misma estructura de esquema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [paso 2: crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) y [paso 3: crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md).  
  
## <a name="procedures"></a>Procedimientos  
 La asignación depende del esquema de solicitud y del esquema RequestDecline.  Debe compilar el proyecto con el esquema antes de poder utilizarlo en una asignación.  
  
#### <a name="to-compile-the-eaischemas-project"></a>Para compilar el proyecto EAISchemas  
  
-   En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **generar**.  
  
#### <a name="to-create-the-map"></a>Para crear la asignación  
  
1.  En el Explorador de soluciones, haga clic en el **EAISchemas** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento - EAISchemas** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Plantillas instaladas**|Haga clic en **archivos de asignación**y, a continuación, haga clic en **mapa**.|  
    |**Nombre**|Tipo de **MapToReqDecline.btm**.|  
  
3.  Haga clic en **Agregar**.  
  
     La siguiente ilustración muestra el Esquema de origen, el Esquema de destino y la Cuadrícula del Asignador.  
  
     ![Mapa MapToReqDenied](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")  
  
4.  En el **esquema de origen** panel, haga clic en **Abrir esquema de origen**.  
  
5.  En el **selector de tipos de BizTalk** cuadro de diálogo, expanda **EAISchemas**, expanda **esquemas**, haga clic en **EAISchemas.Request**y, a continuación, haga clic en  **Aceptar**.  
  
6.  En el **esquema de origen** panel, haga clic en  **\<esquema\>** y, a continuación, haga clic en **Expandir nodo de árbol**.  
  
7.  En el **esquema de destino** panel, haga clic en **Abrir esquema de destino**.  
  
8.  En el **selector de tipos de BizTalk** cuadro de diálogo, expanda **EAISchemas**, expanda **esquemas**, haga clic en **EAISchemas.RequestDecline**y, a continuación, Haga clic en **Aceptar**.  
  
9. En el **esquema de destino** panel, haga clic en  **\<esquema\>** y, a continuación, haga clic en **Expandir nodo de árbol**.  
  
10. En el **esquema de origen** , arrastre el **ReqID** campo a la **ReqID** en el **esquema de destino** panel. Aparece una línea que conecta los dos elementos.  
  
11. En el **esquema de origen** , arrastre el **GrandTotal** campo a la **GrandTotal** campo el **esquema de destino** panel para asignar los datos de un esquema a otro.  
  
12. En el **archivo** menú, haga clic en **guardar todo** para guardar su trabajo.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, creó una asignación que transforma el mensaje de solicitud en un mensaje RequestDecline.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Generar el proyecto EAISchemas.  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md)   
 [Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md)   
 [Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md)   
 [Paso 4: Crear el mapa](../core/step-4-create-the-map.md)   
 [Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md)   
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)