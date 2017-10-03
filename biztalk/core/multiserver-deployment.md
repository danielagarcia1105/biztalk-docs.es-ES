---
title: "Implementación multiservidor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], multi-server deployment
- planning, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, deploying
- Windows SharePoint Services adapters, multi-server deployment
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
ms.assetid: 0c6e2aa0-e873-461b-8101-9b0988019597
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d9770a2d9e4977ec23c8ff4013d5415c75087d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="multiserver-deployment"></a>Implementación multiservidor
En este tema se analizan la implementación y configuración multiservidor del adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Windows SharePoint Services.  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a>Instalar el adaptador de Windows SharePoint Services en una implementación multiservidor  
 Al seleccionar el componente de servicio web del adaptador de Windows SharePoint Services, se instala el software necesario para que el adaptador de Windows SharePoint Services procese documentos entrantes y salientes a través de Windows SharePoint Services. Este servicio web debe instalarse en el servidor en el que se instala Windows SharePoint Services.  
  
 El servicio web de adaptador puede controlar varios sitios de SharePoint, independientemente de si se encuentran en el mismo sitio de IIS o en sitios de IIS diferentes.  
  
 El adaptador de Windows SharePoint Services tiene tres componentes:  
  
-   Componentes de tiempo de ejecución  
  
-   Componentes de tiempo de diseño  
  
-   Servicio web del adaptador  
  
 La característica de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instala y configura automáticamente el tiempo de ejecución del adaptador. Los componentes de tiempo de diseño del adaptador se instalan y configuran con otras características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para interactuar con los componentes de tiempo de diseño, cree puertos de Windows SharePoint Services con las herramientas que se incluyen en las características Herramientas de administración, SDK y Herramientas de programadores o Tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. No puede personalizar ninguna de las opciones de configuración de los componentes de tiempo de ejecución y tiempo de diseño. Únicamente puede personalizar las opciones del servicio web del adaptador de Windows SharePoint Services.  
  
 Solo los miembros del grupo Hosts habilitados de SharePoint tienen permiso para invocar el servicio web del adaptador. Para obtener más información acerca de los permisos de Windows SharePoint Services que sea necesario mediante la ejecución del adaptador de Windows SharePoint Services, vea la sección de seguridad en [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).  
  
> [!NOTE]
>  El componente de servicio web del adaptador de Windows SharePoint Services se selecciona automáticamente si elige instalar BAS.  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>Para instalar el adaptador de Windows SharePoint Services  
  
1.  Instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).  
  
2.  En el **instalación de componentes** pantalla **componentes disponibles**, en **Software adicional**, seleccione **adaptador de Windows SharePoint Services Servicio Web**.  
  
> [!NOTE]
>  Debe ejecutar la instalación y configuración tanto en el equipo que hospeda el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como en el equipo que ejecuta Windows SharePoint Services.  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a>Configuración del servicio web del adaptador de Windows SharePoint Services en una implementación multiservidor  
 El adaptador de Windows SharePoint Services se configura con la configuración de BizTalk Server. Para obtener más información acerca de estas herramientas, consulte [Introducción a la configuración de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).  
  
### <a name="using-a-custom-configuration"></a>Usar una configuración personalizada  
 La configuración de BizTalk Server proporciona un análisis de alto nivel del estado de configuración de las características que ha instalado en el equipo local. La herramienta permite configurar y desconfigurar características, configurar valores de seguridad, e importar y exportar configuraciones de otros equipos.  
  
 Use la **Windows SharePoint Services** página para configurar el adaptador de Windows SharePoint Services en este equipo. En la siguiente tabla se enumeran las opciones de configuración.  
  
|Use|Para|  
|--------------|----------------|  
|**Habilitar a adaptador de Windows SharePoint Services en este equipo**|Seleccione **habilitar adaptador de Windows SharePoint Services en este equipo** para habilitar el adaptador en este equipo.|  
|**Grupo de Windows**|El **grupo de Windows** lista proporciona una vista que se puede editar del grupo de Windows de Hosts habilitados de BizTalk SharePoint adaptador.|  
|**Sitio Web del adaptador de Windows SharePoint Services**|Seleccione el sitio web que hospedará el servicio web del adaptador de Windows SharePoint Services.|  
  
 Al configurar el adaptador de Windows SharePoint Services con la configuración personalizada, ocurre lo siguiente:  
  
-   Se crea el grupo de Windows Hosts habilitados de SharePoint de forma predeterminada a menos que se especifique otro grupo de Windows  
  
-   El sitio web predeterminado se usa para hospedar el adaptador de Windows SharePoint Services, a menos que se especifique otro sitio web.  
  
-   El grupo de aplicaciones BTSSharePointAdapterWSAppPool se crea y configura para que se ejecute en la cuenta que también se utiliza para ejecutar el grupo de aplicaciones de Windows SharePoint Services.  
  
-   La aplicación virtual BTSharePointAdapterWS se crea y configura para que se ejecute en el grupo de aplicaciones BTSSharePointAdapterWSAppPool.  
  
> [!NOTE]
>  Si ya existe este directorio virtual, la configuración no actualizará las propiedades en la metabase. Debe eliminar el directorio virtual y ejecutar de nuevo la configuración.  
  
-   La aplicación virtual BTSharePointAdapterWS contiene el servicio Web  
  
 Para obtener más información acerca de la configuración de BizTalk Server, vea [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a>Para configurar el adaptador de Windows SharePoint Services con la configuración personalizada  
  
1.  En el **configuración de BizTalk Server**, seleccione la **adaptador de Windows SharePoint** nodo.  
  
2.  Seleccione **habilitar adaptador de Windows SharePoint Services en este equipo**.  
  
3.  En **grupo de Windows**, seleccione el grupo de Windows que se va a usar para el adaptador de Windows SharePoint Services. El grupo predeterminado es Hosts habilitados de SharePoint.  
  
4.  En el **sitio Web de adaptador de Windows SharePoint Services** cuadro de lista desplegable, seleccione el sitio Web donde se instalará los componentes de adaptador. De forma predeterminada, éste es el sitio Web predeterminado.  
  
    > [!NOTE]
    >  La instalación del sitio web del adaptador de Windows SharePoint Services en un equipo de SharePoint Server remoto que no tiene ningún otro componente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es una configuración completamente admitida.  
  
5.  Haga clic en **Aplicar configuración**.  
  
## <a name="considerations-for-a-multiserver-deployment"></a>Consideraciones para una implementación multiservidor  
 ![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")  
  
### <a name="general-considerations"></a>Consideraciones generales  
 Al configurar e implementar el adaptador de Windows SharePoint Services en un entorno multiservidor, tenga en cuenta lo siguiente:  
  
-   Agregue la cuenta de servicio de BizTalk al grupo de Windows Hosts habilitados de SharePoint de cada servidor.  
  
-   Agregue el grupo Hosts habilitados de SharePoint a la función Colaboradores de SharePoint con la herramienta Administración central de SharePoint.  
  
-   En [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], la identidad bajo la que el servicio web del adaptador de SharePoint se ejecuta debe tener los permisos siguientes:  
  
     **Lectura** permisos en el **archivos de programa\Microsoft BizTalk Server \<versión > \Business Activity Services\BTSharePointV3AdapterWS** carpeta. Si usa una versión de 64 bits de Windows y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], permisos deben establecerse en el **(x86) de archivos de programa \Microsoft BizTalk Server \<versión > \Business Activity Services\BTSharePointV3AdapterWS**  
  
     **Lectura** permiso en la siguiente clave del registro: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.  
  
     Permisos de inicio de sesión en el servidor SQL Server que contiene las bases de datos de SharePoint.  
  
     Un miembro de la **público** y **WSS_Content_Application_Pools** roles dentro de la base de datos de configuración de SharePoint.  
  
     Un miembro de la **público** y **propietario de la base de datos** roles dentro de la base de datos de contenido de SharePoint.  
  
-   El sitio web en el que se instale el servicio web debe extenderse como un sitio web de SharePoint Services.  
  
-   Puede instalar y configurar el adaptador de Windows SharePoint Services con una instalación silenciosa. Para obtener más información, consulte [Apéndice A: instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md).  
  
### <a name="considerations-for-network-load-balancing-nlb"></a>Consideraciones para el equilibrio de carga de red (NLB)  
 El adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Windows SharePoint Services es compatible con los clústeres de NLB de los servidores de Windows SharePoint Services junto con varios servidores de BizTalk configurados en el mismo grupo. Para ello, Windows SharePoint Services debe instalarse en el clúster de NLB como se recomienda en la documentación de SharePoint.  
  
 Al configurar e implementar el adaptador de Windows SharePoint Services en un entorno multiservidor con NLB, tenga en cuenta lo siguiente:  
  
-   Al configurar Windows SharePoint Services, seleccione la opción de señalar a una base de datos de administración de BizTalk existente. Señale a la base de datos de administración de BizTalk creada en el primer equipo. Con ello se le indica a Windows SharePoint Services que pretende crear un entorno de servidor web. Extienda el sitio web al señalar a la base de datos de contenido existente.  
  
-   Debe extender el mismo sitio web (por ejemplo, el sitio web predeterminado en el puerto 80) en cada equipo con Windows SharePoint Services del entorno de servidor web.  
  
-   BTSharePointAdapterWS se debe instalar y configurar del mismo modo en cada uno de los hosts de NLB. Se debe efectuar la siguiente configuración de NLB:  
  
    -   Protocolo: TCP  
  
    -   Puertos: 80 (el puerto HTTP del sitio web de IIS en el que se ha instalado y configurado el servicio web del adaptador de Windows SharePoint Services)  
  
    -   Modo de filtrado: Varios host  
  
    -   Afinidad: Ninguna  
  
> [!NOTE]
>  Esta configuración se puede utilizar únicamente si el sitio no se ha configurado para HTTPS. Si el servicio web BTSharePointAdapterWS se instala en un sitio con HTTPS, se debe usar la afinidad de cliente único.  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter.md)   
 [Implementación de servidor único](../core/single-server-deployment.md)