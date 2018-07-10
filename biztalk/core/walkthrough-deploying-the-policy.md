---
title: 'Tutorial: Implementar la directiva | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35b7d9c3b2b7780ef87b0dedae52f58c20dc835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996301"
---
# <a name="walkthrough-deploying-the-policy"></a>Tutorial: Implementar la directiva
Este tutorial proporciona instrucciones paso a paso para implementar la **ProcessPurchaseOrder** directiva en las tres formas siguientes:  
  
-   Exportación e importación de la directiva utilizando el Asistente para implementación de motor de reglas de negocios.  
  
-   Exportar la directiva a un archivo XML e importarla desde él en la consola de administración de BizTalk Server.  
  
-   Exportar la directiva como parte de un archivo MSI e importar éste último en la consola de administración de BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe completar el [Tutorial: ejecución de la directiva de seguimiento](../core/walkthrough-tracking-policy-execution.md) tutorial antes de realizar este tutorial.  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tema contiene los tres tutoriales siguientes:  
  
1.  El primer tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva utilizando el Asistente para implementación de motor de reglas de negocios. En la tabla siguiente se describen los procedimientos de este tutorial.  
  
    |Título del procedimiento|Descripción del procedimiento|  
    |---------------------|---------------------------|  
    |Para exportar POVocabulary 1.0 y 1.1 mediante el Asistente para implementar el motor de reglas de negocios|Proporciona instrucciones paso a paso para exportar las versiones 1.0 y 1.1 de la **POVocabulary** archivos vocabulario XML utilizando el Asistente para implementación de motor de reglas de negocios.|  
    |Para exportar ProcessPurchaseOrder 1.3 mediante el Asistente para implementar el motor de reglas de negocios|Proporciona instrucciones paso a paso para exportar la versión 1.3 de la **ProcessPurchaseOrder** directiva a un archivo XML utilizando el Asistente para implementación de motor de reglas de negocios.|  
    |Para eliminar ProcessPurchaseOrder y POVocabulary|Proporciona instrucciones paso a paso para eliminar la **ProcessPurchaseOrder** directiva y **POVocabulary** vocabulario importando el archivo XML de archivos para que pueda probar para volver a crearlos.|  
    |Para importar desde XML a fin de volver a crear POVocabulary 1.0 y 1.1|Proporciona instrucciones paso a paso para importar el archivo XML de vocabulario que creó en el primer procedimiento para volver a crear la **POVocabulary** vocabulario.|  
    |Para comprobar que se han vuelto a crear POVocabulary 1.0 y 1.1|Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que las versiones 1.0 y 1.1 de **POVocabulary** se vuelven a crear.|  
    |Para importar desde XML a fin de volver a crear ProcessPurchaseOrder 1.3|Proporciona instrucciones paso a paso para importar el archivo XML de directiva que creó en el segundo procedimiento para volver a crear la versión 1.3 de la **ProcessPurchaseOrder** directiva.|  
    |Para comprobar que se ha vuelto a crear ProcessPurchaseOrder 1.3|Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que la versión 1.3 de la **ProcessPurchaseOrder** se vuelve a crear la directiva.|  
  
2.  El segundo tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva mediante el uso de un archivo XML exportado desde la consola de administración de BizTalk Server la siguiente tabla describen los procedimientos de este tutorial.  
  
    |Título del procedimiento|Descripción del procedimiento|  
    |---------------------|---------------------------|  
    |Para exportar la directiva ProcessPurchaseOrder 1.3 y el vocabulario POVocabulary a un archivo XML|Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para exportar el **ProcessPurchaseOrder** directiva y la **POVocabulary** vocabulario a un archivo XML.|  
    |Para eliminar la directiva ProcessPurchaseOrder|Proporciona instrucciones paso a paso para eliminar la **ProcessPurchaseOrder** directiva desde **RuleTestApp** y la base de datos de motor de reglas.|  
    |Para importar el archivo XML a fin de volver a crear la directiva ProcessPurchaseOrder|Proporciona instrucciones paso a paso para importar el archivo XML exportado en el primer procedimiento para volver a crear la **ProcessPurchaseOrder** directiva.|  
    |Para agregar la directiva ProcessPurchaseOrder a la aplicación RuleTestApp |Proporciona instrucciones paso a paso para agregar la **ProcessPurchaseOrder** directiva a la **RuleTestApp** aplicación.|  
  
3.  El tercer tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva mediante el uso de un archivo MSI exportado desde la consola de administración de BizTalk Server. En la tabla siguiente se describen los procedimientos de este tutorial.  
  
    |Título del procedimiento|El procedimiento contiene instrucciones paso a paso para|  
    |---------------------|---------------------------------------------------|  
    |Para exportar la aplicación RuleTestApp a un archivo MSI|Proporciona instrucciones paso a paso para exportar el **RuleTestApp** aplicación a un archivo MSI, que se usará posteriormente para volver a crear la aplicación.|  
    |Para eliminar la aplicación RuleTestApp |Proporciona instrucciones paso a paso para eliminar la **RuleTestApp** aplicación para que pueda probar volver a crear la aplicación mediante el archivo MSI.|  
    |Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han eliminado|Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que la **ProcessPurchaseOrder** directiva y el vocabulario POVocabulary se eliminan.|  
    |Para importar el archivo MSI a fin de volver a crear la aplicación RuleTestApp |Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para importar el archivo MSI para volver a crear la **RuleTestApp** aplicación.|  
    |Para comprobar que la directiva ProcessPurchaseOrder se ha agregado a RuleTestApp |Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para comprobar que la **ProcessPurchaseOrder** directiva se agrega a la **RuleTestApp** aplicación.|  
    |Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han vuelto a crear|Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que la **ProcessPurchaseOrder** directiva y **POVocabulary** vocabulario se vuelven a crear.|  
    |Para probar la solución|Proporciona instrucciones paso a paso para probar la solución.|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a>Procedimientos para implementar la directiva ProcessPurchaseOrder mediante el Asistente para implementación de motor de reglas de negocios  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a>Para exportar POVocabulary 1.0 y 1.1 mediante el Asistente para implementar el motor de reglas de negocios  
  
1.  En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  Haga clic en **Siguiente**.  
  
3.  En el **tarea de implementación** página, seleccione **Exportar directiva o vocabulario a archivo de base de datos**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **directiva Store** página, haga clic en **siguiente**.  
  
5.  En el **Exportar directiva o vocabulario** página, haga clic en **vocabulario**.  
  
6.  Seleccione **POVocabulary.1.0** en la lista desplegable para **directiva o vocabulario**, escriba o busque y especifique el nombre de archivo de salida XML como **C:\BRE-walkthroughs\POVocabulary10.xml**y, a continuación, haga clic en **siguiente**.  
  
7.  En el **listo** página, haga clic en **siguiente**.  
  
8.  En el **Exportando directiva o vocabulario** página, haga clic en **siguiente.**  
  
9. Seleccione **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  
  
     Dado que seleccionó **vuelva a ejecutar este asistente**, la primera pantalla del asistente aparece de nuevo.  
  
10. Repita los pasos 2 a 6.  
  
11. Seleccione **POVocabulary.1.1** en la lista desplegable para **directiva o vocabulario**, escriba o busque y especifique el nombre de archivo de salida XML como **C:\BRE-walkthroughs\POVocabulary11.xml**y, a continuación, haga clic en **siguiente**.  
  
12. Repita los pasos 8 y 9.  
  
13. Haga clic en **Finalizar**.  
  
    > [!NOTE]
    >  Debe exportar las versiones 1.0 y 1.1 de **POVocabulary** porque **ProcessPurchaseOrder** 1.3 depende de ambas versiones de **POVocabulary**. El **número máximo de elementos permitidos** se utiliza la definición de la versión 1.1 del vocabulario. El **cantidad solicitada** y **estado de la solicitud** se usan las definiciones de la versión 1.0.  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a>Para exportar ProcessPurchaseOrder 1.3 mediante el Asistente para implementación de motor de reglas de negocios  
  
1.  En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **éste es el Asistente para la implementación del motor de reglas** página, haga clic en **siguiente**.  
  
3.  Seleccione **Exportar directiva o vocabulario a archivo de base de datos**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **directiva Store** página, haga clic en **siguiente**.  
  
5.  Compruebe que la **directiva** está seleccionada.  
  
6.  Seleccione **ProcessPurchaseOrder.1.3** en la lista desplegable para **directiva o vocabulario**.  
  
7.  Escriba o busque **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** como el nombre de archivo de salida XML.  
  
8.  Haga clic en **siguiente** tres veces al y, a continuación, haga clic en **finalizar**.  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a>Para eliminar ProcessPurchaseOrder y POVocabulary  
  
1.  En el **iniciar** menú Abrir **compositor**. Si tiene ya, presione F5 o haga clic en el Compositor de reglas de negocio **recarga** en el **archivo** menú para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **eliminar**. Si **eliminar** está deshabilitado, haga clic en **versión 1.0**y, a continuación, haga clic en **Undeploy**.  
  
    > [!NOTE]
    >  Las versiones de directivas implementadas no se pueden eliminar. Es preciso anular la implementación de una directiva para poder eliminar una versión de esa directiva.  
  
3.  Haga clic en **Sí** en el cuadro de mensaje de confirmación.  
  
4.  Repita los pasos 2 y 3 para eliminar **versión 1.1**.  
  
5.  Repita los pasos 2 y 3 para eliminar **versión 1.2**.  
  
6.  Haga clic en **versión 1.3 implementada**y, a continuación, haga clic en **Undeploy**. Si el **Undeploy** opción está deshabilitada, omita este paso.  
  
7.  En la ventana Explorador de hechos, expanda **vocabularios**, haga clic en **POVocabulary**y, a continuación, haga clic en **eliminar**.  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a>Para importar desde XML a fin de volver a crear POVocabulary 1.0 y 1.1  
  
1.  En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **éste es el Asistente para la implementación del motor de reglas**, haga clic en **siguiente**.  
  
3.  En el **tarea de implementación** página, seleccione **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **directiva Store** página, haga clic en **siguiente**.  
  
5.  Busque y seleccione el **POVocabulary10.xml** archivo que creó en el primer procedimiento.  
  
6.  Haga clic en **abierto** o haga doble clic en **POVocabulary10.xml**.  
  
7.  Haga clic en **siguiente** en el Asistente para implementación de motor de reglas de negocios.  
  
8.  Haga clic en **Siguiente**.  
  
9. Haga clic en **Siguiente**.  
  
10. Seleccione **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  
  
11. Repita los pasos del 2 al 9 para importar **POVocabulary11.xml**.  
  
12. Haga clic en **Finalizar**.  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a>Para comprobar que se han vuelto a crear POVocabulary 1.0 y 1.1  
  
1.  En el **iniciar** menú Abrir **compositor**. Si tiene ya está abierto, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.  
  
3.  Expanda **vocabularios**, y debería ver **POVocabulary**.  
  
4.  Expanda **POVocabulary**, y debería ver **versión 1.0** y **versión 1.1**.  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a>Para importar desde XML a fin de volver a crear ProcessPurchaseOrder 1.3  
  
1.  En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **éste es el Asistente para la implementación del motor de reglas**, haga clic en **siguiente**.  
  
3.  En el **tarea de implementación** página, seleccione **importar y publicar una directiva o vocabulario a la base de datos desde archivopara base de datos de archivo**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **directiva Store** página, haga clic en **siguiente**.  
  
5.  Busque y seleccione el **ProcessPOPolicy13.xml** archivo que creó anteriormente en este tutorial.  
  
6.  Haga clic en **abierto** o haga doble clic en **ProcessPOPolicy13.xml**.  
  
7.  Haga clic en **siguiente** en el Asistente para implementación de motor de reglas de negocios.  
  
8.  Haga clic en **Siguiente**.  
  
9. Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a>Para comprobar que se ha vuelto a crear ProcessPurchaseOrder 1.3  
  
1.  En el **iniciar** menú Abrir **compositor**. Si tiene ya está abierto, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas** y debería ver **ProcessPurchaseOrder**.  
  
3.  Expanda **ProcessPurchaseOrder** y debería ver **versión 1.3 publicada**.  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a>Procedimientos para implementar la directiva mediante un archivo XML exportado desde la consola de administración de BizTalk Server  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a>Para exportar la directiva ProcessPurchaseOrder 1.3 y el vocabulario POVocabulary a un archivo XML  
  
1. En el **iniciar** menú Abrir [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]. Si la herramienta ya está abierta, presione F5 para actualizarla.  
  
2. Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **RuleTestApp** .  
  
3. Haga clic en **directivas** y asegúrese de que ve la directiva ProcessPurchaseOrder 1.3 de la lista.  
  
4. Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **exportar**.  
  
5. En el **exportar directivas** diálogo cuadro, asegúrese de que el **ProcessPurchaseOrder** directiva y la **POVocabulary** están seleccionadas.  
  
   > [!NOTE]
   >  Puede exportar todas las directivas en una aplicación en un archivo XML con el botón secundario **RuleTest** y, a continuación, haga clic en **exportar** en el **directivas** menú. De este modo, se exportan todas las directivas y el vocabulario usados por esta aplicación a un mismo archivo XML.  
  
   > [!NOTE]
   >  Puede exportar todas las directivas en todas las aplicaciones en un archivo XML haciendo clic con el **aplicaciones** nodo y, a continuación, haga clic en **exportar** en el **directivas** menú. De este modo, se exportan todas las directivas y vocabularios usados en todas las aplicaciones a un mismo archivo XML.  
  
6. Especifique un nombre de archivo XML de salida (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a>Para eliminar la directiva ProcessPurchaseOrder  
  
1.  En administración de BizTalk Server, haga clic en **ProcessPurchaseOrder** en la lista y, a continuación, haga clic en **quitar**.  
  
2.  Haga clic en **Sí** en el **Quitar directiva** cuadro de mensaje.  
  
    > [!NOTE]
    >  Si la directiva está en estado implementado, no se puede quitar. Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **Undeploy** para anular la implementación de la directiva. El **quitar** elemento de menú está disponible cuando la directiva está implementada.  
  
    > [!NOTE]
    >  Los vocabularios en el que el **ProcessPurchaseOrder** directiva depende, en este caso **POVocabulary**, también se eliminan.  
  
    > [!NOTE]
    >  Cuando se quita una directiva de una aplicación, tanto la directiva como los vocabularios de los que depende se eliminan asimismo de la base de datos del motor de reglas, no sólo de la aplicación.  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a>Para importar el archivo XML a fin de volver a crear la directiva ProcessPurchaseOrder  
  
1. En administración de BizTalk Server, expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.  
  
2. Haga clic en **aplicaciones**, apunte a **importación**y, a continuación, haga clic en **directivas**.  
  
3. Busque y haga doble clic en el archivo XML (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) que creó en el primer procedimiento.  
  
4. Expanda **\<todos los artefactos\>** en **aplicaciones**.  
  
5. Haga clic en **directivas**, y debería ver la versión 1.3 de la **ProcessPurchaseOrder** directiva en la lista.  
  
6. Presione F5 para actualizar la vista. El **ProcessPurchaseOrder** directiva debe estar en el **no publicado** estado.  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a>Para agregar la directiva ProcessPurchaseOrder a la aplicación RuleTestApp   
  
1.  En administración de BizTalk Server, haga clic en **ProcessPurchaseOrder** directiva y, a continuación, haga clic en **publicar**.  
  
    > [!NOTE]
    >  Sólo se pueden agregar a una aplicación de BizTalk las directivas publicadas.  
  
2.  En el **aplicaciones** nodo, expanda **RuleTestApp**.  
  
3.  Haga clic en **directivas** en **RuleTestApp**.  
  
4.  Haga clic en la lista de la derecha, seleccione **agregar**y, a continuación, haga clic en **directiva**.  
  
5.  Expanda el **ProcessPurchaseOrder** nodo, seleccione la casilla de verificación **versión 1.3 (publicada)** y, a continuación, haga clic en **Aceptar**. .  
  
6.  Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **implementar**. Si no ve **ProcessPurchaseOrder** en la lista, presione F5 para actualizar la vista.  
  
7.  Haga clic en **Sí** en el cuadro de mensaje de confirmación.  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a>Procedimientos para implementar la directiva mediante un archivo MSI  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a>Para exportar la aplicación RuleTestApp a un archivo MSI  
  
1. En el **iniciar** menú Abrir **administración de BizTalk Server**. Si la herramienta ya está abierta, presione F5 para actualizarla.  
  
2. Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Haga clic en **RuleTestApp**, apunte a **exportar**y, a continuación, haga clic en **archivo MSI**.  
  
4. En el **éste es el Asistente para exportar archivos MSI** página, haga clic en **siguiente**.  
  
5. En el **seleccionar recursos** , revise todas las opciones predeterminadas y, a continuación, haga clic en **siguiente**.  
  
6. En el **especificar Hosts de ISS** página, haga clic en **siguiente**.  
  
7. En el **dependencias** página, haga clic en **siguiente**.  
  
8. En el **destino** , especifique el directorio y el nombre del archivo msi **C:\BRE-Walkthroughs\RuleTestApp.msi**.  
  
9. Haga clic en **Exportar**.  
  
10. En el **resumen** página, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  Al exportar la aplicación RuleTestApp, las directivas y los vocabularios usados en esa aplicación también se exportan al archivo MSI. Posteriormente, cuando importe el archivo MSI, se volverán a crear el vocabulario, la directiva y la aplicación.  
  
#### <a name="to-delete-the-ruletestapp-application"></a>Para eliminar la aplicación RuleTestApp   
  
1.  En administración de BizTalk Server, haga clic en **RuleTestApp**y compruebe si el **eliminar** menú está habilitado o deshabilitado.  
  
2.  Si **eliminar** está deshabilitado, haga clic en **RuleTestApp**, haga clic en **detener**, seleccione **detención completa: finalizar instancia**y, a continuación, haga clic en  **Detener**.  
  
3.  Haga clic en **RuleTestApp**y, a continuación, haga clic en **eliminar**.  
  
4.  Haga clic en **Sí** para confirmar la eliminación.  
  
    > [!NOTE]
    >  Cuando se elimina una aplicación, todas las directivas de la aplicación y los vocabularios dependientes se eliminan asimismo de la base de datos del motor de reglas.  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a>Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han eliminado  
  
1.  En el **iniciar** menú Abrir **compositor**. Si tiene compositor ya abierto, presione F5 para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**y asegúrese de que no existe la directiva ProcessPurchaseOrder.  
  
3.  En la ventana Explorador de hechos, expanda **vocabularios**y asegúrese de que no existe POVocabulary.  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a>Para importar el archivo MSI a fin de volver a crear la aplicación RuleTestApp   
  
1. En el **iniciar** menú Abrir **administración de BizTalk Server**. Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.  
  
2. Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.  
  
3. Haga clic en **aplicaciones**, apunte a **importación**y, a continuación, haga clic en **archivo MSI**.  
  
4. En el **el Asistente para importar** página, busque y seleccione el archivo MSI (RuleTestApp.msi) que exportó anteriormente para el **archivo MSI para importar** configuración.  
  
5. Haga clic en **Siguiente**.  
  
6. En el **configuración de la aplicación** página, haga clic en **siguiente**.  
  
7. En el **configuración del entorno de destino de aplicación** página, haga clic en **siguiente**.  
  
8. En el **resumen de importación** página, haga clic en **importación**.  
  
9. En el **importación se realizó correctamente** página, haga clic en **finalizar**. Debería ver que el **RuleTestApp** aplicación se crea en **aplicaciones** en la consola de administración de BizTalk Server.  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a>Para comprobar que la directiva ProcessPurchaseOrder se ha agregado a RuleTestApp   
  
1.  Expanda **RuleTestApp** en la consola de administración de BizTalk Server.  
  
2.  Seleccione **directivas** y debería ver **ProcessPurchaseOrder** en la lista en el panel derecho.  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a>Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han vuelto a crear  
  
1.  En el **iniciar** menú Abrir **compositor**. Si ya está abierto, presione F5 para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**y asegúrese de que **ProcessPurchaseOrder** existe.  
  
3.  En la ventana Explorador de hechos, expanda **vocabularios**y asegúrese de que **POVocabulary** existe.  
  
#### <a name="to-test-the-solution"></a>Para probar la solución  
  
1. En el **iniciar** menú Abrir **administración de BizTalk Server**. Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.  
  
2. Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**.  
  
4. Haga clic en **iniciar**.  
  
5. Copia **SamplePO.xml** que creó en [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) al directorio de entrada para la orquestación.  
  
6. Debería ver un archivo de salida en el directorio de salida de la orquestación. Abra el archivo XML de salida y observe que el valor de la **estado** campo se establece en **aprobado**.  
  
7. Repita los pasos 3 y 4 con **SamplePO2.xml**y tenga en cuenta que el valor de la **estado** campo en el documento de salida es igual que en el documento de entrada (**XYZ**).  
  
## <a name="comments"></a>Comentarios  
  
-   Es **muy importante** recordar que, cuando se quita una directiva desde una aplicación, no solo quita la asociación entre la aplicación y la directiva; eliminar también la directiva y su vocabulario asociado de la regla base de datos del motor.  
  
-   Al iniciar una aplicación, ésta implementa de manera predeterminada y automática todas las directivas. De forma similar, al detener una aplicación y seleccionar **detención completa: finalizar instancias**, las directivas asociadas se anula automáticamente. Al seleccionar **detención parcial: suspender las instancias en ejecución**, las directivas asociadas no se anula automáticamente.  
  
-   Debe actualizar las vistas del Compositor de reglas de negocio y de la consola de administración de BizTalk Server para asegurarse de estar viendo la información más reciente antes de llevar a cabo cualquier operación.  
  
-   Si crea una versión nueva de la directiva cuya versión anterior está asociada a una aplicación de BizTalk, debe agregar manualmente a la aplicación la nueva versión de la directiva. No debe quitar la versión anterior de la directiva a no ser que desee eliminarla por completo de la base de datos del motor de reglas.  
  
-   Puede combinar dos o más archivos BRL (archivos XML de Lenguaje de reglas de negocio) en un solo archivo BRL antes de importar. El código siguiente muestra tres archivos BRL. El primer archivo BRL contiene el **POVocabulary** vocabulario. El segundo archivo BRL contiene el **ProcessPurchaseOrder** directiva. El tercer archivo BRL contiene tanto el **POVocabulary** vocabulario y el **ProcessPurchaseOrder** directiva. Para realizar el tercer archivo BRL, realice estos pasos:  
  
    1.  Crear un nuevo archivo con cualquier archivo editor y guárdelo como un archivo XML (por ejemplo: POPolicyVocabulary.xml).  
  
    2.  Copie el contenido XML completo del primer archivo BRL que contiene el vocabulario.  
  
    3.  Copie el bloque del conjunto de reglas (comienza con la \<ruleset\> etiqueta y finaliza con la \</ruleset\> etiqueta) del segundo archivo BRL.  
  
    4.  Guarde el archivo nuevo. Puede importar este archivo XML único para crear el **POVocabulary** vocabulario y el **ProcessPurchaseOrder** directiva.  
  
    > [!NOTE]
    >  El orden en que se enumeran los nodos vocabulary y ruleset en el archivo BRL combinado no es relevante. Puede colocar el nodo ruleset antes que el nodo vocabulary.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
    </brl>  
  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
    ```