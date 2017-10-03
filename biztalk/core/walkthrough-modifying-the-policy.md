---
title: 'Tutorial: Modificar la directiva | Documentos de Microsoft'
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd74440-2a45-4a1a-8e36-98796e1e1392
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7292d541adaf0ae2242d1c504f1a845dde66f5dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-modifying-the-policy"></a>Tutorial: Modificar la directiva
Este tutorial proporciona instrucciones paso a paso para crear una nueva versión de la **POVocabulary**, crear una nueva versión de la **ProcessPurchaseOrder** directiva y utilizar la versión más reciente de la **POVocabulary** en la nueva versión de la **ProcessPurchaseOrder** directiva.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe completar la [Tutorial: agregar una regla a la directiva](../core/walkthrough-adding-a-rule-to-the-policy.md) tutorial antes de llevar a cabo este tutorial.  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene tres procedimientos, tal y como se muestra en la tabla siguiente.  
  
|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para modificar el vocabulario POVocabulary|Proporciona instrucciones paso a paso para crear una nueva versión de vocabulario para modificar el valor de **número máximo de elementos permitidos** de **500** a **1000**.|  
|Para modificar la directiva ProcessPurchaseOrder con objeto de usar el vocabulario actualizado|Proporciona instrucciones paso a paso para crear una nueva versión de la **ProcessPurchaseOrder** directiva que se utilizará la nueva versión de **POVocabulary**.|  
|Para probar la solución|Proporciona instrucciones detalladas para probar la solución y comprobar que la nueva directiva está activa.|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a>Para modificar el vocabulario POVocabulary  
  
1.  En el **iniciar** menú Abrir **Compositor de reglas de negocios**. Si tiene el Compositor de reglas de negocio ya abrir, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de hechos, expanda **vocabularios**y, a continuación, expanda **POVocabulary**.  
  
3.  Haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **copia**.  
  
4.  Haga clic en **POVocabulary**y, a continuación, haga clic en **Pegar versión de vocabulario**.  
  
5.  Haga doble clic en **máximo número de elementos permitidos** en **versión 1.1 (sin guardar)** para iniciar el Asistente para definición de vocabulario.  
  
6.  Haga clic en **Siguiente**.  
  
7.  Haga clic en **Siguiente**.  
  
8.  Cambie el valor de **500** a **1000**.  
  
9. Haga clic en **Finalizar**.  
  
10. Haga clic en **versión 1.1 (sin guardar)**y, a continuación, haga clic en **guardar**.  
  
11. Haga clic en **versión 1.1**y, a continuación, haga clic en **publicar**.  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a>Para modificar la directiva ProcessPurchaseOrder con objeto de usar el vocabulario actualizado  
  
1.  En el Explorador de directivas, expanda **directivas**y, a continuación, expanda **ProcessPurchaseOrder**.  
  
2.  Haga clic en **versión 1.2**y, a continuación, haga clic en **copia**.  
  
3.  Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **PastePolicyVersion**.  
  
4.  Haga clic en **ApprovalRule** en **versión 1.3 (sin guardar)**.  
  
5.  En el Explorador de hechos, expanda **vocabularios**, expanda **POVocabulary**y, a continuación, expanda **versión 1.1 - publicados**.  
  
6.  Arrastre **máximo número de elementos permitidos** en **versión 1.1 - publicados** para reemplazar **máximo número de elementos permitidos** de la versión 1.0 en el panel si.  
  
7.  Repita los pasos del 4 al 6 con **DeniedRule**.  
  
8.  Haga clic en **versión 1.3 (sin guardar)**y, a continuación, haga clic en **guardar**.  
  
9. Haga clic en **versión 1.3**y, a continuación, haga clic en **publicar**.  
  
10. Haga clic en **versión 1.3**y, a continuación, haga clic en **implementar**.  
  
### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  Haga clic en **iniciar**, abra **administración de BizTalk Server**. Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.  
  
2.  Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**. Si **iniciar** está deshabilitado, la aplicación ya se está ejecutando y puede omitir el paso siguiente.  
  
3.  Haga clic en **iniciar**.  
  
4.  Copia la **SamplePO2.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.  
  
5.  Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output. Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.  
  
    > [!NOTE]
    >  El valor de la **cantidad** campo de SamplePO2.xml es 700. La versión 1.3 de la **ProcessPurchaseOrder** directiva compara este valor con 1000 en vez de compararlo con 500, tal y como se hacía la versión 1.2.  
  
## <a name="comments"></a>Comentarios  
  
-   Una directiva publicada no se puede modificar. Para modificarla, hay que crear una nueva versión de la directiva. Del mismo modo, un vocabulario publicado tampoco se puede modificar. Para modificarlo, hay que crear una nueva versión del vocabulario.  
  
-   La orquestación que invoca una directiva mediante el uso de la **reglas de llamada** forma usa la última versión implementada de la directiva. Por ejemplo, si tiene implementadas las versiones 1.0, 1.1, 1.2 y 1.3 de la directiva, la orquestación usa la versión 1.3. Si no está implementada la versión 1.3 y sí lo está la 1.2, la orquestación usará esta última. Por lo tanto, si desea usar la versión 1.2, tan sólo necesita anular la implementación de la versión 1.3 y asegurarse de que la versión 1.2 está implementada.  
  
-   Para utilizar una versión específica de una directiva desde una orquestación, debe usar un **expresión** forma e invocar el motor de reglas para ejecutar la directiva mediante programación utilizando la **Policy.Execute** método.  
  
-   Observe que la versión 1.3 de la directiva usa las definiciones de vocabulario tanto de la versión 1.0 como de la versión 1.1 del vocabulario POVocabulary. Si exporta la versión 1.3 de la directiva a un archivo XML y lo importa para crear la directiva en un equipo diferente, el proceso de importación busca ambas versiones del vocabulario. Por lo tanto, necesitará exportar tanto la versión 1.0 como la 1.1 del vocabulario e importarlas antes de importar la versión 1.3 de la directiva.  
  
-   Después de implementar una versión más actual de la directiva, debe esperar aproximadamente 60 segundos antes de probar la solución. El servicio de actualización del motor de reglas busca actualizaciones de directivas cada 60 segundos de forma predeterminada. Si existieran, actualiza la caché con la nueva información.  
  
## <a name="next-steps"></a>Pasos siguientes  
  
-   Ahora que ha completado este tutorial, realice la [Tutorial: ejecución de la directiva de seguimiento](../core/walkthrough-tracking-policy-execution.md) tutorial, que encontrará instrucciones paso a paso para realizar el seguimiento de los detalles de ejecución de directiva.