---
title: 'Tutorial: Crear y utilizar un vocabulario en la directiva | Documentos de Microsoft'
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c306a6e-3384-4f43-9c75-c5407cd9aed2
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb64a0548fefb816e1975e4c858934fc3dceb7c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-creating-and-using-a-vocabulary-in-the-policy"></a>Tutorial: Crear y utilizar un vocabulario en la directiva
Este tutorial proporciona procedimientos paso a paso para crear un vocabulario y usarlo en el **ProcessPurchaseOrder** directiva.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe completar la [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de llevar a cabo este tutorial. Sin embargo, se recomienda realizar previamente todos los tutoriales que aparecen enumerados antes de éste en la documentación.  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene tres procedimientos, tal y como se muestra en la tabla siguiente.  
  
|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para crear el vocabulario POVocabulary|Proporciona instrucciones paso a paso para crear la **POVocabulary** vocabulario con tres definiciones: cantidad solicitada, el máximo número de elementos permitidos y el estado de la solicitud.|  
|Para usar el POVocabulary en la directiva ProcessPurchaseOrder|Proporciona instrucciones paso a paso para crear una nueva versión de la **ProcessPurchaseOrder** directiva con **POVocabulary**.|  
|Para probar la solución|Proporciona instrucciones paso a paso para probar la solución.|  
  
### <a name="to-create-the-povocabulary-vocabulary"></a>Para crear el vocabulario POVocabulary  
  
1.  En el **iniciar** menú Abrir **Compositor de reglas de negocios**. Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.  
  
3.  Haga clic en **vocabularios**, haga clic en **Agregar nuevo vocabulario**y, a continuación, escriba **POVocabulary** como el nombre para el vocabulario.  
  
4.  Si no cambió el nombre del vocabulario a POVocabulary en el paso 3, cambie el nombre del vocabulario a **POVocabulary**en la ventana Propiedades.  
  
5.  Haga clic en **versión 1.0 (sin guardar)** en **POVocabulary**y, a continuación, haga clic en **agregar nueva definición**.  
  
6.  En el Asistente para definición de vocabulario, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.  
  
7.  Para el **nombre de definición de**, tipo **cantidad solicitada**.  
  
8.  Haga clic en **examinar**y seleccione el **PO.xsd** de archivos que ha creado en [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md).  
  
9. En el **Seleccionar enlace** cuadro de diálogo, expanda **PurchaseOrder**, expanda **elemento**y, a continuación, haga doble clic en **cantidad**.  
  
10. Asegúrese de que el **tipo de documento** está establecido en **RuleTest.PO**. Si no es así, cambie el tipo de documento a RuleTest.PO. Este paso es muy importante.  
  
     ![BRE &#45; Tutorial &#45; ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")  
  
11. Especifique el **Seleccionar operación** en el **Seleccionar operación** grupo como **realizar la operación Get**.  
  
     ![BRE &#45; Tutorial &#45; SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")  
  
12. Haga clic en **Finalizar**.  
  
13. Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva definición**.  
  
14. Seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.  
  
15. Para el **nombre de definición de**, tipo **estado de la solicitud**.  
  
16. Haga clic en **examinar**y seleccione el **PO.xsd** archivo.  
  
17. En el **Seleccionar enlace** cuadro de diálogo, expanda **PurchaseOrder**y, a continuación, haga doble clic en **estado**.  
  
18. Cambiar el **tipo de documento** a **RuleTest.PO**. Este paso es muy importante.  
  
19. Asegúrese de que el **operación realizar Set** opción está seleccionada y, a continuación, haga clic en **siguiente.**  
  
20. Haga clic en **Finalizar**.  
  
21. Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva definición**.  
  
22. Asegúrese de que **valor constante, rango de valores o conjunto de valores** está seleccionada y, a continuación, haga clic en **siguiente**.  
  
23. Para el **nombre de definición de**, tipo **máximo número de elementos permitidos**.  
  
24. Asegúrese de que **tipo de definición de valor constante** está seleccionada y, a continuación, haga clic en **siguiente**.  
  
25. Tipo de **500** para el valor y, a continuación, haga clic en **finalizar**.  
  
26. Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **guardar**.  
  
27. Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **publicar**.  
  
### <a name="to-use-the-povocabulary-in-the-processpurchaseorder-policy"></a>Para usar el POVocabulary en la directiva ProcessPurchaseOrder  
  
1.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **copiar**.  
  
2.  Haga clic en **ProcessPurchaseOrder** y, a continuación, haga clic en **Pegar versión de directiva**.  
  
3.  Haga clic en **ApprovalRule** en **versión 1.1 (sin guardar)**.  
  
4.  En la ventana Explorador de hechos, expanda **vocabularios**, expanda **POVocabulary**, expanda **versión 1.0**y, a continuación, arrastre **cantidad solicitada**al panel si para sustituir la parte izquierda (LHS) argumento del predicado LessThanOrEqual.  
  
     ![BRE &#45; Tutorial &#45; DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")  
  
     ![BRE &#45; Tutorial &#45; ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")  
  
5.  Arrastre **máximo número de elementos permitidos** para reemplazar el derecho (RHS) argumento de la condición (**500**).  
  
6.  Seleccione la acción existente en el panel, a continuación, menú contextual y, a continuación, haga clic en **Eliminar acción**.  
  
    > [!NOTE]
    >  También puede presionar SUPRIMIR después de seleccionar la acción que va a eliminar.  
  
7.  Arrastre **estado de la solicitud** a la **, a continuación,** panel.  
  
8.  Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **aprobado**.  
  
9. Haga clic en **versión 1.1 (sin guardar)** en la ventana Explorador de directivas y, a continuación, haga clic en **guardar**.  
  
10. Haga clic en **versión 1.1 (sin guardar)** en la ventana Explorador de directivas y, a continuación, haga clic en **publicar**.  
  
### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  En el Compositor de reglas de negocio, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0 - implementada**y, a continuación, haga clic en **Undeploy**.  
  
    > [!NOTE]
    >  Este paso es opcional porque la orquestación siempre toma la última versión implementada de la directiva, que es la 1.1 después de realizar el paso 2.  
  
2.  Haga clic en **versión 1.1 - publicada**y, a continuación, haga clic en **implementar**.  
  
3.  Espere aproximadamente **60** segundos. El servicio de actualización del motor de reglas actualiza su caché cada 60 segundos si hay actualizaciones en una directiva que almacena. No importa si ha realizado o no el paso 1 porque la orquestación toma la última versión implementada de la directiva, que es la 1.1.  
  
4.  Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.  
  
5.  Copia la **SamplePO.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.  
  
6.  Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output para la orquestación. Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.  
  
7.  Repita los pasos 5 y 6 con **SamplePO2.xml**y observe que el valor de la **estado** campo en el documento de salida es el mismo que el documento de entrada (**XYZ**).  
  
    > [!NOTE]
    >  El valor de la **estado** campo sigue siendo el mismo (XYZ) porque el motor de reglas no ejecuta la acción en el **ApprovalRule** regla porque la condición se evaluó como `false`.  
  
## <a name="comments"></a>Comentarios  
  
-   Después de guardar el vocabulario, puede modificarla. En cambio, después de publicarlo, no puede modificar el vocabulario.  
  
-   Si necesita modificar una definición, agregar una nueva o eliminar una definición, debería crear una versión nueva del vocabulario.  
  
-   En las directivas sólo se pueden usar vocabularios publicados.  
  
-   En el procedimiento "para crear el vocabulario POVocabulary", se cambió el tipo de documento para **RuleTest.PO**. Para ver los resultados de este cambio, en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **PO.xsd**. En la ventana Propiedades, tenga en cuenta que **RuleTest** es el nombre del espacio de nombres, y **pedido** es el nombre de la **tipo**.  
  
-   En este tutorial, sólo usó un documento XML como un hecho para la directiva. También puede usar hechos .NET y hechos de la base de datos al crear directivas.  
  
-   Cuando se selecciona **realizar operación "Set"** en la segunda página del Asistente para definición de vocabulario, puede especificar un **cadena de formato de presentación** en la página siguiente. Por ejemplo, puede cambiar la cadena de formato de presentación de **estado de la solicitud {0}** a **solicitud de estado es: {0}** antes de hacer clic **finalizar** en el paso 20 de la "crear procedimiento de vocabulario".  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha completado este tutorial, realice la [Tutorial: agregar una regla a la directiva](../core/walkthrough-adding-a-rule-to-the-policy.md) tutorial, que encontrará instrucciones paso a paso para agregar una nueva regla a la **ProcessPurchaseOrder**directiva.  
  
## <a name="see-also"></a>Vea también  
 [Vocabularios](../core/vocabularies.md)   
 [Cómo desarrollar vocabularios](../core/how-to-develop-vocabularies.md)   
 [Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md)   
 [Agenda y prioridad](../core/agenda-and-priority.md)