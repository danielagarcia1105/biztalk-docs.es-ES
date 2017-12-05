---
title: Habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF | Documentos de Microsoft
description: "Instalar ensamblados, configurar machine.config, agregar la extensión al administrador de BizTalk, crear ubicación de recepción para habilitar puntos de extensibilidad WCF para los adaptadores de WCF en BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2881ddd83ebeb31a9f5ff3da6ed858f158751d64
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a>Cómo habilitar los puntos de extensibilidad WCF con los adaptadores de WCF
Habilitar tres puntos de extensibilidad WCF: extensión de comportamiento, extensión de elemento de enlace y extensión de enlace, con los adaptadores de WCF-Custom y WCF-CustomIsolated. Para ello, primero instale los ensamblados que implementan los puntos de extensibilidad WCF en la caché de ensamblado global (GAC), a continuación, modifique el archivo machine.config de su equipo y configure el adaptador de WCF-Custom o el WCF-CustomIsolated mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
Vea [extensión de WCF](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf) para obtener más información sobre los puntos de extensibilidad WCF.
  
 
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. [Permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md) proporciona más información.  
  
## <a name="install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a>Instalar a ensamblados que implementan un punto de extensibilidad WCF en la GAC  
  
1.  Copie los ensamblados que implementan el punto de extensibilidad WCF a una carpeta en su equipo local.  
  
2.  Copie los ensamblados que utiliza el punto de extensibilidad WCF a una carpeta en su equipo local.  
  
3.  Iniciar el **símbolo del sistema de Visual Studio**.  
  
4.  Escriba el siguiente comando:  
  
     **Gacutil.exe /if "\<**  *ruta de acceso al archivo .dll del ensamblado*  **\>"**  
  
5.  Se instalará el ensamblado en la GAC, sobrescribiendo cualquier ensamblado existente con el mismo nombre.  
  
6.  En el símbolo del sistema [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], repita los pasos 4 y 5 en todos los ensamblados que copió en los pasos 1 y 2 de este procedimiento.  
  
7.  Si tiene varios [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución y administración, repita los pasos del 1 al 6 de este procedimiento en todos los equipos.  
  
    > [!NOTE]
    >  Para activar los puntos de extensibilidad WCF para los adaptadores de WCF, la instancia de host de BizTalk que ejecuta el adaptador debe poder cargar los ensambles en tiempo de ejecución en donde se implementan los puntos de extensibilidad WCF.  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-extension"></a>Configurar el archivo machine.config para una extensión de enlace de WCF  
  
1.  En un símbolo del sistema, vaya a la % FrameworkDir%\v4. Carpeta X.XXXXX\CONFIG y, a continuación, abra el **machine.config** archivo mediante el Bloc de notas.  
  
2.  En el Bloc de notas, si el archivo machine.config no tiene la  **\<system.serverModel\>\\< extensiones\>**  elementos, agregar los elementos dentro de la  **\<configuración\>**  elemento del archivo machine.config de archivo y, a continuación, agregue el  **\<bindingExtensions\>**  (elemento) para una extensión de enlace de WCF dentro de el  **\<system.serverModel\>\\< extensiones\>**  elementos. Por ejemplo, para habilitar una extensión de enlace personalizado, netHttpBinding, agregue el código siguiente dentro de la  **\<configuración\>**  elemento del archivo machine.config:  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
          <add name="netHttpBinding" type="Microsoft.Samples.Channels.NetHttpBindingCollectionElement, NetHttpBinding, Version=3.0.0.0, Culture=neutral, PublicKeyToken=5b637b51c4aaa2a8" />  
        </bindingExtensions>        
      </extensions>  
    </system.serviceModel>  
    ```  
  
    > [!NOTE]
    >  - Puede encontrar la información de los ensamblados que se va a registrar mediante el comando **gacutil /lr** *< assembly_name >*.  
    >  - Vea [bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions) en este elemento.
  
3.  Guarde el archivo machine.config en el Bloc de notas.  
  
4.  Si dispone de varios equipos en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y equipos de administración, repita los pasos del 1 al 3 de este procedimiento en todos los equipos.  
  
    > [!NOTE]
    >  Debe repetir estos pasos en todos los equipos de la infraestructura WCF para procesar el punto de extensibilidad WCF para la instancia de host de BizTalk y la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a>Configurar una extensión de enlace de WCF mediante la consola de administración de BizTalk  
  
1.  Abra **administración de BizTalk Server**.  
  
    > [!NOTE]
    >  Si la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya está abierta, reinicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  Si utiliza el adaptador de WCF-Custom, en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], expanda Configuración de plataforma e Instancias de host y, a continuación, reinicie la instancia de host de BizTalk que ejecuta el adaptador.  
  
3.  Si utiliza el adaptador de WCF-CustomIsolated, en la consola de administración de IIS, reinicie el grupo de aplicación asociado a la ubicación de recepción WCF.  
  
4.  Si desea configurar una ubicación de recepción para usar un punto de extensibilidad WCF, en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda  *\<aplicación de BizTalk\>* , expanda **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en  *\<ubicación de recepción\>*.  
  
    -   En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **tipo** lista desplegable, seleccione **WCF-Custom** o **WCF-CustomIsolated** Dependiendo del adaptador WCF que desea usar y, a continuación, haga clic en **configurar**.  
  
5.  Si desea configurar un puerto de envío para utilizar un punto de extensibilidad WCF, en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda  *\<aplicación de BizTalk\>* , expanda **puertos de envío**y, a continuación, en el panel derecho, haga doble clic en  *\<puerto de envío\>*.  
  
    -   En el **propiedades de puerto de envío** cuadro de diálogo, en la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
6.  En el cuadro de diálogo Propiedades de transporte, en la **enlace** ficha, seleccione la extensión de enlace y, a continuación, configure el resto de la configuración para el transporte.  
  
7.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, cierre todos los cuadros de diálogo abiertos haciendo clic en el **Aceptar** botones y, a continuación, asegúrese de que no hay mensajes de error y los registros de eventos erróneos aparecen.  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a>Configurar el archivo machine.config para una extensión de elemento de enlace de WCF  
  
1.  En un símbolo del sistema, vaya a la % FrameworkDir%\v4. Carpeta X.XXXXX\CONFIG y, a continuación, abra el **machine.config** archivo mediante el Bloc de notas.  
  
2.  En el Bloc de notas, si el archivo machine.config no tiene la  **\<system.serverModel\>\\< extensiones\>**  elementos, agregar los elementos dentro de la  **\<configuración\>**  elemento del archivo machine.config de archivo y, a continuación, agregue el  **\<bindingElementExtensions\>**  (elemento) para un elemento de enlace de WCF extensión de dentro de la  **\<system.serverModel\>\\< extensiones\>**  elementos. Por ejemplo, para habilitar una extensión de elemento de enlace personalizado, Droppingintercepto, agregue el código siguiente dentro de la  **\<configuración\>**  elemento del archivo machine.config:  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <bindingElementExtensions>  
          <add name="droppingInterceptor" type="Microsoft.ServiceModel.Samples.DroppingServerElement, MessageInterceptor, Version=0.0.0.0, Culture=neutral, PublicKeyToken=098514eef14aa34a"/>  
        </bindingElementExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
    > [!NOTE]
    > - Puede encontrar la información de los ensamblados que se va a registrar mediante el comando **gacutil /lr** *< assembly_name >*.  
    > - Vea [bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions) en este elemento.
  
3.  Guarde el archivo machine.config en el Bloc de notas.  
  
4.  Si dispone de varios equipos en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y equipos de administración, repita los pasos del 1 al 3 de este procedimiento en todos los equipos.  
  
    > [!NOTE]
    >  Debe repetir estos pasos en todos los equipos de la infraestructura WCF para procesar el punto de extensibilidad WCF para la instancia de host de BizTalk y la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a>Configurar una extensión de elemento de enlace de WCF mediante la consola de administración de BizTalk  
  
1.  Abra **administración de BizTalk Server**.  
  
    > [!NOTE]
    >  Si la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya está abierta, reinicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  Si utiliza el adaptador de WCF-Custom, en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], expanda Configuración de plataforma e Instancias de host y, a continuación, reinicie la instancia de host de BizTalk que ejecuta el adaptador.  
  
3.  Si utiliza el adaptador de WCF-CustomIsolated, en la consola de administración de IIS, reinicie el grupo de aplicación asociado a la ubicación de recepción WCF.  
  
4.  Si desea configurar una ubicación de recepción para usar un punto de extensibilidad WCF, en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda  *\<aplicación de BizTalk\>* , expanda **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en  *\<ubicación de recepción\>*.  
  
    -   En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **tipo** lista desplegable, seleccione **WCF-Custom** o **WCF-CustomIsolated** Dependiendo del adaptador WCF que desea usar y, a continuación, haga clic en **configurar**.  
  
5.  Si desea configurar un puerto de envío para utilizar un punto de extensibilidad WCF, en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda  *\<aplicación de BizTalk\>* , expanda **puertos de envío**y, a continuación, en el panel derecho, haga doble clic en  *\<puerto de envío\>*.  
  
    -   En el **propiedades de puerto de envío** cuadro de diálogo, en la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
6.  En el cuadro de diálogo Propiedades de transporte, en la **enlace** ficha la **BindingType** lista desplegable, seleccione **customBinding**.  
  
7.  En el cuadro de diálogo Propiedades de transporte, en la **enlace** pestaña, haga clic en el área cliente de la **enlace** lista y, a continuación, haga clic en **Agregar extensión**.  
  
8.  En el **Seleccionar extensión de elemento de enlace** cuadro de diálogo, seleccione una extensión de elemento de enlace y, a continuación, haga clic en **Aceptar**.  
  
9. En el cuadro de diálogo Propiedades de transporte, en la **enlace** ficha, ajuste el orden de los elementos de enlace que se agregó en el **enlace** lista según el tipo de la extensión de elemento de enlace que agregó en el paso anterior como sigue:  
  
    -   En el **enlace** lista, haga clic en una extensión de elemento de enlace y, a continuación, haga clic en **mover extensión hacia arriba** o **mover extensión hacia abajo**. La extensión de elemento de enlace más bajo en el **enlace** lista se corresponde con el componente de la parte inferior de la pila de canales. El elemento de enlace superior en el **enlace** lista corresponde al componente superior de la pila de comunicación.  
  
        > [!NOTE]
        >  Vea [enlaces personalizados](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings) para obtener más información acerca del orden de los elementos de enlace específico para el enlace personalizado.
  
10. En el cuadro de diálogo de propiedades de transporte, configure el resto de la configuración del transporte.  
  
11. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, cierre todos los cuadros de diálogo abiertos haciendo clic en el **Aceptar** botones y, a continuación, asegúrese de que no hay mensajes de error y los registros de eventos erróneos aparecen.  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a>Configurar el archivo machine.config para una extensión de comportamiento WCF  
  
1.  En un símbolo del sistema, vaya a la % FrameworkDir%\v4. Carpeta X.XXXXX\CONFIG y, a continuación, abra el **machine.config** archivo mediante el Bloc de notas.  
  
2.  En el Bloc de notas, si el archivo machine.config no tiene la  **\<system.serverModel\>\\< extensiones\>**  elementos, agregar los elementos dentro de la  **\<configuración\>**  elemento del archivo machine.config de archivo y, a continuación, agregue el  **\<behaviorExtensions\>**  elemento para una extensión de comportamiento WCF dentro de la  **\<system.serverModel\>\\< extensiones\>**  elementos. Por ejemplo, para habilitar una extensión de comportamiento personalizado, schemaValidator, agregue el código siguiente dentro de la  **\<configuración\>**  elemento del archivo machine.config:  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ad307e213604f592"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
    > [!NOTE]
    >  - Puede encontrar la información de los ensamblados que se va a registrar mediante el comando **gacutil /lr** *< assembly_name >*.  
    >  - Vea [behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions) en este elemento.
  
3.  Guarde el archivo machine.config en el Bloc de notas.  
  
4.  Si dispone de varios equipos en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y equipos de administración, repita los pasos del 1 al 3 de este procedimiento en todos los equipos.  
  
    > [!NOTE]
    >  Debe repetir estos pasos en todos los equipos de la infraestructura WCF para procesar el punto de extensibilidad WCF para la instancia de host de BizTalk y la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a>Configurar una extensión de comportamiento WCF mediante la consola de administración de BizTalk  
  
1.  Abra **administración de BizTalk Server**.  
  
    > [!NOTE]
    >  Si la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya está abierta, reinicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  Si utiliza el adaptador de WCF-Custom, en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], expanda Configuración de plataforma e Instancias de host y, a continuación, reinicie la instancia de host de BizTalk que ejecuta el adaptador.  
  
3.  Si utiliza el adaptador de WCF-CustomIsolated, en la consola de administración de IIS, reinicie el grupo de aplicación asociado a la ubicación de recepción WCF.  
  
4.  Si desea configurar una ubicación de recepción para usar un punto de extensibilidad WCF, en la consola de administración de BizTalk, expanda **grupo de BizTalk**, expanda  *\<aplicación de BizTalk\>* , expanda **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en  *\<ubicación de recepción\>*.  
  
    -   En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **tipo** lista desplegable, seleccione **WCF-Custom** o **WCF-CustomIsolated** Dependiendo del adaptador WCF que desea usar y, a continuación, haga clic en **configurar**.  
  
5.  Si desea configurar un puerto de envío para usar un punto de extensibilidad WCF, en la consola de administración de BizTalk, expanda **grupo de BizTalk**, expanda  *\<aplicación de BizTalk\>*, Expanda **puertos de envío**y, a continuación, en el panel derecho, haga doble clic en  *\<puerto de envío\>*.  
  
    -   En el **propiedades de puerto de envío** cuadro de diálogo, en la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
6.  En el cuadro de diálogo Propiedades de transporte, en la **comportamiento** pestaña, haga clic en **ServiceBehavior** o **EndpointBehavior** según el tipo de la extensión de comportamiento y, a continuación, en la **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione la extensión de comportamiento y, a continuación, haga clic en **Aceptar**.  
  
7.  En el cuadro de diálogo de propiedades de transporte, configure el resto de la configuración del transporte.  
  
8.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, cierre todos los cuadros de diálogo abiertos haciendo clic en el **Aceptar** botones y, a continuación, asegúrese de que no hay mensajes de error y los registros de eventos erróneos aparecen.  
  
## <a name="configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a>Configurar un WCF-Custom ubicación de recepción con un certificado SSL  
  
-   Si utiliza el controlador de modo kernel HTTP (HTTP.sys) como una ubicación de recepción WCF-Custom el **httpsTransport** elemento de enlace, para las comunicaciones de Secure Sockets Layer (SSL), la ubicación de recepción debe tener un certificado registrado para cada socket (combinación de dirección/puerto IP). Utilice la herramienta HttpCfg.exe para enlazar un certificado SSL con un puerto en el equipo. Para obtener más información, consulte [How To: configurar un puerto con un certificado SSL](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate).