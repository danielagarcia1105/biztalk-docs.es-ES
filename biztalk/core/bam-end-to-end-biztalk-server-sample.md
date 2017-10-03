---
title: Ejemplo de extremo a extremo BAM en BizTalk Server | Documentos de Microsoft
description: "Escenario sobre cómo correlacionar eventos desde varios componentes mediante la supervisión de la actividad de negocio de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21cf3bcfae53d3204a1b4de23c1476591be2b453
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-end-to-end-biztalk-server-sample"></a>Extremo a extremo de BAM (ejemplo de BizTalk Server)
En el ejemplo de extremo a extremo se muestra cómo correlacionar eventos desde varios componentes (en este caso, tres orquestaciones y una canalización) mediante BAM.  
  
 BAM reconstruye la actividad económica que abarca el componente de canalización y las orquestaciones. En el nivel más bajo, esto se realiza mediante llamadas a **EventStream.EnableContinuation** de cada componente de implementación que espera más eventos de la actividad. La llamada a **EnableContinuation** es explícita, mientras que las llamadas de Orchestration1 y Orchestration2 se realizan mediante la adición de una carpeta Continuation al perfil de seguimiento en una programación y una carpeta ContinuationID a la programación que sigue a se.  
  
 En el siguiente diagrama se muestra el flujo de trabajo usado en el ejemplo.  
  
 ![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")  

  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En el ejemplo de extremo a extremo de BAM se muestra cómo puede usar BAM para recopilar información desde una canalización y varias orquestaciones y actualizar una única actividad.  
  
## <a name="how-this-sample-was-designed-and-why"></a>Cómo y por qué se ha diseñado este ejemplo  
 El ejemplo de extremo a extremo de BAM se ha diseñado para demostrar las siguientes actividades:  
  
-   Uso de BAM dentro de una canalización  
  
-   Uso del Editor de perfiles de seguimiento (TPE) para asignar elementos de actividad a formas en una orquestación y a elementos de un mensaje  
  
-   Uso de continuaciones para mantener activa una actividad cuando contribuyen a ella varias piezas de una solución  
  

El ejemplo funciona como se describe a continuación:  
  
1.  Un mensaje de entrada se recupera de la  *\<ruta de ejemplos >*carpeta \BamEndToEnd\Input.  
  
2.  El componente de canalización asigna un identificador de documento único al mensaje y usa la API de BAM para comenzar una nueva actividad de BAM. El DocumentID se adjunta como una parte separada del mensaje de entrada para que esté disponible para las orquestaciones.  
  
3.  La Orchestration1 se activa cuando se recibe el mensaje de entrada.  
  
4.  La Orchestration1 modifica el mensaje de entrada y lo pasa como un parámetro a la Orchestration2.  
  
5.  La Orchestration2 modifica el mensaje de entrada y lo envía a la base de datos de cuadro de mensajes, la cual activa la Orchestration3.  
  
6.  La Orchestration3 modifica el mensaje y lo escribe en la carpeta  *\<ruta de ejemplos >*\BamEndToEnd\Output.  
  
7.  Cada orquestación actualiza los elementos de actividad de la actividad de BAM.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Puede encontrar este ejemplo en  *\<ruta de ejemplos >*\BAM\BamEndToEnd.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|----|---|  
|BamEndToEnd.sln|Solución de ejemplo de Extremo a extremo de BAM.|  
|BamEndToEnd.xls|Hoja de estilos de definición de BAM.|  
|BamEndToEnd.xml|XML de definición de BAM.|  
|BAMEndToEndBinding.xml|Enlace de BAM.|  
|Cleanup.bat|Archivo por lotes que se usa para anular la implementación del ejemplo.|  
|InputMessage.xml|Mensaje de entrada.|  
|Setup.bat|Archivo por lotes para compilar e implementar el ejemplo.|  
|\Components\AssemblyInfo.cs|Código de componente de canalización.|  
|\Components\BAMMessagePartPLComponent.cs|Código de componente de canalización.|  
|\Components\Components.csproj|Proyecto de componentes de canalización.|  
|\Messages\InputMessage01.xml<br /><br /> ...<br /><br /> \Messages\InputMessage10.xml|Mensajes de entrada de ejemplo.|  
|\Services\BAMInbound.btp|Archivo de canalización de entrada.|  
|\Services\BAMPartSchema.xsd|Esquema de mensajes de la parte de BAM.|  
|\Services\Orchestration1.odx|Orquestación.|  
|\Services\Orchestration2.odx|Orquestación.|  
|\Services\Orchestration3.odx|Orquestación.|  
|\Services\PropertySchema.xsd|Esquema de propiedad.|  
|\Services\Schema1.xsd|Esquema de mensajes.|  
|\Services\Schema2.xsd|Esquema de mensajes.|  
Services\Schema3.xsd|Esquema de mensajes.|  
|\Services\Services.btproj|Archivo de proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].|  
|\Services\Transform_1.btm|Archivo de asignación.|  
|\Services\Transform_2.btm|Archivo de asignación.|  
|\Services\Transform_3.btm|Archivo de asignación.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use los siguientes procedimientos para generar y ejecutar el ejemplo de extremo a extremo de BAM:  
  
-   [Para crear e inicializar este ejemplo](#To_Build_Sample)  
  
-   [Para ejecutar este ejemplo](#To_Run_Sample)  
  
-   [Para ver los datos BAM](#To_View_Data)  
  
##  <a name="To_Build_Sample"></a>Crear e inicializar este ejemplo  
  
1.  Abra un símbolo del sistema como administrador y ejecute  *\<ruta de ejemplos >*\BAM\BAMEndToEnd\Setup.bat. Setup.bat genera e inicializa la infraestructura de BAM para este ejemplo. Mantenga abierto el símbolo del sistema.  
  
2.  Cree un perfil de seguimiento para asignar Orchestration1, Orchestration2 y Orchestration3 a la actividad de BAM. (Dado que crear el perfil de seguimiento es un proceso complejo, las instrucciones detalladas se encuentran en un procedimiento independiente denominado **para crear un perfil de seguimiento**. Este procedimiento aparece más adelante en este documento).  
  
3.  Implemente el perfil de seguimiento BamEndToEnd.btt que creó en el paso anterior.  En el símbolo del sistema, cambie a la  *\<ruta de ejemplos >*directorio \BAM\BamEndToEnd. Para implementar el perfil de seguimiento, escriba la línea siguiente y, a continuación, presione **ENTRAR**:  
  
    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`
  
     [Cómo implementar perfiles de seguimiento con la utilidad de administración de perfiles de seguimiento](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md) proporciona más información.
  
    > [!IMPORTANT]
    >  Puede pasar por alto el mensaje que indica que el identificador de continuación Orch1_ no tiene una continuación coincidente. Es previsible que aparezca este mensaje, pues la continuación denominada Orch1_ está definida en el componente de canalización y no en el perfil de seguimiento.  
  
##  <a name="To_Run_Sample"></a>Ejecutar este ejemplo  
  
Copie el archivo  *\<ruta de ejemplos >*\BamEndToEnd\InputMessage.xml en la carpeta  *\<ruta de ejemplos >*\BamEndToEnd\Input. Después de unos segundos, el mensaje desaparece de la carpeta de entrada y aparece un mensaje de salida en el  *\<ruta de ejemplos >*carpeta \BamEndToEnd\Output.  
  
##  <a name="To_View_Data"></a>Ver los datos de BAM  
  
1.  Abra SQL Server Management Studio.  
  
2.  En SQL Server Management Studio, expanda el servidor, expanda **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.  
  
3.  Haga clic en **dbo.bam_EndToEndActivity_Completed**y, a continuación, haga clic en **Abrir tabla**. Si utilizas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], haga clic en **seleccionar las primeras 1000 filas**.  
  
     El contenido de la tabla bam_EndToEndActivity_Completed se muestra en el panel derecho. Cada fila de la tabla representa una actividad EndToEndActivity que se ha completado.  
  
#### <a name="rerun-this-sample"></a>Vuelva a ejecutar este ejemplo  
  
1.  Abra un símbolo del sistema como administrador y cambie a la  *\<ruta de ejemplos >*directorio \BAM\BamEndToEnd. Escriba la línea siguiente:  
  
    `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  
  
    > [!NOTE]
    >  Si no ha instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la unidad C, reemplace "C" por la letra de unidad donde se instaló [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  Ejecutar  *\<ejemplos de ruta de acceso >*\BAM\BAMEndToEnd\Cleanup.bat. Cleanup.bat quita la infraestructura de BAM para este ejemplo.  
  
3.  Realice los pasos en **para crear e inicializar este ejemplo** sección en este tema.  
  
##  <a name="TPE_procedure"></a>Crear un perfil de seguimiento  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]. Haga clic en **Editor de perfiles de seguimiento**, y **ejecutar como administrador**.  
  
2.  En el panel izquierdo de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar una definición de actividad de BAM**.  
  
3.  En el **nombre de definición de actividad de BAM** sección de la **Importar definición de actividad de BAM** cuadro de diálogo, seleccione **EndToEndActivity**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el panel derecho de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar un origen de eventos**.  
  
5.  En el **nombre de ensamblado** sección de la **seleccionar ensamblado primario de origen de eventos** cuadro de diálogo, seleccione **Microsoft.Samples.BizTalk.BamEndToEnd.Services**y, a continuación, haga clic en **Siguiente**.  
  
6.  En el **nombre de la orquestación** sección de la **Seleccionar orquestación** cuadro de diálogo, seleccione **BamEndToEnd.Services.Orchestration1**y, a continuación, haga clic en **Aceptar** .  
  
7.  En el panel izquierdo de la **Editor de perfiles de seguimiento** ventana, haga clic en **EndToEndActivity**y, a continuación, haga clic en **nuevo ContinuationID**. Nombre del nuevo continuation ID **Orch1_**. Repita este paso para crear la continuación más dos identificadores denominados **Orch2_** y **Orch3_**.  
  
8.  Haga clic en **EndToEndActivity**y, a continuación, haga clic en **nueva Continuation**. Nombre de la nueva continuación **Orch2_**. Repita este paso para crear otra continuación denominada **Orch3_**.  
  
9. Haga clic en el **Receive1** forma y, a continuación, haga clic en **esquemas de propiedad de contexto**.  
  
10. Desplácese hasta el final de la **nombre de la propiedad de contexto** lista y, a continuación, haga doble clic en **BAMEndToEnd.Services.PropertySchema.DocumentID**.  
  
11. Expanda  **\<esquema >**y, a continuación, arrastre **DocumentID** en el panel derecho a **Orch1_** en el panel izquierdo.  
  
12. Haga clic en el icono de carpeta con la flecha (![botón con carpeta y flecha arriba](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) dos veces para mostrar la orquestación.  
  
13. Arrastre el **Receive1** forma en el panel derecho a **SBegin1** en el panel izquierdo.  
  
14. Arrastre el **StartOrchestration_1** forma en el panel derecho a **SEnd1** en el panel izquierdo.  
  
15. Haga clic en el **StartOrchestration_1** forma y, a continuación, haga clic en **Message Payload Schemas**.  
  
16. Haga doble clic en la fila que contiene el valor "Message_2" en la **mensaje** columna y el valor "MessageBody" en la **parte** columna.  
  
     ![Esquema de carga de mensaje TPE que muestra mensajes &#95; 2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")  
  
17. Expanda **Schema2**y, a continuación, arrastre **Data2** en el panel derecho a **Data1** en el panel izquierdo.  
  
18. Haga clic en **Seleccionar origen de eventos**y, a continuación, haga clic en **Seleccionar propiedad de contexto**.  
  
19. Desplácese hasta el final de la **nombre de la propiedad de contexto** lista y, a continuación, haga doble clic en **BAMEndToEnd.Services.PropertySchema.DocumentID**.  
  
20. Expanda  **\<esquema >**y, a continuación, arrastre **DocumentID** a la **Orch2_** continuación en el panel izquierdo.  
  
    > [!NOTE]
    >  No confunda la continuación Orch2_ con el identificador de continuación Orch2_. El icono que representa un identificador de continuación contiene una clave (![icono para un identificador de continuación](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), mientras que el icono que representa una continuación no contiene una clave ( ![icono para una continuación](../core/media/test.gif "probar")).  
  
21. Haga clic en **Seleccionar origen de eventos**y, a continuación, haga clic en **seleccionar programación de orquestación**.  
  
22. En el **nombre de ensamblado** sección de la **seleccionar ensamblado primario de origen de eventos** cuadro de diálogo, seleccione **Microsoft.Samples.BizTalk.BamEndToEnd.Services**y, a continuación, haga clic en **Siguiente**.  
  
23. En el **nombre de la orquestación** sección de la **Seleccionar orquestación** cuadro de diálogo, seleccione **BamEndToEnd.Services.Orchestration2**y, a continuación, haga clic en **Aceptar** .  
  
24. Haga clic en el **ConstructMessage_1** forma y, a continuación, haga clic en **Message Payload Schemas**.  
  
25. Haga doble clic en la fila que contiene el valor "Message_3" en la **mensaje** columna y el valor "BAMPart" en la **parte** columna.  
  
26. Expanda **BAMPart**y, a continuación, arrastre **DocumentID** en el panel derecho a la **Orch2_** identificador de continuación en el panel izquierdo.  
  
    > [!NOTE]
    >  No confunda la continuación Orch2_ con el identificador de continuación Orch2_. El icono que representa un identificador de continuación contiene una clave (![icono para un identificador de continuación](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), mientras que el icono que representa una continuación no contiene una clave ( ![icono para una continuación](../core/media/test.gif "probar")).  
  
27. Haga clic en el icono de carpeta con la flecha (![botón con carpeta y seguridad &#45; flecha](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) dos veces para mostrar la orquestación.  
  
28. Arrastre el **ConstructMessage_1** forma en el panel derecho a **SBegin2** en el panel izquierdo.  
  
29. Arrastre el **Send_1** forma en el panel derecho a **SEnd2** en el panel izquierdo.  
  
30. Haga clic en el **Send_1** forma y, a continuación, haga clic en **Message Payload Schemas**.  
  
31. Haga doble clic en la fila que contiene el valor "Message_3" en la **mensaje** columna y el valor "MessageBody" en la **parte** columna.  
  
32. Expanda **Schema3**y, a continuación, arrastre **Data3** en el panel derecho a **Data2** en el panel izquierdo.  
  
33. En la lista desplegable situada sobre el panel derecho, seleccione **Message Payload Schemas**.  
  
34. Haga doble clic en la fila que contiene el valor "Message_3" en la **mensaje** columna y el valor "BAMPart" en la **parte** columna.  
  
35. Expanda **BAMPart**y, a continuación, arrastre **DocumentID** en el panel derecho a la **Orch3_** continuación en el panel izquierdo.  
  
    > [!NOTE]
    >  No confunda la continuación Orch3_ con el identificador de continuación Orch3_. El icono que representa un identificador de continuación contiene una clave (![icono para un identificador de continuación](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), mientras que el icono que representa una continuación no contiene una clave ( ![icono para una continuación](../core/media/test.gif "probar")).  
  
36. Haga clic en **Seleccionar origen de eventos**y, a continuación, haga clic en **seleccionar programación de orquestación**.  
  
37. En el **nombre de ensamblado** sección de la **seleccionar ensamblado primario de origen de eventos** cuadro de diálogo, seleccione **Microsoft.Samples.BizTalk.BamEndToEnd.Services**y, a continuación, haga clic en **Siguiente**.  
  
38. En el **nombre de la orquestación** sección de la **Seleccionar orquestación** cuadro de diálogo, seleccione **BamEndToEnd.Services.Orchestration3**y, a continuación, haga clic en **Aceptar** .  
  
39. Haga clic en el **Receive1** forma y, a continuación, haga clic en **Message Payload Schemas**.  
  
40. Haga doble clic en la fila que contiene el valor "Message_3" en la **mensaje** columna y el valor "BAMPart" en la **parte** columna.  
  
41. Expanda **BAMPart**y, a continuación, arrastre **DocumentID** en el panel derecho a la **Orch3_** identificador de continuación en el panel izquierdo.  
  
    > [!NOTE]
    >  No confunda la continuación Orch3_ con el identificador de continuación Orch3_. El icono que representa un identificador de continuación contiene una clave (![icono para un identificador de continuación](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), mientras que el icono que representa una continuación no contiene una clave ( ![icono para una continuación](../core/media/test.gif "probar")).  
  
42. Haga clic en el icono de carpeta con la flecha (![botón con carpeta y flecha arriba](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) dos veces para mostrar la orquestación.  
  
43. Arrastre el **Receive1** forma en el panel derecho a **SBegin3** en el panel izquierdo.  
  
44. Arrastre el **Send_1** forma en el panel derecho a **SEnd3** en el panel izquierdo.  
  
45. Haga clic en el **Send_1** forma y, a continuación, haga clic en **esquema de carga de mensaje**.  
  
46. Expanda **Schema3**y, a continuación, arrastre **Data3** en el panel derecho a **Data3** en el panel izquierdo.  
  
47. Haga clic en **DocumentID** a continuación el **Orch2_** continuación y, a continuación, haga clic en **establecer asignaciones de puertos**.  
  
    > [!NOTE]
    >  No confunda la continuación Orch2_ con el identificador de continuación Orch2_. El icono que representa un identificador de continuación contiene una clave (![icono para un identificador de continuación](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), mientras que el icono que representa una continuación no contiene una clave ( ![icono para una continuación](../core/media/test.gif "probar")).  
  
48. En el **seleccionar puertos** sección de la **seleccionar puertos** cuadro de diálogo, haga clic en **BamEndToEnd_ReceivePort**, haga clic en la mayor-de inicio de sesión ( **>** ) y, a continuación, haga clic en **Aceptar**.  
  
49. Guarde el perfil de seguimiento para  *\<ruta de ejemplos >*\BAM\BamEndToEnd\BamEndToEnd.btt.  
  
## <a name="important-details"></a>Detalles importantes  
 Los archivos de seguimiento no son compatibles con las canalizaciones. Sin embargo, la llamada a **BeginActivity** en la canalización de componente es lo mismo que usar ActivityID en una orquestación. La llamada a **EnableContinuation** es lo mismo que usar una continuación en una orquestación.  
  
## <a name="see-also"></a>Vea también  
 [(Carpeta de ejemplos de BizTalk Server) de supervisión de la actividad de negocio](../core/business-activity-monitoring-biztalk-server-samples-folder.md)