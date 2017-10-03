---
title: Adaptador de HTTP (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4f443bf0b60f0bb90a914824b3922110ee1b300
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-biztalk-server-sample"></a>Adaptador de HTTP (ejemplo de BizTalk Server)
En el ejemplo de adaptador de HTTP se muestra cómo se implementan los paradigmas de comunicación de solicitud-respuesta y de petición-respuesta que se usan en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\AdaptersDevelopment\HttpAdapter\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|\Design-Time\Adapter Management|Contiene el proyecto que implementa la parte de tiempo de diseño de este adaptador.|  
|\Run-Time\HttpReceive|Contiene el proyecto que implementa la del patrón de comunicación del adaptador de solicitud-respuesta. Se trata de un receptor aislado.|  
|\Run-Time\HttpSend|Contiene el proyecto que implementa la del patrón de comunicación del adaptador de petición-respuesta.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 El propósito de este ejemplo es constituir un marco de trabajo que pueda usarse para el desarrollo de adaptadores personalizados. En algunos casos, es posible que BizTalk Server necesite transportar mensajes a una aplicación personalizada específica o usar un protocolo para el que no exista un adaptador nativo. Las compañías de terceros han escrito adaptadores compatibles con otros protocolos. Antes de decidirse a escribir un adaptador personalizado, puede que desee saber si ya hay un adaptador para el protocolo. Si no consigue encontrar un adaptador compatible para satisfacer los requisitos de comunicación, puede desarrollar un adaptador personalizado propio.  
  
 La escritura de un adaptador personalizado puede resultar todo un desafío. Para simplificar este proceso, Microsoft ha desarrollado una base denominada el marco de trabajo de adaptadores. Puede usar este marco de trabajo como base para el desarrollo junto con el código fuente de adaptador de ejemplo que se encuentra en el SDK de BizTalk Server.  Para obtener más información sobre adaptadores personalizados y el marco de trabajo, consulte la **Vea también** sección al final de este documento.  
  
## <a name="building-and-initializing-the-sample-adapter"></a>Crear e inicializar el adaptador de ejemplo  
  
> [!IMPORTANT]
>  Si la instalación de BizTalk es de 64 bits o se modifica la ubicación de la instalación, OutboundAssemblyPath, InboundAssemblyPath y AdapterMgmtAssemblyPath deben cambiarse según corresponda.  
  
#### <a name="to-build-and-initialize-the-http-adapter-sample"></a>Para crear e inicializar el ejemplo del adaptador de HTTP  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\HttpAdapter  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Compila el adaptador de HTTP y todas sus dependencias.  
  
    -   Crea una aplicación de Internet Information Services (IIS) que se usa para la recepción en el adaptador.  
  
 En IIS 7,0, debe asegurarse de que la identidad del grupo de aplicaciones que se ejecuta en esta aplicación de IIS es miembro de los grupos siguientes:  
  
-   Grupo de usuarios de hosts aislados de BizTalk.  
  
-   Grupo IIS_WPG.  
  
-   En IIS 7.0, debe migrar la aplicación para que funcione con el modo .NET integrado. Puede migrar la configuración de la aplicación, incluido el contenido de la \<httpHandlers > sección de configuración, con lo siguiente desde una ventana de línea de comandos (la ventana debe estar ejecutándose como administrador):  
  
    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  
  
-   Después de migrar la aplicación, se ejecutará en los modos .NET clásico e integrado, así como en plataformas de nivel inferior.  
  
> [!NOTE]
>  Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.  
  
> [!NOTE]
>  Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
> [!NOTE]
>  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="registering-the-sample-adapter"></a>Registrar el adaptador de ejemplo  
  
#### <a name="to-register-the-http-adapter-sample"></a>Para registrar el ejemplo de adaptador de HTTP  
  
1.  En el Explorador de Windows, vaya a la unidad de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, navegue hasta \<ruta de ejemplos > \AdaptersDevelopment\HTTPAdapter.  
  
2.  Para agregar el adaptador de ejemplo en el registro, haga doble clic en **HTTP.NET.reg**.  
  
    > [!NOTE]
    >  HTTP.NET.reg incluye las rutas de acceso codificadas para el directorio de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no instaló [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la ubicación predeterminada o si actualizó la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a partir de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], deberá modificar el archivo HTTP.NET.reg con las rutas apropiadas. Actualice las rutas asociadas a los valores "OutboundAssemblyPath" y "AdapterMgmtAssemblyPath" para que señalen la ubicación correcta de los archivos especificados.  
  
    > [!IMPORTANT]
    >  Si instala BizTalk en un equipo de 64 bits, cambie todas las instancias de la entrada de registro HKEY_CLASSES_ROOT\CLSID\ a HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ en el **HTTP.NET.reg** archivo de registro.  
  
3.  En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar**.  
  
4.  Para cerrar el Explorador de Windows, en la **archivo** menú, haga clic en **cerrar**.  
  
## <a name="installing-the-sample-adapter"></a>Instalar el adaptador de ejemplo  
  
#### <a name="to-install-the-http-adapter-sample"></a>Para instalar el ejemplo del adaptador de HTTP  
  
1.  Haga clic en el **iniciar** menú, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, seleccione **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] de árbol, a continuación, expanda el **grupo de BizTalk** de árbol, a continuación, expanda el **configuración de plataforma** árbol.  
  
3.  Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.  
  
4.  En el **propiedades del adaptador** diálogo cuadro, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Nombre|Tipo de **HTTP.NET**.|  
    |Adaptador|Seleccione **HTTP.NET** en la lista desplegable.|  
    |Description|Tipo de **ejemplo de adaptador de HTTP.NET**.|  
  
5.  Haga clic en **Aceptar**.  
  
6.  El adaptador aparece en la lista de adaptadores de la ventana derecha de la consola de administración de BizTalk Server.  
  
## <a name="stopping-and-restarting-the-host-instance"></a>Detener y reiniciar la instancia de host  
  
#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a>Para detener y reiniciar la instancia de host para el ejemplo de adaptador de HTTP  
  
1.  Haga clic en el **iniciar** menú, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y seleccione [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] de árbol, a continuación, expanda **configuración de plataforma**y haga clic en **instancias de Host**.  
  
3.  En el panel de resultados, haga clic en la instancia de host (normalmente, el nombre del equipo) y, a continuación, haga clic en **detener**.  
  
     El estado de la instancia de host cambia a **detenido**.  
  
4.  En el panel de resultados, haga clic en la instancia de host y, a continuación, haga clic en **iniciar**.  
  
 La aplicación ya puede utilizar el adaptador de HTTP.NET. Al configurar el adaptador, el formato para la **directorio Virtual** propiedades de transporte tiene el formato: /httpreceive/httpreceive.aspx?optionalQueryString.  
  
## <a name="comments"></a>Comentarios  
 El hace de adaptador HTTP.NET uso de las clases de BaseAdapter proporcionada en * \<ruta de ejemplos >*\AdaptersDevelopment\BaseAdapter\v1.0... 2\\. Las clases que se proporcionan en el proyecto BaseAdapter tienen como finalidad acelerar el desarrollo del adaptador. Vea los comentarios de código BaseAdapter para obtener más información acerca de las clases proporcionadas.  
  
## <a name="see-also"></a>Vea también  
 [Registrar un adaptador](../core/registering-an-adapter.md)   
 [Ejemplos de adaptadores - uso](../core/adapter-samples-usage.md)   
 [Desarrollar adaptadores personalizados](../core/developing-custom-adapters.md)   
 [¿Qué es el marco de trabajo?](../core/what-is-the-adapter-framework.md)   
 [Con las herramientas de marco de trabajo de adaptador](../core/using-the-adapter-framework-tools.md)   
 [Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Cómo implementar un adaptador personalizado](../core/how-to-deploy-a-custom-adapter.md)   
 [Sugerencias para diseñar un adaptador](../core/tips-for-designing-your-adapter.md)   
 [Configuración de tiempo de diseño de adaptador](../core/adapter-design-time-configuration.md)