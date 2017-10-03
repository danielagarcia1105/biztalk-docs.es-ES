---
title: "Apéndice B: instalar el adaptador de Microsoft SharePoint | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f67c888d844182daa6ecdc8e65e13487b8b337f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>Apéndice B: Instalar el adaptador de Microsoft SharePoint
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un adaptador [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] que permite recibir o enviar mensajes a [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. 

En este tema se describe el adaptador de SharePoint.  En los requisitos de software de [BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) y [BizTalk Server 2013 y 2013 R2](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) se indican las versiones compatibles de SharePoint.

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>Adaptador de SharePoint en BizTalk Server 2016

El programa de instalación de BizTalk Server instala automáticamente el paquete redistribuible de CSOM, así como el adaptador de archivo, el adaptador de FTP y otros adaptadores predefinidos. 

Se ha quitado la opción SSOM, por lo que ya no está disponible.


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>Adaptador de SharePoint en BizTalk Server 2013 y R2
En [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013, hay dos opciones para el adaptador de SharePoint.

|Modelo de objetos de SharePoint|Descripción|  
|-------------------------|-----------------|  
|CSOM: adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]|**Se recomienda**. El programa de instalación de BizTalk Server instala automáticamente el paquete redistribuible de CSOM, así como el adaptador de archivo, el adaptador de FTP y otros adaptadores predefinidos. <br/><br/>No hay ningún requisito de instalación para el equipo de SharePoint.|  
|SSOM: servicio web de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]|**Obsoleto**. En el equipo de SharePoint, ejecute el programa de instalación de BizTalk Server y seleccione **solo** el adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. Este programa de instalación instala un servicio web de IIS que controla la comunicación con el adaptador de SharePoint en BizTalk Server. <br/><br/>En la mayoría de entornos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] están en equipos distintos.|  

##  <a name="BKMK_Before"></a> Antes de la instalación  

*  Los componentes SSOM y CSOM de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] se pueden instalar si [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] o 2013 y [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] están instalados en el mismo equipo.  
  
* El portal de SAE se ejecuta solo en un modo de 32 bits. Si se instala el Portal de SAE en una máquina de 64 bits, asegúrese de que ASP.NET 2.0 de 32 bits esté habilitado y de que el grupo de aplicaciones IIS esté en modo de 32 bits. Para hacerlo:  
  
    -   **ASP.NET**: abra el Administrador de IIS, haga clic en el sitio web del **portal de BAM** y, después, haga doble clic en **Asignaciones de controlador**. En la lista **Habilitado**, asegúrese de que está incluido **PageHandlerFactory-ISAPI-2.0**.  
  
    -   **Grupo de aplicaciones**: abra el Administrador de IIS, haga clic en **Grupos de aplicaciones**, en **BAMAppPool** y, después, en **Configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **True**.  
  
* Al instalar [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], haga clic en la opción **Granja de servidores**, incluso si va a crear una instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] de servidor único. La instalación de una **Granja de servidores** permite configurar las bases de datos de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].  
* En [CSOM: Adaptador de SharePoint Services](../core/csom-sharepoint-services-adapter.md) se proporciona información sobre la configuración de un puerto de envío y de una ubicación de recepción de SharePoint.  
* BizTalk Server 2010 y versiones anteriores usan el modelo SSOM (Modelo de objetos del lado servidor) para conectarse a SharePoint 2010. 

## <a name="csom-and-ssom-supported-versions"></a>Versiones compatibles de CSOM y SSOM  
En la tabla siguiente se muestra la compatibilidad con [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]:  
  
||Compatible con CSOM|Compatible con SSOM|  
|-|-------------------|-------------------|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2016|Sí|No|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013|Sí|No|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Online|Sí|No|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010|Sí|Sí|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007 |No|Sí|  
  
##  <a name="BKMK_CSOM"></a> Instalar el adaptador de SharePoint de CSOM  
  
1.  Utilice un equipo de SharePoint en función de los siguientes requisitos:  
  
    ||Compatibilidad con CSOM|  
    |-|------------------|  
        |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2016<br /><br /> [Instalación de SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|Sí|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013<br /><br /> [Instalar SharePoint 2013](https://technet.microsoft.com/library/cc262957.aspx)|Sí|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Online<br /><br /> [Administración de SharePoint Online](https://technet.microsoft.com/library/gg132908.aspx)|Sí|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010<br /><br /> [Instalación e implementación de SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|Sí|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007 |No|  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], instale Windows Identity Foundation:  
  
    | Sistema operativo | Información |  
    |-|-|  
    |[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 10, [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 8.1, [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Server 2016, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2|Windows Identity Foundation se incluye con el sistema operativo como característica en **Activar o desactivar las características de Windows**.|  
    |[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] SP1|Descarga disponible en [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331).|  
  
3.  Instale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:

    | |  |  
    |-|-|  
     | [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] | Ejecute el programa de instalación de BizTalk. |
    | [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] | Ejecute el programa de instalación de BizTalk y **no** elija **Adaptador de Windows SharePoint Services**. |  
    | BizTalk Server 2013 | Ejecute el programa de instalación de BizTalk y **no** elija **Adaptador de Windows SharePoint Services**. |
  
##  <a name="BKMK_SSOM"></a> Instalar el adaptador de SharePoint de SSOM (en desuso)  
  
1.  Utilice un equipo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] en función de los siguientes requisitos de SSOM:  
  
    ||Compatibilidad con SSOM|  
    |-|------------------|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2016<br /><br /> [Instalación de SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|No| 
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013<br /><br /> [Instalar SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)|No|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Online<br /><br /> [Administración de SharePoint Online](https://technet.microsoft.com/library/gg132908.aspx)|No|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010<br /><br /> [Instalación e implementación de SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|Sí|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007<br /><br /> [Implementación de SharePoint Server 2007](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |Sí|  
  
2.  En el equipo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], configure SharePoint y extienda el sitio web predeterminado. Al extender el sitio web se creará un sitio web IIS independiente que incluye el mismo contenido pero que también proporciona un tipo de autenticación y una dirección URL únicos.  
  
     Consulte [Extensión de una aplicación web (SharePoint Server 2010)](http://go.microsoft.com/fwlink/p/?LinkId=259124).  
  
3.  En el equipo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], ejecute la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y active **solo** la opción **Adaptador de Windows SharePoint Services**. De este modo se instalará el servicio web. **No ejecute la configuración de BizTalk**.  
  
4.  En el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], instale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. **No** elija **Adaptador de Windows SharePoint Services**.  
  
5.  El Servicio Web [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (SSOM) solo se ejecuta en el modo de 64 bits. ASP.NET y el grupo de aplicaciones de IIS deben estar en el modo de 64 bits en el equipo de SharePoint antes de instalar SharePoint. Para hacerlo:  
  
    -   **ASP.NET**: abra el Administrador de IIS, haga clic en el sitio web y, después, haga doble clic en **Asignaciones de controlador**. En la lista **Habilitado**, asegúrese de que está incluido **PageHandlerFactory-ISAPI-2.0-64**.  
  
    -   **Grupo de aplicaciones**: abra el Administrador de IIS, haga clic en **Grupos de aplicaciones**, seleccione el grupo de aplicaciones y, después, haga clic en **Configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **False**.  

