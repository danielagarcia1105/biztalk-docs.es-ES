---
title: 'Tutorial: Invocar la directiva desde una orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33bef51b2c702e71fcf6ef0ea0c4fd63b28fbde8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976563"
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a>Tutorial: Invocar la directiva desde una orquestación
Puede invocar una directiva desde una orquestación de una de las formas siguientes:  

- Mediante el uso de la **reglas de llamada** forma  

- Mediante el uso de la **expresión** dar forma a e invocando mediante programación el motor de reglas para ejecutar la directiva (**Policy.Execute** método)  

  Mediante el **reglas de llamada** forma es la manera más común y también el método recomendado para invocar una directiva desde una orquestación. Este tutorial proporciona procedimientos paso a paso para usar el **reglas de llamada** forma para invocar el **ProcessPurchaseOrder** directiva.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe completar el [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) tutorial antes de realizar este tutorial.  

## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene siete procedimientos, tal y como se muestra en la tabla siguiente.  

|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para crear un proyecto de BizTalk con un esquema y una orquestación|Proporciona instrucciones paso a paso para crear un esquema y una orquestación que invoca la **ProcessPurchaseOrder** directiva.|  
|Procedimiento para crear variables de mensaje|Proporciona instrucciones paso a paso para crear variables de mensaje que se usan en la orquestación.|  
|Para configurar formas|Proporciona instrucciones paso a paso para configurar formas en la orquestación.|  
|Para crear puertos|Proporciona instrucciones paso a paso para crear puertos en la orquestación.|  
|Procedimiento para conectar puertos con las formas|Proporciona instrucciones paso a paso para conectar puertos con las formas.|  
|Procedimiento para generar e implementar la solución|Proporciona instrucciones paso a paso para generar e implementar la solución.|  
|Para probar la solución|Proporciona instrucciones paso a paso para probar la solución.|  

### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a>Para crear un proyecto de BizTalk con un esquema y una orquestación  

1. Iniciar **Microsoft Visual Studio**.  

2. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  

3. En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  


   |             Use              |                             Para                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **Tipos de proyecto**         |                     Haga clic en **proyectos de BizTalk**.                     |
   |           **Templates** (Plantillas [C++])           |               Haga clic en **proyecto de BizTalk Server vacío**.               |
   |             **Nombre**              |                         Tipo **RuleTest**.                          |
   |           **Ubicación**            |                  Especificar **C:\BRE-Walkthroughs**.                   |
   |         **Nombre de solución**         |                        Tipo **RuleTestSol**.                        |
   | **Crear directorio para la solución** | Seleccione esta casilla para crear un directorio para los archivos de la solución. |


4. Haga clic en **Aceptar**. El **RuleTest** proyecto debe aparecer en el Explorador de soluciones. Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.  

5. En el Explorador de soluciones, haga clic en **RuleTest**, apunte a **agregar**y, a continuación, haga clic en **elemento existente**.  

6. Busque y agregue el **PO.xsd** que creó en el archivo de esquema el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial. Visual Studio realiza una copia de la **PO.xsd** de archivo y lo agrega al proyecto.  

7. En el Explorador de soluciones, haga clic en **RuleTest**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  

8. En el **Agregar nuevo elemento** diálogo cuadro, realice lo siguiente:  


   |    Use    |            Para            |
   |----------------|----------------------------------|
   | **Categorías** |  Haga clic en **archivos de orquestación**.  |
   | **Templates** (Plantillas [C++])  | Haga clic en **orquestación de BizTalk**. |
   |    **Nombre**    |      Tipo **RuleTest.odx**.      |


9. Haga clic en **Agregar**.  

10. Haga clic en **coloca una forma desde el cuadro de herramientas aquí**, apunte a **Insertar forma**y, a continuación, haga clic en **recepción**.  

11. En la ventana Propiedades, cambie el nombre de la **recepción** dar forma a **ReceivePO**y establezca el valor de la **activar** propiedad `true`.  

12. En el cuadro de herramientas, en el **orquestaciones de BizTalk** pestaña, arrastre el **reglas de llamada** forma en una línea de conexión debajo el **recepción** forma.  

13. En la ventana Propiedades, cambie el nombre de la **reglas de llamada** dar forma a **CallProcessPOPolicy**.  

14. A continuación haga el **reglas de llamada** forma, elija **Insertar forma**y, a continuación, haga clic en **enviar**.  

15. En la ventana Propiedades, cambie el nombre de la **enviar** dar forma a **SendPO**. La orquestación tendrá aspecto de la ilustración siguiente:  

     ![BRE&#45;tutorial&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")  

### <a name="to-create-message-variables"></a>Procedimiento para crear variables de mensaje  

1.  En la ventana Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**. Si no ve la ventana Vista orquestación, haga clic en el **vista** menú, elija **Other Windows**y, a continuación, haga clic en **Vista orquestación**. Normalmente, la ventana Vista orquestación está en la ficha situada junto a la ficha Explorador de soluciones. De forma predeterminada, el nuevo mensaje se denomina **Message_1**.  

     ![BRE&#45;tutorial&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")  

2.  En la ventana Vista orquestación, haga clic en **Message_1**.  

3.  En la ventana Propiedades, haga lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Identificador**|Tipo **POInst**, y, a continuación, presione ENTRAR.|  
    |**Tipo de mensaje**|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione **RuleTest.PO**.|  

     ![BRE&#45;tutorial&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")  

### <a name="to-configure-shapes"></a>Para configurar formas  

1. Seleccione el **recepción** forma en el Diseñador de orquestaciones.  

2. En la ventana Propiedades, seleccione **POInst** para el **mensaje** propiedad.  

3. Haga doble clic en el **reglas de llamada** forma en el Diseñador de orquestaciones.  

4. En el **configuración de directiva de reglas de llamada** cuadro de diálogo, seleccione **ProcessPurchaseOrder** para la directiva.  

5. Haga clic en siguiente para **\\** <em>, a continuación ** nombre de parámetro</em><em>y seleccione **POInst</em>*  como un parámetro a la directiva.  

    ![BRE&#45;tutorial&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")  

6. Haga clic en **Aceptar**.  

7. Seleccione el **enviar** forma en la orquestación.  

8. En la ventana Propiedades, establezca el valor de la **tipo de mensaje** propiedad **POInst**.  

### <a name="to-create-ports"></a>Para crear puertos  

1.  Cree dos carpetas, **entrada** y **salida**, en la carpeta C:\BRE-Walkthroughs\RuleTestSol.  

2.  Haga clic en la superficie de puerto de la izquierda de la orquestación y, a continuación, haga clic en **nuevo puerto configurado**.  

3.  Haga clic en **Siguiente**. Tipo **ReceivePOPrt** para el nombre del puerto.  

4.  Haga clic en **siguiente** dos veces.  

5.  Seleccione **especificar ahora** para el **enlace de puerto**.  

6.  Especificar **archivo** para el **transporte**y escriba el nombre del directorio de entrada como **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** junto con la máscara de archivo (**\*.xml**) para el URI.  

7.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  

8.  Haga clic en la superficie para puerto derecha de la orquestación y, a continuación, haga clic en **nuevo puerto configurado**.  

9. Haga clic en **Siguiente**. Tipo **sendpoport como** para el nombre del puerto.  

10. Haga clic en **siguiente** dos veces.  

11. Cambiar el **dirección de puerto de comunicación** a **siempre enviaré los mensajes en este puerto**.  

12. Seleccione **especificar ahora** para el **enlace de puerto**.  

13. Especificar **archivo** para el **transporte**y escriba el nombre del directorio de salida como **C:\BRE-Walkthroughs\RuleTestSol\Output**y %MessageID%.xml como el archivo de salida nombre.  

14. Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  

### <a name="to-connect-ports-with-the-shapes"></a>Procedimiento para conectar puertos con las formas  

1.  Conectar el **ReceivePOPrt** puerto a la **ReceivePO** forma. (Arrastre la flecha situada a la derecha del puerto ReceivePOPrt sobre la superficie de puerto hasta el cuadro sobre la forma ReceivePO.)  

     ![BRE&#45;tutorial&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")  

2.  Conectar el **SendPO** dar forma a la **SendPOPrt** puerto.  

     ![BRE&#45;tutorial&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")  

### <a name="to-build-and-deploy-the-solution"></a>Procedimiento para generar e implementar la solución  

1. Iniciar **Microsoft Visual Studio**.  

2. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en el **RuleTest** del proyecto y, a continuación, haga clic en **propiedades**.  

3. En el Diseñador de proyectos (en el panel central), haga clic en **firma**.  

4. En la ficha firma, marque **firmar el ensamblado** casilla de verificación; En la lista desplegable **elegir un archivo de clave de nombre seguro**, haga clic en **New**; En el **nombre de archivo de clave** , introduzca la prueba de la regla; En el **contraseña** campo (opcional), establezca la contraseña y, a continuación, haga clic en **Aceptar**.  

5. En el Diseñador de proyectos, haga clic en **implementación** para cambiar a la pestaña implementación.  

6. Especificar **RuleTestApp** como el nombre de la aplicación.  

    ![BRE&#45;tutorial&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")  

7. Haga clic en **Aceptar**.  

8. Haga clic en el **RuleTest** del proyecto y, a continuación, haga clic en **compilar**.  

9. Haga clic en el **RuleTest** del proyecto y, a continuación, haga clic en **implementar**.  

### <a name="to-test-the-solution"></a>Para probar la solución  

1. En el Compositor de reglas de negocio, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **publicar**.  

2. Haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  

3. En el **iniciar** menú Abrir **administración de BizTalk Server**. Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.  

4. Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  

5. Haga clic en **RuleTestApp**y, a continuación, haga clic en **configurar**.  

6. Haga clic en **Orchestration_1**y especifique **BizTalkServerApplication** como el host.  

    ![BRE&#45;tutorial&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")  

7. Haga clic en **Aceptar**.  

8. Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**.  

9. En el **inicio de aplicación 'RuleTestApp'** cuadro de diálogo, haga clic en **iniciar**y, a continuación, espere hasta que la aplicación se ha iniciado correctamente.  

10. Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.  

11. Copia el **SamplePO.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.  

12. Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output para la orquestación. Abra el archivo XML de salida y observe que el valor de la **estado** campo se establece en **aprobado**.  

13. Repita los pasos 11 y 12 con **SamplePO2.xml**y tenga en cuenta que el valor de la **estado** campo en el documento de salida es igual que en el documento de entrada (**xyz**).  

## <a name="comments"></a>Comentarios  

-   En este tutorial no se han utilizado las formas del Cuadro de herramientas para agregarlas a la orquestación. En lugar de ello, ha hecho clic con el botón secundario del mouse y ha seleccionado la forma que quería insertar.  

-   La configuración de la **reglas de llamada** forma examina la última versión guardada al determinar los tipos utilizados. En tiempo de ejecución, se utilizará la última versión implementada.  

-   Si tiene previsto utilizar una versión de directiva que no sea la última versión implementada, debe usar un **expresión** forma e invocar el motor de reglas mediante programación para ejecutar la directiva de esa versión específica. Para obtener más información, consulte [cómo ejecutar directivas](../core/how-to-execute-policies.md).  

-   El **reglas de llamada** forma reconstruye el mensaje, como si utilizara un **construir mensaje** shape, que a su vez puede provocar que las propiedades de contexto del mensaje que se pierdan.  

-   Una directiva no se puede modificar tras su publicación.  

-   Las aplicaciones cliente pueden obtener acceso sólo a las directivas implementadas. Si una aplicación cliente invoca una directiva que no se ha implementado, el motor de reglas genera una **RuleEngineDeploymentNotDeployedException** excepción. Puede ver el mensaje de error detallado en el registro de eventos de la aplicación.  

## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha realizado este tutorial, realice el [Tutorial: crear y usar un vocabulario en la directiva](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) tutorial, que encontrará instrucciones paso a paso para crear un vocabulario y usarlo en el **ProcessPurchaseOrder** directiva.  

## <a name="see-also"></a>Vea también  
 [Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md)   
 [Agenda y prioridad](../core/agenda-and-priority.md)   
 [Invocación de reglas de negocio en orquestaciones](../core/invoking-business-rules-in-orchestrations.md)