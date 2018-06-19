---
title: HTTPRequestResponse | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 81c66f61-d86c-49cf-8d24-21c67c68bc5a
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 549f343818464a8316246f8b6996755ce5fef136
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973754"
---
# <a name="httprequestresponse"></a>HTTPRequestResponse
En el ejemplo HTTPRequestResponse se muestra cómo usar el filtro de la interfaz de programación de aplicaciones para servidores de Internet (ISAPI) de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de Microsoft para permitir que una aplicación ASP.NET se comunique con una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo, la aplicación ASP.NET envía una solicitud al filtro ISAP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. A continuación, la orquestación consume este mensaje y lo devuelve a la aplicación ASP.NET por medio de una respuesta sincrónica. La integración entre la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la aplicación ASP.NET se consigue mediante el filtro ISAPI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 En este ejemplo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la aplicación ASP.NET intercambian el pedido de compra (PO) y los mensajes de confirmación de pedido según la siguiente secuencia de pasos:  
  
1.  Una aplicación ASP.NET, a través de una solicitud HTTP, envía un mensaje de pedido XML a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe el mensaje de pedido XML, construye un mensaje de confirmación de pedido XML y, a continuación, devuelve el mensaje a la aplicación ASP.NET en la respuesta HTTP.  
  
 La aplicación ASP.NET recibe la respuesta de confirmación de pedido XML y actualiza el formulario Web con la información de estado extraída de la respuesta.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>* \AdaptersUsage\HTTPRequestResponse\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.|  
|HTTPRequestResponse.btproj, HTTPRequestResponse.sln|Proporciona archivos del proyecto y de origen para el proyecto de BizTalk que recibe la solicitud HTTP, procesa el mensaje de pedido y emite la respuesta.|  
|HTTPRequestResponseBinding.xml|Proporciona la instalación automatizada, como el enlace de puertos.|  
|POAck.xsd, POSchema.xsd|Proporciona esquemas para la confirmación de pedido y para los archivos de pedido .xml, respectivamente.|  
|POReceiveOrchestration.odx|Proporciona una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que recibe el pedido de compra, lo procesa y emite la confirmación de pedido.|  
|Setup.bat|Crea e inicializa este ejemplo.|  
|En la carpeta \RequestResponse:<br /><br /> AssemblyInfo.cs, default.aspx, default.aspx.cs, Global.asax, Global.asax.cs, RequestResponse.csproj, RequestResponse.csproj.webinfo, RequestResponse.sln, Web.config|Contiene archivos que forman la aplicación ASP.NET que sirve como controlador para este ejemplo, incluidos los archivos del proyecto y de la solución, archivos ASPX, archivos de origen de Microsoft Visual C# .NET, etc.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Utilice el siguiente procedimiento para generar e inicializar el ejemplo HTTPRequestResponse.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\AdaptersUsage\HTTPRequestResponse  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Compila y configura la aplicación ASP.NET utilizada para controlar este ejemplo.  
  
        > [!NOTE]
        >  Al crear el grupo de aplicaciones en el Administrador de IIS, establezca el **DefaultAppPool** versión de .NET Framework para **.Net Framework v4.0**.  
  
    -   Compila e implementa la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se usa en este ejemplo.  
  
    -   Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] de Microsoft para este ejemplo.  
  
    -   Crea y enlaza los puertos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesarios.  
  
    -   Inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
        > [!IMPORTANT]
        >  Debe modificar el código del ejemplo que implementa la aplicación Web (Default.aspx.cs) para reflejar su entorno:  
        >   
        >  http://\<*nombre del servidor*\>/\<*dir virtual*\>/BTSHTTPReceive.dll donde `<servername>` es el nombre de la Web servidor que se va a registrar en, y `<` *dir virtual* `>` es el directorio virtual donde reside este archivo.  
  
        > [!NOTE]
        >  Debe confirmar que BizTalk no ha informado de ningún error durante el proceso de generación e inicialización antes de intentar ejecutar este ejemplo.  
  
        > [!NOTE]
        >  Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes. También debe eliminar de forma manual las referencias a default.aspx.resx y Global.asax.resx del archivo RequestResponse.csproj antes de intentar generar ese proyecto.  
  
        > [!NOTE]
        >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
        > [!NOTE]
        >  Debe configurar y habilitar ISS para usar el adaptador de recepción HTTP. Para obtener más información, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
3.  El archivo setup.bat configura el directorio virtual de este ejemplo para ejecutarlo en el grupo de aplicaciones de IIS asociado al sitio Web predeterminado.  Para configurar el directorio virtual para este ejemplo y ejecutarlo en el contexto de un usuario en el **usuarios de hosts aislados de BizTalk** y **IIS_IURS** grupos de usuarios, debe configurar el directorio virtual para ejecutarlo en una nueva Grupo de aplicaciones de IIS. Configure el directorio virtual para ejecutarlo en un grupo de aplicaciones IIS nuevo realizando los pasos que se indican a continuación:  
  
    > [!NOTE]
    >  Si ya ha creado un grupo de aplicaciones nuevo para otro ejemplo de SDK, puede continuar con el último paso que aparece a continuación.  
  
    1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
    2.  En el **Internet Information Services (IIS) Manager**, navegue hasta la **grupos de aplicaciones** carpeta.  
  
    3.  Haga clic en el **grupos de aplicaciones** carpeta y haga clic en **New**, **grupo de aplicaciones...**  
  
    4.  Escriba un nombre para el **Id. de grupo de aplicaciones:** como BizTalkSDKSamples, compruebe que la **usar configuración predeterminada para el nuevo grupo de aplicaciones** opción está seleccionada y haga clic en **Aceptar** a Crear nuevo grupo de aplicaciones.  
  
    5.  Haga clic en el nuevo grupo de aplicaciones y, a continuación, haga clic en **propiedades**.  
  
    6.  Haga clic en el **identidad** ficha del cuadro de diálogo Propiedades del cuadro y cambiar la identidad bajo la que se ejecuta este grupo de aplicaciones a un usuario que sea miembro de la **usuarios de hosts aislados de BizTalk** grupo de usuarios.  Este usuario también debe ser miembro de la variable local **IIS_IURS** grupo de usuarios.  
  
    7.  Configure el directorio virtual de este ejemplo SDK para ejecutarlo en el grupo de aplicaciones nuevo. El **grupo de aplicaciones** está disponible en la **directorio Virtual** ficha del cuadro de diálogo de propiedades de directorio Virtual. El directorio virtual que se ha creado para este ejemplo es HttpRequestResponseSample.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo HTTPRequestResponse.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En Internet Explorer, visite http://localhost/RequestResponse/.  
  
2.  Complete los campos necesarios en el formulario Web Forms y, a continuación, haga clic en **realizar pedido** para enviar el pedido.  
  
3.  Consulte el estado de su pedido cuando se actualice el formulario Web después de recibir una respuesta.  
  
## <a name="comments"></a>Comentarios  
 El **BTSHTTPReceiveISAPI** extensión utilizada en este ejemplo se configura para que funcionen en una instalación predeterminada de equipo único. Para extender este ejemplo para configuraciones adicionales, vea [adaptador de HTTP](../core/http-adapter.md).  
  
 Puede extender este ejemplo a aplicaciones que requieren enviar datos a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a través de un formulario web o mediante HTTP de manera general. Si extiende la parte de la aplicación ASP.NET de este ejemplo, podrá consultar más información y realizar otro preprocesamiento antes de enviar los datos a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores de HTTP](../core/http-adapter-samples.md)