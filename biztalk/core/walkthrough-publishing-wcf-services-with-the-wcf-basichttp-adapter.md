---
title: 'Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorials, publishing
- WCF adapters, tutorials
- publishing, WCF services
- WCF-BasicHttp adapters, tutorials
- publishing, tutorials
- WCF services, publishing
- tutorials, WCF adapters
ms.assetid: 43b76215-9cb0-47ab-a085-c4cf265410f9
caps.latest.revision: "72"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8915c298160f53ea21c62bc6f44d51aec36cdf94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter"></a>Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp
## <a name="introduction"></a>Introducción  
 En este tutorial se publica un Servicio [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] como una orquestación de BizTalk mediante el adaptador de WCF-BasicHttp y el Asistente para publicación de Servicio WCF de BizTalk. Una orquestación de BizTalk aparece a un cliente externo, por ejemplo, otro servicio web o aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], como Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] al exponer un extremo [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mediante el adaptador de WCF-BasicHttp. El adaptador de WCF-BasicHttp se compone tanto de un adaptador de envío como de uno de recepción. En este ejemplo, solo usará el lado de recepción de este adaptador para recibir peticiones de servicio WCF a través del protocolo HTTP o HTTPS desde aplicaciones cliente de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
 El adaptador de WCF-BasicHttp usa la **BasicHttpBinding** enlace para proporcionar una implementación de pila de protocolos o transporte compatible con la versión inicial de los servicios Web para que actúe como un puente entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]funcionalidad. Proporciona comunicación con servicios y clientes web basados en ASMX compatibles con el perfil básico de servicios web WS-I, versión 1.1 mediante el transporte HTTP o HTTPS con codificación de texto. Mediante el adaptador BasicHttp de WCF, no podrá usar las características avanzadas de comunicación web compatibles con los protocolos WS-*. Para ello, use el adaptador WCF-WSHttp.  
  
 En este tutorial se muestra el modo de crear una ubicación de recepción WCF-BasicHttp para publicar una orquestación como Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  Configurará servicios de Internet Information Services (IIS) para proporcionar hospedaje aislado de dicho Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  Una aplicación de cliente de ejemplo llama a la orquestación de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicada como un ejemplo de cómo un cliente externo puede llamar al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicado en Internet para usar su funcionalidad.  
  
 Cuando concluya el tutorial, comprenderá cómo se realizan las tareas siguientes:  
  
-   En Visual Studio, use la **implementar** comando para implementar la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio en forma de una orquestación de BizTalk en un ensamblado de BizTalk a una instancia local de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La implementación desde Visual Studio crea una aplicación de BizTalk que se rellena con los ensamblados que contienen recursos, tales como orquestaciones, canalizaciones, esquemas y asignaciones que se usarán en la solución de BizTalk.  
  
-   Una vez que se haya implementado, la orquestación de BizTalk estará disponible para la configuración y control a través de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este tutorial configurará la ubicación de recepción WCF-BasicHttp para aceptar los mensajes de entrada enviados al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] que el Asistente para publicación de Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de BizTalk. El host aislado de BizTalk aloja la ubicación de recepción como un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] para obtener las solicitudes entrantes.  
  
> [!NOTE]
>  En este tutorial, usará el Asistente para publicación de Servicio WCF de BizTalk o el Asistente para publicación de servicio web de BizTalk para publicar orquestaciones y esquemas de BizTalk como Servicios de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] con los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Para publicar orquestaciones y esquemas como servicios Web con el adaptador de SOAP, use la **Asistente para publicación de WCF de BizTalk** o **Asistente para publicación de BizTalk Web Services**.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los pasos descritos en este ejemplo, asegúrese de que el entorno instala los siguientes requisitos previos:  
  
-   El equipo que genera los ensamblados y ejecuta el proceso de implementación tanto el equipo que ejecuta el ejemplo requieren Microsoft Windows Server 2008 SP2 o Windows Server 2008 R2, Microsoft .NET Framework 4 y Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
-   El equipo que se usa para generar los ensamblados y ejecutar el proceso de implementación requiere Microsoft Visual Studio.  
  
-   El equipo que ejecuta el ejemplo requiere los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y las herramientas de administración de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Se trata de opciones de instalación durante la instalación de Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
-   En los equipos que use para realizar las tareas administrativas, debe ejecutar una cuenta de usuario que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar los parámetros de aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta cuenta de usuario también debe ser miembro del grupo de administradores local para la implementación de la aplicación, la administración de las instancias de host y otras tareas que puedan ser necesarias.  
  
-   En cualquier equipo que requiera [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] capacidad, complete el procedimiento de instalación única para la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejemplos en [http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510).  
  
-   En el equipo que ejecuta el ejemplo e importa un enlace o un archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de que el host no es un host de confianza. De lo contrario, se producirá un error en la importación.  
  
-   Debe descargar el código del tutorial y extraerlo en el equipo. Este tutorial es una parte de todo el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] paquete de tutoriales del adaptador. Puede descargar el archivo **WCFAdapterWalkthroughs.exe** desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Developer Center en [http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140).  
  
### <a name="to-deploy-the-sample-biztalk-solution-biztalkapp"></a>Para implementar la solución de BizTalk de ejemplo, BizTalkApp  
  
1.  Ejecutar la extracción automática **WCFBasicHttpReceiveAdapter.exe** de archivos y extraiga los archivos en el **C:\WCFBasicHttpReceiveAdapter** carpeta.  
  
2.  En Microsoft Visual Studio, abra el **C:\WCFBasicHttpReceiveAdapter\WCFBasicHttpReceiveAdapter.sln** archivo.  
  
3.  El **Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp** ensamblado contiene un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orquestación, un mapa y dos esquemas. Debe instalarse en la GAC y necesita una clave de nombre seguro archivará para que esto se produzca. Haga clic en el **BizTalkApp** del proyecto y, a continuación, haga clic en **propiedades**. En el **propiedades** página, haga clic en **firma**y seleccione **firmar el ensamblado**. Haga clic en la flecha hacia abajo en la **elegir un archivo de clave de nombre seguro** la lista desplegable, haga clic en  **\<nuevo >**y escriba `keyfile.snk` en el **nombre de archivo de clave** cuadro de texto . Desactive la opción **proteger mi archivo de clave con una contraseña**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de soluciones, haga clic en el **BizTalkApp** del proyecto y, a continuación, haga clic en **volver a generar**.  
  
    > [!NOTE]
    >  No intente una **generar solución**, o para crear el **WCFClient** aplicación en este momento. El **WCFClient** no está listo para compilarse en este punto en el ejemplo.  
  
5.  Expanda **BizTalkApp**y, a continuación, abra **DeliveryProcess.odx** para revisar. La orquestación toma una solicitud [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] a través de HTTP con el adaptador WCF-BasicHttp. Modifica la solicitud mediante una asignación de transformación y envía la respuesta de nuevo mediante el mismo adaptador de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
    1.  Esta orquestación tiene un puerto de solicitud-respuesta lógico que se publicará con el adaptador de WCF-BasicHttp. Se enlazará a un puerto físico en un paso posterior.  
  
    2.  Haga clic en el nodo superior del **DeliveryProcess.odx** en la ventana del diseñador y, a continuación, seleccione **propiedades**. Asegúrese de que el **modificador de tipo** propiedad del tipo de puerto es **público**.  
  
6.  En el Explorador de soluciones, haga clic en **BizTalkApp**y, a continuación, haga clic en **propiedades**.  
  
    1.  Si la base de datos de administración de BizTalk no se hospeda localmente, modifique la **Server** propiedad si utiliza un servidor de base de datos diferente. Haga clic en el **implementación** ficha y, a continuación, modifique la **Server** propiedad para que apunte al servidor de base de datos.  
  
    2.  Asegúrese de que el **nombre de la aplicación** propiedad está establecida en **WCFBasicHttpReceiveAdapter**. Se trata del nombre de la aplicación de BizTalk en la que se va a implementar la solución de BizTalk.  
  
    3.  En el Explorador de soluciones, haga clic en **BizTalkApp**y, a continuación, haga clic en **implementar**. Si no se implementa de forma local, es posible que sea necesario configurar el servidor SQL Server para permitir conexiones remotas. Para obtener más información, consulte [http://go.microsoft.com/fwlink/?LinkId=194141](http://go.microsoft.com/fwlink/?LinkId=194141).  
  
### <a name="to-publish-the-sample-orchestration-by-using-the-biztalk-wcf-service-publishing-wizard"></a>Para publicar la orquestación de ejemplo mediante el Asistente para publicación de Servicio WCF de BizTalk  
  
1.  En este paso, ejecutará el ensamblado de orquestación recién implementado y lo publica como un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Para ello, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente de publicación de servicio de WCF de BizTalk** .  
  
2.  En el **éste es el Asistente para publicación de servicio WCF de BizTalk** página, haga clic en **siguiente**.  
  
3.  En el **tipo de servicio WCF** página, lleve a cabo las siguientes acciones para especificar el tipo de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio para publicar y los extremos de BizTalk para recibir [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mensajes y, a continuación, haga clic en **siguiente**:  
  
    1.  Seleccione el **punto de conexión de servicio** opción, que establece que publicará un [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio desde una orquestación en un ensamblado. Seleccione **WCF-BasicHttp** desde el **nombre de adaptador (tipo de transporte)** lista desplegable.  
  
    2.  Seleccione el **habilitar extremo de metadatos** casilla de verificación para realizar la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] hospedado por IIS de ubicación de recepción publicar sus [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] metadatos del servicio. Al seleccionar esta casilla de verificación establece el **httpGetEnabled** atributo de la \< **serviceMetadata**> elemento `true` en el archivo Web.Config. Estos metadatos se recuperan cuando una solicitud HTTP/GET los solicita. Después, usará la herramienta SvcUtil.exe para obtener estos datos con el fin de generar una clase de proxy para el código de cliente para llamar al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
    3.  Seleccione el **ubicaciones de recepción de BizTalk crea en la siguiente aplicación** opción para crear los puertos de recepción y las ubicaciones correspondientes a cada archivo .svc generado para el adaptador de WCF-BasicHttp. Elija el nombre de la aplicación de BizTalk, **WCFBasicHttpReceiveAdapter**, donde los puertos de recepción y las ubicaciones se genera y, a continuación, haga clic en **siguiente**.  
  
         El asistente crea un archivo de enlace, Binding.XML, para representar ubicaciones de recepción asociadas. El archivo se encuentra en el directorio web y después se puede importar manualmente a través de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
        > [!NOTE]
        >  Si no selecciona una aplicación de BizTalk implementada, se seleccionará la aplicación predeterminada.  
  
4.  En el **crear servicio WCF** página, seleccione **publicar orquestaciones de BizTalk como servicio WCF**y, a continuación, haga clic en **siguiente**. Esto publicará la orquestación especificada en el siguiente paso como un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
5.  Seleccione el ensamblado que contiene la orquestación que se va a publicar. En el **ensamblado de BizTalk** página, en la **archivo de ensamblado de BizTalk (\*.dll)** cuadro de texto, haga clic en **examinar** para ir a la **C:\ WCFBasicHttpReceiveAdapter\BizTalkApp\bin\Development** carpeta, haga doble clic en el **Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp** ensamblado que contiene el ejemplo orquestación para la publicación, haga clic en **abiertos**y, a continuación, haga clic en **siguiente**.  
  
6.  En el **orquestaciones y puertos** página, asegúrese de que el **puerto: DeliveryRequestPort** nodo está seleccionado en la página y, a continuación, haga clic en **siguiente**. Si selecciona este nodo, significará que los nodos de nivel superior correspondientes también se seleccionan. El puerto se publicará con una ubicación de recepción solicitud-respuesta que aloja el adaptador de WCF-BasicHttp.  
  
7.  En el **propiedades del servicio WCF** página, en la **destino** espacio de nombres de la **servicio WCF** cuadro de texto, escriba un URI que desee que este [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio que se usará, y a continuación, haga clic en **siguiente**. En este tutorial, deje la dirección URI predeterminada, "**http://tempuri.org/"** en el espacio de nombres de destino de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] cuadro de texto del servicio.  
  
8.  En el **ubicación del servicio WCF** página, lleve a cabo las siguientes acciones para especificar la ubicación de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] services para crear y, a continuación, haga clic en **siguiente**:  
  
    1.  En el **ubicación** cuadro de texto, escriba el directorio Web nombre donde la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejecuciones del servicio, o haga clic en **examinar** y seleccione el directorio Web. En este tutorial, como el nombre del ensamblado es el mismo que el directorio virtual, deje la ubicación predeterminada (**http://localhost/Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**) en el  **Ubicación** cuadro de texto.  
  
    2.  Seleccione el **permitir acceso anónimo al servicio WCF** opción y, a continuación, haga clic en **siguiente**. Esta opción permite acceso anónimo al directorio virtual creado. Debido a que este tutorial usa el modo de seguridad de transporte sin autenticación, es necesario que esta opción se seleccione para permitir la autenticación anónima para la aplicación web que este asistente va a crear.  
  
9. En el **resumen de servicio WCF** página, haga clic en **crear** para crear el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service. Este paso crea un puerto de recepción para la orquestación especificada disponible a través del directorio Web especificado.  
  
10. En el **completar BizTalk WCF Asistente para publicar servicios** página, haga clic en **finalizar**.  
  
### <a name="to-enable-the-sample-biztalk-application"></a>Para habilitar la aplicación de ejemplo de BizTalk  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **aplicaciones**, expanda **WCFBasicHttpReceiveAdapter**, expanda **orquestaciones**, haga clic en el  **DeliveryProcess** orquestación, haga clic en **propiedades**y, a continuación, configure la información de enlace como se indica a continuación:  
  
    1.  En el **propiedades de orquestación** cuadro de diálogo, haga clic en **enlaces**y, a continuación, establezca **Host** a **BizTalkServerApplication**.  
  
    2.  En el **propiedades de orquestación** cuadro de diálogo, seleccione un puerto de recepción para el **DeliveryRequestPort** para enlazar. En este tutorial, seleccione la recepción de puerto que BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Asistente para publicación de servicio creado en el procedimiento anterior y, a continuación, haga clic en **Aceptar**.  
  
3.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **WCFBasicHttpReceiveAdapter**, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **iniciar Aplicación** cuadro de diálogo.  
  
### <a name="to-configure-the-web-application-hosting-the-published-wcf-service"></a>Para configurar la aplicación Web que aloja el Servicio WCF publicado  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **el Administrador de Internet Information Services (IIS) 7.0**.  
  
2.  En el Administrador de IIS, expanda **sitios**, expanda **sitio Web predeterminado**y, a continuación, expanda la aplicación Web **Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**que la **Asistente de publicación de servicio de WCF de BizTalk** creado.  
  
3.  Cree un grupo de aplicaciones en el que se va a ejecutar este servicio. Haga clic en **grupos de aplicaciones**, haga clic en **Agregar grupo de aplicaciones**, escriba un nombre para el grupo de aplicaciones y, a continuación, haga clic en **Aceptar**.  
  
4.  Expanda **grupos de aplicaciones**, haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **configuración avanzada**. En **modelo de proceso** sección, especifique la cuenta que tiene acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el **identidad** campo.  
  
5.  En el Administrador de IIS, haga clic en **vista de contenido**.  En el panel derecho, haga clic en el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] archivo .svc del servicio que la **Asistente de publicación de servicio de WCF de BizTalk** creado y, a continuación, haga clic en **examinar**. Con esto se abre Internet Explorer para mostrar una página que indica que ha creado correctamente un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] en ejecución. La página también incluye una dirección WSDL completa que puede copiar y usar con una herramienta de metadatos de servicio (svcutil.exe) para recuperar código de proxy y un archivo de configuración que puede usarse para crear una aplicación cliente para el servicio.  
  
6.  Copiar en el Portapapeles la línea de comandos SvcUtil.exe con la dirección WSDL completa especificada en la página que muestra Internet Explorer en el paso anterior.  
  
### <a name="to-create-the-proxy-class-for-the-sample-wcf-client-application-wcfclient"></a>Para crear la clase de proxy para la aplicación de cliente WCF de ejemplo, WCFClient  
  
1.  Cree una clase de proxy para que la aplicación de ejemplo de cliente [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] pueda llamar al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Cuando un proxy no es necesario, escribir el código manualmente es muy complejo, por lo que se recomienda crear un proxy. Abra un **Visual Studio Command Prompt** y vaya a la **C:\WCFBasicHttpReceiveAdapter\WCFClient** carpeta donde se colocará el archivo de configuración de aplicación y de clase de proxy.  
  
2.  Pegar la **svcutil.exe** línea de comandos con la dirección WSDL completa que ha copiado en el procedimiento anterior y, a continuación, presione **ENTRAR** para crear el archivo de configuración de aplicación y de clase de proxy. Esta línea de comandos crea **BizTalkServiceInstance.cs** para la clase de proxy y **output.config** para el archivo de configuración de aplicación.  
  
3.  En Visual Studio, en el Explorador de soluciones, haga clic en **WCFClient**, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
4.  En el **Agregar elemento existente** cuadro de diálogo, vaya a la **WCFClient** carpeta, seleccione **todos los archivos (\*.\*)**  en el **archivos de tipo** lista desplegable, seleccione la **BizTalkServiceInstance.cs** y **output.config** de archivos y, a continuación, haga clic en  **Agregar**.  
  
5.  Para el **WCFClient** proyecto de equipo y expanda **referencias**y, a continuación, asegúrese de que el **WCFClient** proyecto tiene **System.ServiceModel** como uno de sus referencias.  
  
6.  Expanda el **WCFClient** proyecto de equipo y haga clic en **output.config**, haga clic en **cambiar el nombre de**y, a continuación, escriba **App.config** para el nuevo nombre.  
  
7.  Haga doble clic en **Program.cs** para revisar cómo se llama publicado [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio que utiliza la clase de proxy generada por **Svcutil.exe**. Las llamadas para instanciar e invocar un [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio parecen ser llamadas locales en el código sencillo mediante el **Microsoft_Samples_BizTalk_WCFBasicHttpReceiveAdapter_BizTalkApp_DeliveryProcess_DeliveryRequestPortClient** clase. No se necesita ningún código adicional para realizar una llamada a un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] remoto.  
  
8.  En Visual Studio, en el **depurar** menú, haga clic en **iniciar sin depurar** para ejecutar WCFClient. El código de cliente crea un mensaje DeliveryItem y realiza una llamada al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], y transmite la dirección, el identificador de producto y la cantidad.  
  
    ```  
    DeliveryItem deliveryRequestItem = new DeliveryItem();  
    deliveryRequestItem.Address = "One Microsoft Way";  
    deliveryRequestItem.ProductID = "00A120c";  
    deliveryRequestItem.Amount = "300";  
    DeliveryRequestPortClient deliveryProcessClient = new DeliveryRequestPortClient("BasicHttpBinding_ITwoWayAsync");  
    DeliveryItem1 deliveryConfirmation = deliveryProcessClient.Submit(deliveryRequestItem);  
    ```  
  
     Si el cliente recibe correctamente el mensaje de respuesta del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicado, mostrará el número de confirmación de entrega (una concatenación del identificador de producto y la dirección) en el mensaje de respuesta.  
  
     **Enviar la operación con deliveryRequestItem**  
  
     **Devuelve el número de confirmación de entrega: 00A120c300One Microsoft Way**  
  
     **Presione cualquier tecla para continuar...**  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar orquestaciones como servicios WCF](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)