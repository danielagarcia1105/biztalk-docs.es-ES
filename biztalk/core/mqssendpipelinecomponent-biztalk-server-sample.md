---
title: MQSSendPipelineComponent (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- pipelines, examples
- MQSeries adapters, examples
- examples, pipelines
ms.assetid: ac709e45-524b-45ab-9673-060790ecbed2
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 256731dbb6194aa1962d62ec9fdbe58a0fd60e03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqssendpipelinecomponent-biztalk-server-sample"></a>MQSSendPipelineComponent (ejemplo de BizTalk Server)
En este ejemplo se muestra cómo escribir un componente de canalización que lea un conjunto de valores de propiedades de MQSeries a partir de un archivo XML y que los aplique a un mensaje.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo se compone de dos proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], un proyecto del componente de canalización y un proyecto de canalización que hace uso del componente.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
  
-   *\<Ruta de ejemplos >*\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent  
  
-   *\<Ruta de ejemplos >*\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|**Archivo**|**Description**|  
|--------------|---------------------|  
|SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln,<br /><br /> SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj|Archivos de proyectos y soluciones para el componente de canalización.|  
|SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs|Archivo de origen de Visual C#® para el componente de canalización.|  
|SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml|Propiedades de MQSeries leídas y usadas por el componente de canalización.|  
|SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj,<br /><br /> SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln|Archivos de proyectos y soluciones para la canalización de BizTalk.|  
|SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk|Archivo de clave de nombre seguro para el proyecto de canalización de BizTalk.|  
|SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp|La canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Para crear la aplicación, debe realizar los siguientes pasos:  
  
1.  Crear las carpetas para la aplicación.  
  
2.  Modificar y compilar el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el componente de canalización.  
  
3.  Copiar el ensamblado compilado y el archivo de encabezado en las carpetas adecuadas.  
  
4.  Modificar el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para la canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
5.  Compilar e implementar el proyecto de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
6.  Configurar una ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
7.  Crear una cola de MQSeries.  
  
8.  Configurar un puerto de envío.  
  
9. Habilitar la ubicación de recepción e iniciar el puerto de envío.  
  
## <a name="creating-the-folders-for-the-application"></a>Crear las carpetas para la aplicación  
 Este procedimiento crea las carpetas correspondientes para la aplicación.  
  
#### <a name="to-create-the-folders-for-the-application"></a>Para crear las carpetas para la aplicación  
  
1.  Cree una carpeta denominada **temp** en la unidad C:\ si aún no existe.  
  
2.  Cree una carpeta bajo la **C:\temp** directorio denominado **Pickup3**.  
  
## <a name="modifying-and-compiling-the-project-for-the-pipeline-component"></a>Modificar y compilar el proyecto para el componente de canalización  
 Este procedimiento modifica y compila el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el componente de canalización.  
  
#### <a name="to-modify-and-compile-the-project-for-the-pipeline-component"></a>Para modificar y compilar el proyecto para el componente de canalización  
  
1.  Haga doble clic en el archivo de solución, **Setmqseriesheaderpropertycomponent\setmqseriesheaderpropertycomponent** para abrir la solución en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Haga doble clic en el archivo de clase **CSetMQSeriesHeaderPropertyComponent.cs** para abrir el archivo de clase en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
3.  Podrá encontrar la variable **samplesDir**, compruebe que esta variable se establece en la ubicación **C:\temp**.  
  
4.  Haga clic en la solución en el Explorador de soluciones y haga clic en **generar**. Esto compilará el proyecto en un archivo dll que se encuentra en la **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\**  directory.  
  
## <a name="copying-the-assembly-and-header-file-to-appropriate-folders"></a>Copiar el ensamblado y el archivo de encabezado en las carpetas adecuadas  
 Este procedimiento copia el ensamblado compilado y el archivo de encabezado en las carpetas adecuadas.  
  
#### <a name="to-copy-the-compiled-assembly-and-header-file-to-the-appropriate-folders"></a>Para copiar el ensamblado compilado y el archivo de encabezado en las carpetas adecuadas  
  
1.  Copie el ensamblado compilado **SetMQSeriesHeaderPropertyComponent.dll** a la carpeta de componentes de canalización de BizTalk. La ubicación predeterminada para la carpeta de componentes de canalización de BizTalk es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components.  
  
2.  Copie el archivo de propiedades MQHeader **SetMQSMQMDHdrProps.xml** a la **C:\temp** directory.  
  
## <a name="modifying-the-project-for-the-biztalk-server-pipeline"></a>Modificar el proyecto para la canalización de BizTalk Server  
 Este procedimiento modifica el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para la canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="to-modify-the-project-for-the-biztalk-server-pipeline"></a>Para modificar el proyecto para la canalización de BizTalk Server  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra la solución haciendo doble clic en el archivo de solución, **Setmqseriesheaderpropertypipeline\setmqseriesheaderpropertypipeline**.  
  
2.  Cree un archivo de clave de nombre seguro para el proyecto. Para ello, haga lo siguiente:  
  
    1.  Abra un símbolo del sistema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
    2.  Cambie los directorios a \<Rutaejemplos > \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent.  
  
    3.  Escriba lo siguiente:  
  
         `sn -k MQSSendPipelineComponent.snk`  
  
    4.  Presione ENTRAR. Al hacerlo, se creará el archivo de clave.  
  
3.  En **el Explorador de soluciones**, haga clic en el proyecto y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto (en la ventana central).  
  
    1.  En el Diseñador de proyectos, haga clic en **firma** ficha.  
  
    2.  En el panel derecho, seleccione la **firmar el ensamblado** opción...  
  
    3.  Haga clic en la lista desplegable para la **elegir un archivo de clave de nombre seguro** opción y haga clic en **examinar**.  
  
    4.  Vaya a \<Rutaejemplos > \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk, haga clic en **abiertos**.  
  
4.  El componente de canalización que creó anteriormente se ha agregado a la **preensamblar** fase de este proyecto de canalización. En caso de que no se haya agregado, debería completar los pasos siguientes para agregarlo:  
  
    1.  En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE, haga clic en el **cuadro de herramientas** ficha en el lado izquierdo.  
  
    2.  Haga clic en el **cuadro de herramientas**y haga clic en **elegir elementos**.  
  
    3.  En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha, seleccione la **componente personalizado para las propiedades de encabezado de MQseries establece**componente, y a continuación, haga clic en **Aceptar**.  
  
    4.  Arrastre el **componente personalizado para las propiedades de encabezado de MQseries establece**componente a la **preensamblar** fase de esta canalización.  
  
## <a name="compiling-and-deploying-the-pipeline-project"></a>Compilar e implantar el proyecto de canalización  
 Este procedimiento compila e implementa el proyecto de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="to-compile-and-deploy-the-pipeline-project"></a>Para compilar e implantar el proyecto de canalización  
  
1.  En la ventana Explorador de soluciones, haga clic en la solución y, a continuación, haga clic en **implementar solución**. Así se genera la solución y se implementa el ensamblado en la base de datos de administración de BizTalk.  
  
2.  Verifique si el ensamblado se ha implementado en la base de datos de administración de BizTalk:  
  
    1.  Abra la consola de administración de BizTalk.  
  
    2.  Haga clic para expandir **grupo de BizTalk [\<nombreDeServidor >:\<base de datos de administración >]**y, a continuación, haga clic para expandir el **ensamblados** carpeta.  
  
         El ensamblado de canalización implementado debe verse en la **ensamblados** carpeta.  
  
## <a name="creating-the-receive-location"></a>Crear la ubicación de recepción  
 Este procedimiento crea una ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="to-create-the-receive-location"></a>Para crear la ubicación de recepción  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
2.  En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo, en la **nombre** cuadro, escriba "MQReply" y haga clic en **Aceptar**.  
  
3.  En el panel izquierdo, haga clic en **ubicaciones de recepción** ficha y, a continuación, haga clic en **nuevo**.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba "ReceiveFile".  
  
5.  En el **tipo de transporte** cuadro, seleccione **archivo**.  
  
6.  En el **controlador de recepción** campo, seleccione **BizTalkServerApplication**.  
  
7.  En el **canalización de recepción** campo, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.  
  
8.  En el **carpeta recepción** , escriba "C:\temp\Pickup3".  
  
9. En el **máscara de archivo** , escriba "*.\*".  
  
10. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo para salir del **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
## <a name="creating-a-mqseries-queue-through-the-mqseries-explorer"></a>Crear una cola de MQSeries mediante el explorador de MQSeries  
 Si dispone de los permisos necesarios para la instalación de MQSeries Server para Windows, puede crear la cola de MQSeries mediante los cuadros de diálogo del adaptador y puede omitir el procedimiento siguiente.  
  
 Si no dispone de este acceso, puede usar el procedimiento siguiente para crear la cola mediante IBM WebSphere MQ Explorer.  
  
#### <a name="to-create-a-mqseries-queue-through-the-mqseries-explorer"></a>Para crear una cola de MQSeries mediante el explorador de MQSeries  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.  
  
2.  Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado. El Administrador de cola predeterminado se suele llamar **QM_**\<*nombre_equipo*> donde *nombre_equipo* es el nombre del equipo.  
  
3.  Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.  
  
4.  En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **SETHEADER**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>Crear el puerto de envío y la cola MQSeries  
 Este procedimiento crea el puerto de envío para el mensaje de salida. También se crea la cola de MQSeries al crear el puerto de envío si no lo ha creado anteriormente.  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>Para crear el puerto de envío y la cola MQSeries  
  
1.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , escriba "MQSolicitResponse".  
  
3.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
4.  En el **canalización de envío** cuadro, seleccione **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**.  
  
5.  En **filtros**, agregue una nueva entrada con los siguientes pares de nombre/valor:  
  
    -   Establecer **propiedad** a "BTS". ReceivePortName".  
  
    -   Establecer **operador** como "==".  
  
    -   Establecer **valor** como "ReceiveFile".  
  
        > [!NOTE]
        >  De este modo, se establece el puerto de envío para suscribirse a mensajes que se reciban en el puerto de recepción ReceiveFile.  
  
6.  Haga clic en **transporte**.  
  
7.  En el **dirección (URI)** , a continuación, haga clic en el botón de puntos suspensivos (...).  
  
8.  En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **definición de la cola** , a continuación, haga clic en el botón de puntos suspensivos (...).  
  
9. En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
10. En el **Administrador de cola** , a continuación, seleccione el Administrador de cola predeterminado.  
  
11. En el campo de la cola, escriba "SETHEADER" y, a continuación, haga clic en **exportar**.  
  
12. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadro de diálogo.  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>Habilitar la ubicación de recepción e iniciar el puerto de envío  
 Este procedimiento habilita la ubicación de recepción e inicia el puerto de envío.  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>Para habilitar la ubicación de recepción e iniciar el puerto de envío  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.  
  
2.  En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.  
  
3.  En el panel de detalles, haga clic en el **SetMQHeader** puerto de envío y haga clic en **iniciar**.  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Este procedimiento comprueba la aplicación.  
  
#### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1.  Coloque un archivo en el **C:\Temp\Pickup3** carpeta.  
  
2.  Inicie WebSphere MQ Explorer y haga doble clic en la cola SETHEADER para examinar los mensajes de dicha cola.  
  
     Para ver todas las propiedades de contexto correspondientes a los mensajes de la cola SETHEADER, debe llevar a cabo los pasos siguientes:  
  
    1.  Haga doble clic en el **SETHEADER** cola para mostrar el **Message Browser** cuadro de diálogo.  
  
    2.  En el **Message Browser** cuadro de diálogo, haga clic en **columnas** para mostrar la **Show/Hide Columns for Messages** cuadro de diálogo.  
  
    3.  En **columnas disponibles**, haga doble clic en cada entrada para hacer que aparezca en el **Message Browser** cuadro de diálogo y, a continuación, haga clic en **Aceptar**.  
  
3.  Las propiedades de contexto de mensaje para cada mensaje deben estar visibles en el **Message Browser** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores de MQSeries](../core/mqseries-adapter-samples.md)