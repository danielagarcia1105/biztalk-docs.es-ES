---
title: 'Apéndice B: instalar el adaptador de SharePoint | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0766eabdad71546090b703e41a00f496629d83
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710839"
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>Apéndice B: Instalar el adaptador de Microsoft SharePoint
BizTalk Server incluye un adaptador de SharePoint que permite recibir o enviar mensajes a SharePoint. 

En los requisitos de software de [BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) y [BizTalk Server 2013 y 2013 R2](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) se indican las versiones compatibles de SharePoint.

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>Adaptador de SharePoint en BizTalk Server 2016

El programa de instalación de BizTalk Server instala automáticamente el paquete redistribuible de CSOM, así como el adaptador de archivo, el adaptador de FTP y otros adaptadores predefinidos. 

Se ha quitado la opción SSOM, por lo que ya no está disponible.


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>Adaptador de SharePoint en BizTalk Server 2013 y R2
En BizTalk Server 2013 R2 y BizTalk Server 2013, hay dos opciones para el adaptador de SharePoint.

|Modelo de objetos de SharePoint|Description|  
|-------------------------|-----------------|  
|CSOM - adaptador de SharePoint|**Se recomienda**. El programa de instalación de BizTalk Server instala automáticamente el paquete redistribuible de CSOM, así como el adaptador de archivo, el adaptador de FTP y otros adaptadores predefinidos. <br/><br/>No hay ningún requisito de instalación para el equipo de SharePoint.|  
|SSOM - servicio Web de SharePoint|**Opción obsoleta**. En el equipo de SharePoint, ejecute el programa de instalación de BizTalk Server, y **sólo** seleccione el adaptador de SharePoint. Este programa de instalación instala un servicio web de IIS que controla la comunicación con el adaptador de SharePoint en BizTalk Server. <br/><br/>En la mayoría de los entornos, BizTalk Server y SharePoint están en equipos independientes.|  

##  <a name="BKMK_Before"></a> Antes de la instalación  

*  Los componentes de SharePoint SSOM y CSOM tanto pueden instalarse si BizTalk Server 2013 R2 o 2013 y SharePoint están instalados en el mismo equipo.  
  
* El portal de SAE se ejecuta solo en un modo de 32 bits. Si se instala el Portal de SAE en una máquina de 64 bits, asegúrese de que ASP.NET 2.0 de 32 bits esté habilitado y de que el grupo de aplicaciones IIS esté en modo de 32 bits. Para hacerlo:  
  
    -   **ASP.NET**: abra el Administrador de IIS, haga clic en el sitio web del **portal de BAM** y, después, haga doble clic en **Asignaciones de controlador**. En la lista **Habilitado**, asegúrese de que está incluido **PageHandlerFactory-ISAPI-2.0**.  
  
    -   **Grupo de aplicaciones**: abra el Administrador de IIS, haga clic en **Grupos de aplicaciones**, en **BAMAppPool** y, después, en **Configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **True**.  
  
* Al instalar SharePoint, haga clic en el **granja de servidores** opción, incluso cuando se crea una instalación de servidor único de BizTalk Server y SharePoint. A **granja de servidores** instalación le permite configurar las bases de datos de SharePoint.  
* En [CSOM: Adaptador de SharePoint Services](../core/csom-sharepoint-services-adapter.md) se proporciona información sobre la configuración de un puerto de envío y de una ubicación de recepción de SharePoint.  
* BizTalk Server 2010 y versiones anteriores usan el modelo SSOM (Modelo de objetos del lado servidor) para conectarse a SharePoint 2010. 

## <a name="csom-and-ssom-supported-versions"></a>Versiones compatibles de CSOM y SSOM  
La compatibilidad con SharePoint aparece en la tabla siguiente:  
  
||Compatible con CSOM|Compatible con SSOM|  
|---|---|---|  
|SharePoint 2016|Sí|no|  
|SharePoint 2013|Sí|no|  
|SharePoint Online|Sí|no|  
|SharePoint 2010|Sí|Sí|  
|SharePoint 2007 |no|Sí|  
  
##  <a name="BKMK_CSOM"></a> Instalar el adaptador de SharePoint de CSOM  
  
1.  Utilice un equipo de SharePoint en función de los siguientes requisitos:  
  
    ||Compatibilidad con CSOM|  
    |---|---|  
    |SharePoint 2016<br /><br /> [Instalación de SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|Sí|  
    |SharePoint 2013<br /><br /> [Instalar SharePoint 2013](https://technet.microsoft.com/library/cc262957.aspx)|Sí|  
    |SharePoint Online<br /><br /> [Administración de SharePoint Online](https://technet.microsoft.com/library/gg132908.aspx)|Sí|  
    |SharePoint 2010<br /><br /> [Instalación e implementación de SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|Sí|  
    |SharePoint 2007 |no|  
  
2.  En el servidor BizTalk Server, instale Windows Identity Foundation:  
  
    | Sistema operativo | Información |  
    |---|---|  
    |Windows 10, Windows 8.1, Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2|Windows Identity Foundation se incluye con el sistema operativo como característica en **Activar o desactivar las características de Windows**.|  
    |Windows Vista SP1|Descarga disponible en [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331).|  
  
3.  Instalar a BizTalk Server:

    | |  |  
    |---|---|  
     | BizTalk Server 2016 | Ejecute el programa de instalación de BizTalk. |
    | BizTalk Server 2013 R2 | Ejecute el programa de instalación de BizTalk y **no** elija **Adaptador de Windows SharePoint Services**. |  
    | BizTalk Server 2013 | Ejecute el programa de instalación de BizTalk y **no** elija **Adaptador de Windows SharePoint Services**. |
  
##  <a name="BKMK_SSOM"></a> Instalar el adaptador de SharePoint de SSOM (en desuso)  
  
1.  Use un equipo de SharePoint en función de los siguientes requisitos de SSOM:  
  
    ||Compatibilidad con SSOM|  
    |---|---|  
    |SharePoint 2016<br /><br /> [Instalación de SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|no| 
    |SharePoint 2013<br /><br /> [Instalar SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)|no|  
    |SharePoint Online<br /><br /> [Administración de SharePoint Online](https://technet.microsoft.com/library/gg132908.aspx)|no|  
    |SharePoint 2010<br /><br /> [Instalación e implementación de SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|Sí|  
    |SharePoint 2007<br /><br /> [Implementación de SharePoint Server 2007](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |Sí|  
  
2.  En el equipo de SharePoint, configure SharePoint y extender el sitio Web predeterminado. Al extender el sitio web se creará un sitio web IIS independiente que incluye el mismo contenido pero que también proporciona un tipo de autenticación y una dirección URL únicos.  
  
     Consulte [Extensión de una aplicación web (SharePoint Server 2010)](http://go.microsoft.com/fwlink/p/?LinkId=259124).  
  
3.  En el equipo de SharePoint, ejecute la instalación de BizTalk Server y **sólo** comprobar **adaptador de Windows SharePoint Services**. De este modo se instalará el servicio web. **No ejecute la configuración de BizTalk**.  
  
4.  En el servidor BizTalk Server, instale a BizTalk Server. **No** elija **Adaptador de Windows SharePoint Services**.  
  
5.  El servicio Web (SSOM) de SharePoint solo se ejecuta en modo de 64 bits. ASP.NET y el grupo de aplicaciones de IIS deben estar en el modo de 64 bits en el equipo de SharePoint antes de instalar SharePoint. Para hacerlo:  
  
    -   **ASP.NET**: abra el Administrador de IIS, haga clic en el sitio web y, después, haga doble clic en **Asignaciones de controlador**. En la lista **Habilitado**, asegúrese de que está incluido **PageHandlerFactory-ISAPI-2.0-64**.  
  
    -   **Grupo de aplicaciones**: abra el Administrador de IIS, haga clic en **Grupos de aplicaciones**, seleccione el grupo de aplicaciones y, después, haga clic en **Configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **False**.  

