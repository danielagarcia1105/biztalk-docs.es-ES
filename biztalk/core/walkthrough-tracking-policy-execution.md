---
title: "Tutorial: Seguimiento de ejecución de la directiva en BizTalk Server | Documentos de Microsoft"
description: Tutorial para habilitar el seguimiento y ver los detalles de seguimiento de la directiva en el servidor BizTalk Server
ms.custom: 
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f1baca3a561702546ca2fae10b1c567042cd387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-tracking-policy-execution"></a>Tutorial: Ejecución de la directiva de seguimiento
Procedimientos paso a paso para habilitar el seguimiento de la **ProcessPurchaseOrder** Directiva así como para ver la información de seguimiento después de ejecutar la directiva.  
  
## <a name="prerequisites"></a>Requisitos previos  
Completar la [Tutorial: modificar la directiva](../core/walkthrough-modifying-the-policy.md) tutorial antes de llevar a cabo este tutorial.  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a>Habilitar el seguimiento de la directiva ProcessPurchaseOrder  
  
1.  Abra **administración de BizTalk Server**. Si ya está abierto, presione F5 para actualizarla.  
  
2.  Expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **RuleTestApp**.  
  
3.  Haga clic en **directivas**, seleccione **agregar**y, a continuación, seleccione **directiva**.  
  
    > [!NOTE]
    >  Para habilitar el seguimiento de una directiva, debe agregarla a una aplicación de BizTalk mediante la consola de administración de BizTalk Server.  
  
4.  En el **agregar directivas** cuadro de diálogo, expanda **ProcessPurchaseOrder**y seleccione versión **1.3**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Si no ve **ProcessPurchaseOrder** en la lista, seleccione F5 para actualizar la vista.
  
7.  Haga clic en **ProcessPurchaseOrder**y, a continuación, seleccione **de seguimiento.**  
  
8.  En el **opciones de seguimiento de la directiva** cuadro de diálogo, seleccione todas las casillas de verificación para **actividad de hechos**, **evaluación de condición**, **regla activaciones**, y **actualizaciones de Agenda**.  
  
9. Haga clic en **Aceptar**.  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a>Probar la solución y ver la información de seguimiento  
  
1.  Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.  
  
2.  Copia **SamplePO.xml** que creó en [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) al directorio de entrada para la orquestación.  
  
3.  Debería ver un archivo de salida en el directorio de salida de la orquestación. Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.  
  
4.  En **administración de BizTalk Server**, vaya a la **información general del grupo** página, haga clic en el **concentrador de grupo** ficha y, a continuación, haga clic en **instancias de servicio controladas**.  
  
5.  Haga clic en el nombre de la orquestación (RuleTest.Orchestration_1) y, a continuación, haga clic en **flujo de mensajes**.  
  
6.  Haga clic en **siga este vínculo para ver los detalles de ejecución de directiva para esta instancia de orquestación**. Asegúrese de que ve una ventana similar a la siguiente ilustración:  
  
     ![BRE &#45; Tutorial &#45; FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")  
  
7. Haga clic en el tiempo o **ProcessPurchaseOrder1.3** para ver la siguiente pantalla. En esta pantalla, puede ver el servicio (orquestación) que solicitó la ejecución de la directiva, el Id. de la orquestación, la fecha y hora de ejecución de la directiva y el Id. de la directiva.  
  
     ![BRE &#45; Tutorial &#45; PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")  
  
8. Haga clic en **actividad de hechos** para ver los hechos (datos) que se impusieron en la regla de trabajo del motor de memoria así como los hechos que se retiraron de memoria de trabajo del motor de reglas.  
  
     ![BRE &#45; Tutorial &#45; FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")  
  
9. En el **archivo** menú, haga clic en **Navigate back**.  
  
10. Haga clic en **condiciones que evalúan**. Consulte los detalles acerca de las condiciones que se han evaluado. En este caso, hay dos reglas en la directiva, y cada directiva tiene una condición. Puede ver que se han evaluado dos condiciones; como `true`, y el otro se evalúa a `false`.  
  
     ![BRE &#45; Tutorial &#45; ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")  
  
11. En el **archivo** menú, haga clic en **Navigate back**.  
  
12. Haga clic en **actualizaciones de Agenda**. Como puede ver, sólo ApprovalRule se agrega a la agenda. DeniedRule no se agrega a la agenda porque su condición se evalúa como `false`.  
  
     ![BRE &#45; Tutorial &#45; Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")  
  
13. Haga clic en **ApprovalRule** para ver la definición correspondiente.  
  
14. En el **archivo** menú, haga clic en **Navigate back**.  
  
15. En **archivo** menú, haga clic en **Navigate back** nuevo.  
  
16. Haga clic en **reglas que ha activado**. Puede ver que sólo ApprovalRule se activó (se ejecutaron acciones para ApprovalRule).  
  
17. En el **archivo** menú, haga clic en **Navigate back**.  
  
18. Haga clic en **reglas que no se han activado**. Puede ver que DeniedRule no se activó porque no estaba en la agenda.  
  
19. Repita los pasos 1-18 con **SamplePO2.xml**.  
  
## <a name="key-details"></a>Detalles de la clave  
  
-   La información de seguimiento de directiva es muy similar a la información de seguimiento que se ve en el Compositor de reglas de negocio cuando se prueba una directiva.  
  
-   Aunque el nombre de la orquestación es RuleTest.odx, el nombre que se ve es Orchestration_1, porque Nombre de tipo está establecido como Orchestration_1 para la orquestación a pesar de que se cambie su nombre. Seguimiento muestra el nombre de la orquestación con el formato \<Namespace >.\< Escriba el nombre >.  
  
-   Al eliminar una directiva de una aplicación de BizTalk con la consola de administración de BizTalk Server, ésta se elimina tanto de la aplicación como de la base de datos del motor de reglas. La directiva ya no aparecerá en el Compositor de reglas de negocio (presione F5 para actualizar la vista). Por tanto, se debe tener cuidado al eliminar una directiva de una aplicación.  
  
-   Cuando se detiene RuleTestApp y se selecciona el **detención completa** opción, la directiva ProcessPurchaseOrder (versión 1.3) se anula automáticamente la implementación.  
  
-   Si varias aplicaciones usan una directiva, cree una aplicación diferente para la directiva y, a continuación, establezca referencias a ella desde las aplicaciones cliente. Si agrega la directiva a todas las aplicaciones cliente, cuando detenga una de ellas, la implementación de la directiva se anulará y las demás aplicaciones clientes no podrán usar la directiva. Por lo tanto, se recomienda crear una aplicación diferente para las directivas que se compartan entre dos o más aplicaciones.  
  
-   Al iniciar RuleTestApp, se implementa automáticamente la directiva ProcessPurchaseOrder (versión 1.3).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha completado este tutorial, vaya a la [Tutorial: implementar la directiva](../core/walkthrough-deploying-the-policy.md) tutorial, que encontrará instrucciones paso a paso para implementar las directivas.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el seguimiento de una directiva](../core/how-to-configure-tracking-for-a-policy.md)   
 [Administración de directivas](../core/managing-policies.md)