---
title: (Ejemplo de BizTalk Server) del adaptador de archivo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de68c57c6b435f85edf630a7b224c5d58ffd0cd6
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="file-adapter-biztalk-server-sample"></a>Adaptador de archivo (ejemplo de BizTalk Server)
El ejemplo de adaptador de archivo está escrito en Microsoft Visual C# .NET para trabajar con Microsoft BizTalk Server. Proporciona código para construir un adaptador estático o dinámico.  Sin embargo, el siguiente procedimiento solo describe el adaptador estático. Un adaptador estático es un adaptador con un conjunto de esquemas estático y sin interfaz de usuario personalizada. Un adaptador dinámico tiene una interfaz de usuario personalizada y posiblemente un conjunto de esquemas dinámico. Tanto los adaptadores estáticos como los dinámicos utilizan el Asistente para agregar adaptador para agregar sus esquemas a un proyecto de BizTalk.  
  
> [!NOTE]
>  El ejemplo de adaptador de archivo no es el mismo que el adaptador de archivo nativo que se incluye con BizTalk Server. Por lo tanto, al seleccionar el tipo de transporte que se va a utilizar con este ejemplo seleccione “estático” en lugar de Archivo.  
  
 El adaptador dinámico, al tener una interfaz de usuario personalizada y posiblemente un conjunto de esquemas dinámico, requerirá código adicional en la administración del adaptador. Para entender mejor el uso de la configuración dinámica de esquemas, vea [configuración de adaptador de tiempo de diseño dinámico](../core/dynamic-design-time-adapter-configuration.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El adaptador de ejemplo copia archivos de una carpeta de archivos, los envía a BizTalk como mensajes o bien obtiene mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los coloca en una carpeta de archivos. Proporciona código para construir un adaptador dinámico o estático; sin embargo, el siguiente procedimiento sólo describe el adaptador estático. Un adaptador estático es un adaptador con un conjunto de esquemas estático y sin interfaz de usuario personalizada. Un adaptador dinámico tiene una interfaz de usuario personalizada y posiblemente un conjunto de esquemas dinámico. Tanto los adaptadores estáticos como los dinámicos utilizan el Asistente para agregar adaptador para agregar sus esquemas a un proyecto de BizTalk.  
  
 Puede utilizar el adaptador de archivo de ejemplo como una plantilla en la que crear otros adaptadores personalizados.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*\>**\AdaptersDevelopment\File adaptador**  
  
> [!NOTE]
>  La ubicación predeterminada de \< *ruta de ejemplos* \> es *% ProgramFiles %*\Microsoft BizTalk Server\SDK\Samples cuando BizTalk Server está instalado en un equipo que ejecuta 32 bits versión de Windows. La ubicación predeterminada de \< *ruta de ejemplos* \> es *ProgramFiles(x86) %*\Microsoft BizTalk Server\SDK\Samples cuando BizTalk Server se instala en un equipo que ejecuta un 64 - versión de bits de Windows. Para determinar los valores asociados a la *% ProgramFiles %* o *ProgramFiles(x86) %* tipo de las variables de entorno **echo % ProgramFiles %** o **echo % % De ProgramFiles(x86)** en un símbolo del sistema y presione ENTRAR. Si ejecuta este ejemplo en un sistema operativo de 64 bits, debe cambiar todas las referencias en cualquiera de los archivos .reg de **% ProgramFiles %** a **ProgramFiles(x86) %** antes de ejecutar estos archivos.  
  
 En las siguientes tablas se enumeran los archivos del ejemplo y se describe el propósito de cada uno.  
  
|Archivos de \File Adapter|Description|  
|--------------------------|-----------------|  
|Archivos de \BizTalk Project|Contiene el proyecto de instrumento de adaptador que se utiliza para probar el adaptador de ejemplo.|  
|Archivos de \Design Time|Contiene el tiempo de diseño y el proyecto de administración (AdapterManagement.csproj).|  
|Archivos de \Runtime|Contiene los proyectos de recepción y transmisión de copia de archivos en tiempo de ejecución (DotNetFile.csproj).|  
|DynamicAdapterManagement.reg|Registra el adaptador dinámico de ejemplo.|  
|Instance.xml|Archivo de ejemplo para pasar a través del adaptador de archivo.|  
|StaticAdapterManagement.reg|Registra el adaptador estático de ejemplo.|  
  
|Archivos de \BizTalk Project\Adapter Harness|Description|  
|----------------------------------------------|-----------------|  
|AdapterHarness.odx, AdapterHarness.sln y AdapterHarnessProject.btproj|Proporciona archivos de proyecto, de solución y archivos relacionados para el proyecto de BizTalk.|  
|mySchema.xsd|Proporciona el esquema Instance.xml que espera la orquestación de instrumento de la parte de recepción del adaptador, así como el esquema Instance.xml que la orquestación entrega a la parte de envío del adaptador.|  
  
|Archivos de \Design Time\Adapter Management|Description|  
|---------------------------------------------|-----------------|  
|AdapterManagement.cs, AdapterManagement.csproj y AdapterManagement.sln|Archivos de proyecto, de solución y archivos relacionados para el tiempo de diseño del adaptador.|  
|AssemblyInfo.cs|Contiene información de ensamblado de este ejemplo.|  
|CategorySchema2.xml|No lo utiliza el adaptador de ejemplo.|  
|CategorySchema.xml|Contiene el árbol de organización de servicio del adaptador estático.|  
|DotNetFileResource.resx|Contiene recursos.|  
|ReceiveHandler.xsd, ReceiveLocation.xsd|Contiene el controlador de recepción y esquemas de propiedades personalizadas de extremos|  
|service1.wsdl|Contiene definiciones de operación del adaptador.|  
|TransmitHandler.xsd, TransmitLocation.xsd|Contiene el controlador de transmisión y esquemas de propiedades personalizadas de extremos|  
  
|Archivos de \Runtime|Description|  
|---------------------|-----------------|  
|DotNetFile.csproj y DotNetFile.sln<br /><br /> AssemblyInfo.cs,<br /><br /> DotNetFileExceptions.cs, DotNetFileProperties.cs, DotNetFileReceiver.cs, DotNetFileReceiverEndPoint.cs, DotNetFileTransmitter.cs,<br /><br /> DotNetFileTransmitterEndpoint.cs,<br /><br /> DotNetFileAsyncTransmitterBatch.cs<br /><br /> BatchMessage.cs|Archivos para los adaptadores de recepción y envío de copias de archivo en tiempo de ejecución. Puede modificar estos archivos y guardarlos con un nombre nuevo para los componentes personalizados.<br /><br /> DotNetFile.csproj y DotNetFile.sln son los archivos de proyecto y solución.<br /><br /> AssemblyInfo.cs contiene información de ensamblado de este ejemplo.<br /><br /> DotNetFileReceiver.cs lee los archivos de las ubicaciones de recepción y los envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].<br /><br /> DotNetFileExceptions.cs implementa código para controlar excepciones durante el procesamiento de mensajes.<br /><br /> DotNetFileProperties.cs contiene propiedades comunes tanto para las operaciones de envío como de recepción<br /><br /> BatchMessage.cs implementa la mensajería de lotes.<br /><br /> DotNetFileReceiverEndPoint.cs es una clase que corresponde a una ubicación de recepción/URI.  Controla el sondeo de la carpeta dada para obtener mensajes nuevos.<br /><br /> DotNetFileTransmitter.cs es una clase singleton para el adaptador de envío DotNetFile. Todos los mensajes que vayan a diferentes puertos de envío de este tipo de adaptador pasan a través de esta clase.<br /><br /> DotNetFileTransmitterEndpoint.cs controla los mensajes de transmisión.|  
  
|Archivos de \SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2|Description|  
|--------------------------------------------------------------------|-----------------|  
|Adapter.cs, AdapterException.cs, AsyncTransmitter.cs, batch.cs, ConfigProperties.cs, ControlledTermination.cs, IManageEndpoints.cs, Receiver.cs y ReceiverEndpoint.cs|Proporciona las clases que constituyen el adaptador base. Puede utilizarlos para crear sus propios adaptadores.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Utilice el adaptador de archivo de ejemplo como una plantilla para crear otros adaptadores personalizados.  
  
## <a name="building-this-sample"></a>Generar este ejemplo  
  
> [!IMPORTANT]
>  Si la instalación de BizTalk es de 64 bits o se modifica la ubicación de la instalación, OutboundAssemblyPath, InboundAssemblyPath y AdapterMgmtAssemblyPath deben cambiarse según corresponda.  
  
 Utilice los procedimientos siguientes para generar e inicializar el ejemplo de adaptador de archivo.  
  
#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a>Para crear una clave de nombre seguro para los proyectos DotNetFileAdapter y el proyecto de adaptador base  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
    > [!NOTE]
    >  Ejecute el símbolo del sistema como administrador.  
  
2.  Cambie el directorio actual a la \< *ruta de ejemplos*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2** directory.  
  
3.  En el símbolo del sistema, escriba **sn – k BaseAdapter.snk** y, a continuación, presione ENTRAR. Es posible que este archivo .snk exista ya como resultado de la ejecución con anterioridad de otros ejemplos. Si es así, puede ir directamente al paso 4 y saltarse éste.  
  
4.  Cambie el directorio actual a la \< *ruta de ejemplos*\>\\**AdaptersDevelopment\File Adapter\Runtime** directory.  
  
5.  En el símbolo del sistema, escriba **sn – k DotNetFileAdapter.snk** y, a continuación, presione ENTRAR.  
  
6.  En el símbolo del sistema, escriba **salir** y, a continuación, presione ENTRAR para cerrar la ventana de símbolo del sistema.  
  
#### <a name="to-build-the-receiver-run-time-project"></a>Para crear el proyecto en tiempo de ejecución del receptor  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.  
  
2.  Navegue hasta la \< *ruta de ejemplos*\>**"\AdaptersDevelopment\File Adapter\Runtime"** directorio y, a continuación, haga doble clic en **DotNetFile.sln**.  
  
3.  Para volver a crear el proyecto de tiempo de ejecución de receptor de adaptador, en el Explorador de soluciones, haga clic en **DotNetFile**y, a continuación, haga clic en **volver a generar**.  
  
4.  Desde el **archivo** menú, haga clic en **Exit** para cerrar Visual Studio.  
  
#### <a name="to-build-the-adapter-design-time-project"></a>Para crear el proyecto en tiempo de diseño del adaptador  
  
1.  En el Explorador de Windows, navegue hasta la \< *ruta de ejemplos*\>**"\AdaptersDevelopment\File Adapter\Design Time\Adapter Management"** directorio y, a continuación, haga doble clic en **Y AdapterManagement.sln**.  
  
2.  En el Explorador de soluciones, haga clic en **AdapterManagement**y, a continuación, haga clic en **volver a generar**.  
  
3.  Desde el **archivo** menú, haga clic en **Exit** para cerrar Visual Studio.  
  
#### <a name="to-register-the-sample-static-adapter"></a>Para registrar el adaptador estático de ejemplo  
  
1.  En el Explorador de Windows, navegue hasta la \< *ruta de ejemplos*\>**"\AdaptersDevelopment\File adaptador"** directory.  
  
2.  Para agregar el adaptador de ejemplo en el registro, haga doble clic en **StaticAdapterManagement.reg**.  
  
    > [!NOTE]
    >  StaticAdapterManagement.reg incluye rutas codificadas de forma rígida en C:\Program Files\Microsoft BizTalk Server\\. Si no ha instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el %ProgramFiles%\Microsoft BizTalk Server\ directorio, si ha actualizado la instalación de BizTalk Server de BizTalk Server 2009 o BizTalk Server 2006 R2, o si ha instalado BizTalk Server en un equipo que ejecuta un versión de 64 bits de Windows, debe modificar el archivo StaticAdapterManagement.reg con las rutas apropiadas. De forma predeterminada, el servidor BizTalk Server está instalado en el % ProgramFiles(x86) %\Microsoft BizTalk Server\ directorio en los equipos que ejecutan una versión de 64 bits de Windows. Actualice las rutas asociadas a los valores "InboundAssemblyPath", "OutboundAssemblyPath" y "AdapterMgmtAssemblyPath" para que señalen la ubicación correcta de los archivos especificados.  
  
    > [!IMPORTANT]
    >  Si instala BizTalk en un equipo de 64 bits, cambie todas las instancias de la entrada de registro HKEY_CLASSES_ROOT\CLSID\ a HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ en el **StaticAdapterManagement.reg** archivo de registro.  
  
3.  En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar**.  
  
4.  Para cerrar el Explorador de Windows, en la **archivo** menú, haga clic en **cerrar**.  
  
#### <a name="to-install-the-sample-static-adapter"></a>Para instalar al adaptador estático de ejemplo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, seleccione **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk**y haga clic para expandir **configuración de plataforma**.  
  
3.  Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.  
  
4.  En el **agregar adaptador** diálogo cuadro, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **estático**.|  
    |**Adaptador**|Seleccione **DotNetFile estático** en la lista desplegable.|  
    |**Comentario**|Tipo de **adaptador de ejemplo**.|  
  
5.  Haga clic en **Aceptar**.  
  
     El adaptador estático aparece ahora en la lista de adaptadores en la ventana derecha de la consola de administración de BizTalk.  
  
#### <a name="to-stop-and-restart-the-host-instance"></a>Para detener y reiniciar la instancia de host  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y seleccione **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk**, haga clic para expandir **configuración de plataforma** y haga clic en **instancias de Host**. Seleccione BizTalkServerApplication en el panel de la derecha.  
  
3.  En el panel de resultados, haga clic en la instancia de host (normalmente, el nombre del equipo) y, a continuación, haga clic en **reiniciar**.  
  
### <a name="running-this-sample"></a>Ejecución del ejemplo  
  
##### <a name="to-run-the-file-adapter-sample"></a>Para ejecutar el ejemplo del adaptador de archivo  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.  
  
2.  Cree las siguientes carpetas en la unidad de instalación de BizTalk Server:  
  
    -   *\<drive\>*:**\Temp**  
  
    -   *\<drive\>*:**\Temp\Send**  
  
    -   *\<drive\>*:**\Temp\Receive**  
  
3.  Para cerrar el Explorador de Windows, en la **archivo** menú, haga clic en **cerrar**.  
  
4.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
5.  Haga clic en el **administración de BizTalk Server** nodo y seleccione **conectar a grupo existente**.  
  
6.  En el **conectarse a base de configuración de servidor de BizTalk existente** diálogo cuadro, realice lo siguiente.  
  
    > [!NOTE]
    >  La base de datos de administración de BizTalk también se denomina la base de datos de configuración de BizTalk.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**SQL Server**|Tipo de **.** (un punto).|  
    |**Base de datos**|Seleccionar el nombre de la base de datos de administración de BizTalk que creó el Asistente para configuración. El nombre de base de datos predeterminado utilizado por el Asistente para configuración es **BizTalkMgmtDb**.|  
  
7.  Haga clic en **Aceptar**.  
  
8.  Expanda el **grupo de BizTalk [*nombre del servidor*]** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda el **aplicaciones** nodo, expanda el  **BizTalk Application 1** nodo.  
  
9. Haga clic en el **puertos de envío** nodo y, a continuación, haga clic en **New**, seleccione **puerto de envío unidireccional estático**y, a continuación, haga clic en **Aceptar**.  
  
10. En el **propiedades de puerto de envío** cuadro de diálogo, seleccione **General**, y realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **AdapterSend**.|  
    |**Tipo de transporte**|Seleccione **estático** desde la lista desplegable y haga clic en **configurar**.<br /><br /> -En el **directorio** , escriba ***\<unidad\>*:\Temp\Send**.<br />-En el **modo de archivo** cuadro, seleccione **CreateNew**.<br />-En el **nombre de archivo** , escriba **%MessageID%.xml**.<br />-Haga clic en **Aceptar**.<br />-El **URI** campo debería mostrar ***\<unidad\>*:\Temp\Send\\%MessageID%.xml**.|  
    |**Canalización de envío**|Seleccione **PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**y, a continuación, haga clic en **Aceptar**.|  
  
11. En el **BizTalk Application 1** nodo haga clic en **puertos de recepción**y seleccione **puerto de recepción unidireccional / nueva**.  
  
12. En el **crear nuevo puerto de recepción** cuadro de diálogo, en la **especificar el tipo de puerto de recepción** cuadro, seleccione **puerto de recepción unidireccional** en la lista desplegable lista y, a continuación, haga clic en  **Aceptar**.  
  
13. En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** , escriba **AdapterReceive**y, a continuación, haga clic en **Aceptar**.  
  
14. En el **BizTalk Application 1** haga clic en el nodo **ubicaciones de recepción**y seleccione **ubicación de recepción unidireccional / nueva**.  
  
15. En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione **AdapterReceive** , a continuación, haga clic en **Aceptar**.  
  
16. En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **AdapterReceiveLocation**|  
    |**Tipo de transporte**|Seleccione **estático** desde la lista desplegable y presione **configurar** para tener acceso a las propiedades restantes.|  
    |**URI**|-Haga clic en el botón de puntos suspensivos (**...** ).<br />-En el **número Of Files In Batch** , escriba **20**.<br />-En el **directorio** , escriba ***\<unidad\>*:\Temp\Receive**.<br />-Asegúrese de que el **máscara de archivo** propiedad está establecida en  **\*.xml**.<br />-En el **intervalo de sondeo** , escriba **5**y haga clic en **Aceptar**.<br />-Asegúrese de que el **URI** etiqueta contiene ***\<unidad\>*:\Temp\Receive\\\*.xml**.|  
    |**Controlador de recepción**|Seleccione **BizTalkServerApplication** en la lista desplegable.|  
    |**Canalización de recepción**|Seleccione **XMLReceive** en la lista desplegable.|  
  
17. Haga clic en **Aceptar**.  
  
     Continúe con *crear, implementar y enlazar el adaptador de ejemplo*.  
  
### <a name="building-deploying-and-binding-the-sample-adapter"></a>Generar, implementar y enlazar el adaptador de ejemplo  
 Antes de que se active el adaptador, debe generar el proyecto, enlazar la orquestación con los puertos y dar de alta el adaptador.  
  
##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a>Para crear una clave de nombre seguro para el adaptador estático  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  En el símbolo del sistema, cambie el directorio actual a la \< *ruta de ejemplos*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter instrumento** directory.  
  
3.  En el símbolo del sistema, escriba **sn – k AdapterHarness.snk**y presione ENTRAR.  
  
4.  Haga clic en **Aceptar**.  
  
##### <a name="to-build-the-adapter-harness-project"></a>Para crear el proyecto de instrumento de adaptador  
  
-   En el Explorador de soluciones, haga clic en **AdapterHarnessProject**y, a continuación, haga clic en **volver a generar**.  
  
##### <a name="to-deploy-the-adapter-harness-project"></a>Para implementar el proyecto de instrumento de adaptador  
  
1.  En el Explorador de soluciones, cuando se vuelve a generar el proyecto, haga clic en **AdapterHarnessProject**y, a continuación, haga clic en **implementar**.  
  
2.  En la consola de administración de BizTalk Server, seleccione el proyecto ha implementado y, a continuación, haga clic en **actualizar**.  
  
##### <a name="to-bind-the-orchestration-with-the-ports"></a>Para enlazar la orquestación con los puertos  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la correspondiente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, expanda la **orquestaciones** nodo.  
  
2.  Haga clic en **AdapterHarness.AdapterHarnessType**y, a continuación, haga clic en **enlazar**.  
  
3.  En el **propiedades de enlace de puerto - AdapterHarness.AdapterHarnessType: configuraciones de enlace** diálogo cuadro, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**AdapterFileReceivePort**|Seleccione **AdapterReceive** en la lista desplegable.|  
    |**AdapterFileSendPort**|Seleccione **AdapterSend** en la lista desplegable.|  
  
4.  En el panel izquierdo, haga clic en **Host**.  
  
5.  En el **Host** cuadro, seleccione **BizTalkServerApplication** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
 Continúe con *administrar el adaptador de ejemplo*.  
  
### <a name="administering-the-sample-adapter"></a>Administrar el Adaptador de ejemplo  
 Complete las tareas de administración para el adaptador de ejemplo en la consola de Administración de BizTalk.  
  
##### <a name="to-administer-the-file-adapter-sample"></a>Para administrar el ejemplo del adaptador de archivo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el panel izquierdo, haga clic para expandir **aplicaciones**, haga clic para expandir **BizTalk Application 1**y haga clic en **ubicaciones de recepción**.  
  
3.  Asegúrese del **AdapterReceive** estado es **habilitado**.  
  
     Si el estado no es **habilitado**, haga clic en **AdapterReceive** en el panel derecho y, a continuación, haga clic en **habilitar**.  
  
4.  En el panel izquierdo, haga clic en **orquestaciones** y asegúrese de que **AdapterHarness.AdapterHarnessType** es **dado de alta**. Haga clic en **AdapterHarness.AdapterHarnessType**y, a continuación, haga clic en **dar de alta** (si AdapterHarness.AdapterHarnessType ya está inscrito, el **dar de alta** es la opción de menú no está disponible).  
  
5.  Haga clic en **AdapterHarness.AdapterHarnessType** y seleccione **iniciar**. El estado de esta orquestación debería cambiar a **ejecutando**.  
  
 Continúe con *probar el adaptador de ejemplo*.  
  
### <a name="testing-the-sample-adapter"></a>Probar el adaptador de ejemplo  
 Una vez que haya implementado el adaptador de ejemplo, debe detener y reiniciar la instancia de host. Es fundamental que pruebe el adaptador de ejemplo antes de colocarlo en producción.  
  
##### <a name="to-stop-and-restart-the-host-instance"></a>Para detener y reiniciar la instancia de host  
  
1.  En el **administración de BizTalk Server** consola, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk**, haga clic para expandir  **Configuración de plataforma** y haga clic en **instancias de Host**. Seleccione BizTalkServerApplication en el panel de la derecha.  
  
2.  Haga clic en la instancia de host (normalmente, el nombre del equipo) y, a continuación, haga clic en **detener**.  
  
     El estado de la instancia de host cambia a **detenido**.  
  
3.  Haga clic en la instancia de host y, a continuación, haga clic en **iniciar**.  
  
     El estado de la instancia de host cambia a **ejecutando**.  
  
##### <a name="to-test-the-sample-static-adapter-runtime"></a>Para probar el adaptador estático de ejemplo en tiempo de ejecución  
  
1.  En el Explorador de Windows, navegue hasta la \< *ruta de ejemplos*\>**\AdaptersDevelopment\File adaptador** directorio y copie el archivo InstanceXML.xml en el Portapapeles.  
  
2.  Vaya a  *\<unidad\>*:**\Temp\Receive** y pegue el archivo Instance.xml en la carpeta.  
  
     Si la transmisión y recepción trabajan adaptadores, debe mover el archivo de la  *\<unidad\>*:**\Temp\Receive** carpeta a la  *\<unidad \>* :**\Temp\Send** carpeta.  
  
##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a>Para probar la funcionalidad del Asistente para agregar adaptador de ejemplo del adaptador estático de ejemplo  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **AdapterHarnessProject**, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados - AdapterHarnessProject** cuadro de diálogo, haga clic en **agregar metadatos de adaptador**y, a continuación, haga clic en **abiertos**.  
  
     Aparecerá la lista de adaptadores registrados.  
  
3.  Seleccione **DotNetFile estático**y, a continuación, haga clic en **siguiente**.  
  
     Aparecerá la organización de servicio que ha expuesto el adaptador.  
  
4.  Expanda **Service Organization**, **sanitaria**y, a continuación, haga clic en **administración**.  
  
     Tenga en cuenta que **elegibilidad** muestra de forma diferente de los demás nodos. **Elegibilidad** es un nodo de servicio que se puede seleccionar. El resto de nodos son nodos de organización que no describen ningún servicio específico.  
  
5.  Seleccione el **elegibilidad** nodo y, a continuación, haga clic en **finalizar**.  
  
     BizTalk importa un archivo .odx y uno .xsd en el proyecto.  
  
     Ahora puede utilizar esquemas, PortTypes, operaciones y MessageTypes que se han importado desde el adaptador a la programación del proyecto de BizTalk.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos utilizados en este ejemplo  
 Interfaces: IBaseMessage, IPropertyBag, IBTTransportProxy  
  
 Clases (del adaptador base): AsyncTransmitterEndpoint, AsyncTransmitter, BatchMessage, ControlledTermination, ReceiverEndpoint, DotNetFileCommonProperties, BatchOperationType  
  
### <a name="comments"></a>Comentarios  
 Una vez finalizado el adaptador de ejemplo, puede modificar el adaptador de ejemplo para crear un adaptador personalizado estático o dinámico para obtener más información, consulte [configuración de tiempo de diseño de adaptador](../core/adapter-design-time-configuration.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores - uso](../core/adapter-samples-usage.md)   
 [Registro de un adaptador](../core/registering-an-adapter.md)