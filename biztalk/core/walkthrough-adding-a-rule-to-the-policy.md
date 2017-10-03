---
title: 'Tutorial: Agregar una regla a la directiva | Documentos de Microsoft'
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2a682c0-a5d7-4550-924d-be9fa29b84d2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343dc2e9c7965ffb27a806d18944da99777dd3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a>Tutorial: Agregar una regla a la directiva
Este tutorial proporciona procedimientos paso a paso para agregar una regla denominada **DeniedRule** a la **ProcessPurchaseOrder** directiva.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe completar la [Tutorial: crear y usar un vocabulario en la directiva](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) tutorial antes de llevar a cabo este tutorial.  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene tres procedimientos, tal y como se muestra en la tabla siguiente.  
  
|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para agregar DeniedRule a la directiva ProcessPurchaseOrder|Proporciona instrucciones paso a paso para agregar una regla nueva denominada **DeniedRule** a la **ProcessPurchaseOrder** directiva. El **DeniedRule** regla establece el valor de la **estado** campo **denegado** si el valor de la **cantidad** es mayor que 500.|  
|Para realizar pruebas con el Compositor de reglas de negocios|Proporciona instrucciones paso a paso para probar el **ProcessPurchaseOrder** directiva usando el Compositor de reglas de negocios.|  
|Para probar la solución|Proporciona instrucciones paso a paso para probar la solución.|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a>Para agregar DeniedRule a la directiva ProcessPurchaseOrder  
  
1.  En el **iniciar** menú Abrir **Compositor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.1**y, a continuación, haga clic en **copiar**.  
  
3.  Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **Pegar versión de directiva**.  
  
4.  Haga clic en **versión 1.2 (sin guardar)**, haga clic en **agregar nueva regla**y, a continuación, cambie el nombre de la regla a **DeniedRule**.  
  
5.  Si olvidó cambiar el nombre de la regla a **DeniedRule** en el paso 4, haga clic en **Rule1**y cambie el nombre a **DeniedRule** en la ventana Propiedades.  
  
6.  En el panel si, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **mayor que**.  
  
7.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.  
  
8.  Expanda **vocabularios**, expanda **POVocabulary**, expanda **versión 1.0 - publicada**y, a continuación, arrastre **cantidad de solicitud** para **argumento1** en el panel si.  
  
9. Arrastre **número máximo de elementos permitidos** a **argumento2** en el panel si.  
  
10. Arrastre **estado de la solicitud** al panel entonces.  
  
11. Haga clic en  **\<una cadena vacía >** y, a continuación, escriba **denegado**.  
  
12. Haga clic en **versión 1.2 (sin guardar)**y, a continuación, haga clic en **guardar**.  
  
13. Haga clic en **versión 1.2**y, a continuación, haga clic en **publicar**.  
  
14. Haga clic en **versión 1.2**y, a continuación, haga clic en **implementar**.  
  
### <a name="to-test-with-business-rule-composer"></a>Para realizar pruebas con el Compositor de reglas de negocios  
  
1.  Abra los archivos SamplePO.xml y SamplePO2.xml en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.2**y, a continuación, haga clic en **probar directiva**.  
  
3.  En el **XMLDocuments** nodo, seleccione **RuleTest.PO**y, a continuación, haga clic en **Agregar instancia**.  
  
4.  Seleccione **SamplePO.xml**y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en **prueba**.  
  
6.  Mire el **actualización de Agenda** sección en la salida y observe que sólo **ApprovalRule** se agrega a la agenda. Por tanto, es la única regla que se activa (se ejecutan las acciones asociadas a la regla).  
  
7.  Abra **SamplePO.xml** en el Bloc de notas y observe que el valor de la **estado** campo está establecido en **aprobado**.  
  
8.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.2**y, a continuación, haga clic en **probar directiva.**  
  
9. Seleccione **SamplePO.xml**, haga clic en **quitar instancia**y, a continuación, haga clic en **Agregar instancia**.  
  
10. Seleccione **SamplePO2.xml**y, a continuación, haga clic en **abiertos**.  
  
11. Haga clic en **prueba**.  
  
12. Mire el **actualización de Agenda** sección en la salida y observe que sólo **DeniedRule** se agrega a la agenda. Por tanto, es la única regla que se activa.  
  
13. Abra **SamplePO2.xml** en el Bloc de notas y observe que el valor de la **estado** campo es **denegado**.  
  
### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.  
  
2.  Copia la **SamplePO.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.  
  
3.  Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output para la orquestación. Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.  
  
4.  Repita los pasos 2 y 3 con **SamplePO2.xml**y observe que el valor de la **estado** campo está establecido en **denegado** en el documento de salida. Esto demuestra que la orquestación está usando la versión 1.2 de la **ProcessPurchaseOrder** directiva. La orquestación utiliza la última versión implementada de la **ProcessPurchaseOrder** directiva, que es **1.2**. No es necesario anular la implementación de la versión 1.1 de la directiva para usar la versión 1.2 de la directiva. Sin embargo, es necesario esperar aproximadamente 60 segundos antes de probar la solución. Para obtener más información, vea la sección Comentarios.  
  
## <a name="comments"></a>Comentarios  
  
-   Una directiva puede tener una o varias reglas. No hay un límite lógico en el número de reglas de una directiva.  
  
-   El motor de reglas usa un algoritmo de Evaluación de condición – Resolución de conflictos – Ejecución de acciones. En el **evaluación de condición** fase, el motor de reglas evalúa condiciones en todas las reglas. Las reglas cuyas condiciones se evalúen como true, se convierten en reglas candidatas para la ejecución. En el **la resolución de conflictos** fase, las reglas candidatas se agregan a la agenda en el orden de prioridad de la regla. En el **ejecución de acciones** fase, las acciones en el candidato que se ejecutan las reglas. Si las reglas candidatas tienen la misma prioridad, no hay un orden determinista en el que ejecutar las acciones para dichas reglas. Debe asumir que se ejecutan en paralelo.  
  
-   En este escenario, sólo se activa una de las reglas para cualquier archivo de ejemplo dado. Asegúrese de que cambia el valor de la **estado** campo antes de ejecutar una prueba.  
  
-   Cuando se implementa una nueva versión de la directiva, debe esperar aproximadamente 60 segundos antes de realizar la prueba. El servicio de actualización del motor de reglas efectúa un sondeo en la base de datos del motor de reglas de forma periódica (cada 60 segundos de forma predeterminada) para buscar las directivas implementadas recientemente. El servicio de actualización del motor de reglas actualiza el objeto de directiva en la memoria con la información acerca de la versión de la última directiva implementada en la base de datos del motor de reglas.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha completado este tutorial, realice la [Tutorial: modificar la directiva](../core/walkthrough-modifying-the-policy.md) tutorial, que encontrará instrucciones paso a paso para modificar la directiva para aprobar los pedidos de compra con el valor de **cantidad** menor o igual que 1000 (en lugar de 500).  
  
## <a name="see-also"></a>Vea también  
 [Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md)   
 [Agenda y prioridad](../core/agenda-and-priority.md)