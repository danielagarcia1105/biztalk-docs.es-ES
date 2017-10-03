---
title: "Implementación de servidor único | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, deploying
- configuring [Windows SharePoint Services adapters], customizing
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
- Windows SharePoint Services adapters, configuring
- configuring [Windows SharePoint Services adapters], single-server deployment
- Windows SharePoint Services adapters, single-server deployment
ms.assetid: 94ba8241-9a30-46ca-b962-721e2d00f420
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38bb6aa65a77c5473ac2934bd2bd0c59268eb2af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-server-deployment"></a>Implementación de servidor único
En este tema se trata la configuración e implementación de un solo servidor para el adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Windows SharePoint Services.  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a>Instalar el adaptador de Windows SharePoint Services en una implementación de un solo servidor  
 Al seleccionar el componente de servicio Web del adaptador de Windows SharePoint Service, se instala el software necesario para que el adaptador de Windows SharePoint Services procese documentos entrantes y salientes mediante Windows SharePoint Services. Este servicio web debe instalarse en el servidor en el que se instala Windows SharePoint Services. El servicio Web del adaptador puede controlar varios sitios de SharePoint, incluido el sitio Web que aloja los Servicios de la actividad de negocio (BAS), independientemente de si están en el mismo sitio de IIS o en sitios diferentes.  
  
 El adaptador de Windows SharePoint Services tiene tres componentes:  
  
-   Componentes de tiempo de ejecución  
  
-   Componentes de tiempo de diseño  
  
-   Servicio web del adaptador  
  
 La característica de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instala y configura automáticamente el tiempo de ejecución del adaptador. Los componentes de tiempo de diseño de adaptador se instalan y configuran con las demás [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] características. Para interactuar con los componentes de tiempo de diseño, cree puertos de Windows SharePoint Services con las herramientas que se incluyen en las características Herramientas de administración, SDK y Herramientas de programadores o Tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. No puede personalizar ninguna de las opciones de configuración de los componentes de tiempo de ejecución y tiempo de diseño. Sólo puede personalizar las opciones del servicio Web del adaptador de Windows SharePoint Services.  
  
 Sólo los miembros del grupo Hosts habilitados de SharePoint tienen permiso para invocar el servicio Web del adaptador. Para obtener más información acerca de los permisos de Windows SharePoint Services que sea necesario mediante la ejecución del adaptador de Windows SharePoint Services, vea la sección de seguridad en [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).  
  
> [!NOTE]
>  El componente de servicio web del adaptador de Windows SharePoint Services se selecciona automáticamente si elige instalar BAS.  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>Para instalar el adaptador de Windows SharePoint Services  
  
1.  Instalar a BizTalk Server. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).  
  
2.  En el **instalación de componentes** pantalla **componentes disponibles**, en **Software adicional**, seleccione **adaptador de Windows SharePoint Services Servicio Web**.  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a>Configurar el servicio Web del adaptador de Windows SharePoint Services en una implementación de un solo servidor  
 Puede configurar el adaptador de Windows SharePoint Services con una configuración básica o con una configuración personalizada. Para obtener más información acerca de estas herramientas, consulte [Introducción a la configuración de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).  
  
### <a name="using-a-basic-configuration"></a>Usar una configuración básica  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite configurar el servidor mediante la configuración predeterminada. La configuración predeterminada del servidor se realiza con el nombre del servidor de la base de datos, el nombre del usuario y la contraseña que especificó en el Asistente para configuración. Cuando se configura el servicio Web del adaptador de Windows SharePoint Services con una configuración básica, ocurre lo siguiente:  
  
-   Se crea el grupo de Windows Hosts habilitados de SharePoint.  
  
-   El sitio Web predeterminado se utiliza para alojar el adaptador de Windows SharePoint Services  
  
-   Se crea y configura el grupo de aplicaciones BTSSharePointAdapterWSAppPool para ejecutarlo con la cuenta que se usa también para ejecutar el grupo de aplicaciones de Windows SharePoint Services.  
  
-   La aplicación virtual BTSharePointAdapterWS se crea y configura para que se ejecute en el grupo de aplicaciones BTSSharePointAdapterWSAppPool.  
  
> [!NOTE]
>  Si ya existe este directorio virtual, la configuración no actualizará las propiedades en la metabase. Debe eliminar el directorio virtual y ejecutar de nuevo la configuración.  
  
-   La aplicación virtual BTSharePointAdapterWS contiene el servicio Web  
  
 Para obtener más información sobre la configuración básica, consulte [configuración básica](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5).  
  
### <a name="using-a-custom-configuration"></a>Usar una configuración personalizada  
 La configuración de BizTalk Server proporciona un análisis de alto nivel del estado de configuración de las características que ha instalado en el equipo local. La herramienta permite configurar y desconfigurar características, configurar valores de seguridad, e importar y exportar configuraciones de otros equipos.  
  
 Use la **servicio Web de adaptador de Windows SharePoint Services** página para configurar el adaptador de Windows SharePoint Services en este equipo. En la siguiente tabla se enumeran las opciones de configuración.  
  
|Use|Para|  
|--------------|----------------|  
|**Habilitar a adaptador de Windows SharePoint Services en este equipo**|Seleccione **habilitar adaptador de Windows SharePoint Services en este equipo** para habilitar el adaptador en este equipo.|  
|**Grupo de Windows**|El **grupo de Windows** lista proporciona una vista que se puede editar del grupo de Windows de Hosts habilitados de BizTalk SharePoint adaptador.|  
|**Sitio Web del adaptador de Windows SharePoint Services**|Seleccionar el sitio Web que alojará el servicio Web del adaptador de Windows SharePoint Services.|  
  
 Cuando se configura el adaptador de Windows SharePoint Services con una configuración personalizada, ocurre lo siguiente:  
  
-   Se crea el grupo de Windows Hosts habilitados de SharePoint de forma predeterminada a menos que se especifique otro grupo de Windows  
  
-   El sitio web predeterminado se usa para hospedar el adaptador de Windows SharePoint Services, a menos que se especifique otro sitio web.  
  
-   El grupo de aplicaciones BTSSharePointAdapterWSAppPool se crea y configura para que se ejecute en la cuenta que también se utiliza para ejecutar el grupo de aplicaciones de Windows SharePoint Services.  
  
-   La aplicación virtual BTSharePointAdapterWS se crea y configura para que se ejecute en el grupo de aplicaciones BTSSharePointAdapterWSAppPool.  
  
> [!NOTE]
>  Si ya existe este directorio virtual, la configuración no actualizará las propiedades en la metabase. Debe eliminar el directorio virtual y ejecutar de nuevo la configuración.  
  
-   La aplicación virtual BTSharePointAdapterWS contiene el servicio Web  
  
 Para obtener más información acerca del Administrador de configuración personalizada, vea [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a>Para configurar el adaptador de Windows SharePoint Services con una configuración personalizada  
  
1.  En el **configuración de BizTalk Server**, seleccione la **adaptador de Windows SharePoint** nodo.  
  
2.  Seleccione **habilitar adaptador de Windows SharePoint Services en este equipo**.  
  
3.  En **grupo de Windows**, seleccione el grupo de Windows que se va a usar para el adaptador de Windows SharePoint Services. El grupo predeterminado es Hosts habilitados de SharePoint.  
  
4.  En el **sitio Web de adaptador de Windows SharePoint Services** cuadro de lista desplegable, seleccione el sitio Web donde se instalará los componentes de adaptador. De forma predeterminada, éste es el sitio Web predeterminado.  
  
5.  Haga clic en **Aplicar configuración**.  
  
## <a name="considerations-for-a-single-server-deployment"></a>Consideraciones para una implementación de un solo servidor  
 Cuando configure e implemente el adaptador de Windows SharePoint Services en un entorno de un solo servidor, considere lo siguiente:  
  
-   Agregue la cuenta de servicio de BizTalk al grupo de Windows Hosts habilitados de SharePoint en ese servidor.  
  
-   Agregue el grupo Hosts habilitados de SharePoint a la función Colaboradores de SharePoint con la herramienta Administración central de SharePoint.  
  
-   En [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], la identidad bajo la que el servicio web del adaptador de SharePoint se ejecuta debe tener los permisos siguientes:  
  
     **Lectura** permisos en el **archivos de programa\Microsoft BizTalk Server \<versión > \Business Activity Services\BTSharePointV3AdapterWS** carpeta. Si usa una versión de 64 bits de Windows y el servidor BizTalk Server, permisos deben establecerse en el **(x86) de archivos de programa \Microsoft BizTalk Server \<versión > \Business Activity Services\BTSharePointV3AdapterWS**  
  
     **Lectura** permiso en la siguiente clave del registro: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.  
  
     Permisos de inicio de sesión en el servidor SQL Server que contiene las bases de datos de SharePoint.  
  
     Un miembro de la **público** y **WSS_Content_Application_Pools** roles dentro de la base de datos de configuración de SharePoint.  
  
     Un miembro de la **público** y **propietario de la base de datos** roles dentro de la base de datos de contenido de SharePoint.  
  
-   El sitio web en el que se instale el servicio web debe extenderse como un sitio web de SharePoint Services.  
  
-   Puede instalar y configurar el adaptador de Windows SharePoint Services con una instalación silenciosa. Para obtener más información, consulte [Apéndice A: instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md).  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter.md)   
 [Implementación multiservidor](../core/multiserver-deployment.md)