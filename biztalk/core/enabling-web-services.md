---
title: Habilitar los servicios Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7cd0b1694422caf04285206f0bd7411ff5de20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-web-services"></a>Habilitar los servicios Web
Para publicar servicios Web, debe configurar cuentas de grupos, de los Servicios de Internet Information Server (IIS), de hosts aislados de BizTalk y de usuarios de Windows. Esta sección describe cómo habilitar los servicios Web en IIS. Para obtener más información acerca de cómo habilitar los servicios Web, consulte la documentación de IIS.  
  
 **Internet Information Services**  
  
 Puede publicar servicios Web en sistemas de Windows que tengan IIS configurado con ASP.NET. Para cada servidor, todos los servicios Web se ejecutan en el proceso de trabajo ASP.NET.  
  
 De forma predeterminada, el proceso de trabajo ASP.NET usa la cuenta local ASPNET. IIS usa grupos de aplicaciones para el procesamiento de solicitudes de servicio Web.  
  
 **Hosts aislados de BizTalk**  
  
 Para habilitar los servicios Web, debe crear al menos un host aislado en BizTalk Server. Los hosts aislados representan procesos externos, como extensiones ISAPI y procesos ASP.NET que BizTalk Server no crea ni controla. Estos tipos de procesos externos deben alojar determinados adaptadores, como los de HTTP y SOAP.  
  
 El Administrador de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea BizTalkServerIsolatedHost, y BizTalk lo usa como el host aislado predeterminado. De forma predeterminada, el nombre del grupo de Windows asociado a este host es Usuarios de hosts aislados de BizTalk. Para obtener más información sobre los Hosts y las instancias de Host, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
 Una instancia de host aislado sólo puede ejecutar un adaptador. Si configura los controladores de recepción de los adaptadores HTTP y SOAP con un host aislado, debe crear dos grupos de aplicaciones, uno para cada adaptador.  
  
 Por ejemplo, si tiene intención de configurar dos hosts aislados de la siguiente manera:  
  
|Nombre del host aislado|Ubicaciones de recepción|  
|------------------------|-----------------------|  
|Host aislado 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1 **Nota:** el **Host aislado 1** se utiliza para recibir controladores de adaptadores de SOAP y HTTP.|  
|Host aislado 2|HTTP_ReceiveLocation2|  
  
 Puede crear cuatro directorios virtuales, uno para cada ubicación de recepción, de la siguiente manera.  
  
|Ubicación de la recepción|Directorio virtual|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 A continuación, debe crear al menos tres grupos de aplicaciones para los directorios virtuales de la siguiente manera:  
  
> [!NOTE]
>  Debe crear al menos un grupo de aplicaciones para cada host aislado.  
  
|Directorios virtuales|Grupo de aplicaciones|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|No se requiere un grupo de aplicaciones independiente, ya que todas las ubicaciones de recepción tienen el mismo host aislado (host aislado 1) y el mismo protocolo.|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|No se requiere un grupo de aplicaciones independiente, ya que la ubicación de recepción usa un protocolo diferente (SOAP) de otras ubicaciones de recepción del mismo host (host aislado 1).|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|Se requiere un grupo de aplicaciones independiente, ya que la ubicación de recepción se ejecuta en un host distinto del host aislado 1.|  
  
> [!NOTE]
>  Debe agregar la cuenta de usuario para los grupos de aplicaciones a los grupos de dominio o locales correspondiente de los hosts aislados. Para obtener más información, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
> [!NOTE]
>  Debe coincidir con la cuenta de usuario entre una instancia de host aislado y el grupo de aplicaciones correspondiente según las tablas anteriores. Para obtener más información sobre la relación entre cuentas de usuario de los grupos de instancia y de aplicación de host aislado, consulte [cómo cambiar las cuentas de servicio y las contraseñas](../core/how-to-change-service-accounts-and-passwords.md).  
  
 **Acceso de base de datos para las instalaciones de servidor único**  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la base de datos de administración de BizTalk se encuentran en el mismo servidor, debe establecer el contexto de usuario del proceso de trabajo ASP.NET o el grupo de aplicaciones IIS como la cuenta de usuario local ASPNET o como una cuenta de usuario local o de dominio con los privilegios mínimos.  
  
 **Acceso de base de datos para varias instalaciones de servidor**  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la base de datos de administración de BizTalk se encuentran en distintos servidores, debe cambiar el contexto de usuario del proceso de trabajo ASP.NET o el grupo de aplicaciones de ISS a una cuenta de usuario de dominio.  
  
 Al implementar una implementación de varios servidores, los grupos de Windows de hosts aislados deben existir en el dominio al que pertenecen los servidores de base de datos de BizTalk a.  
  
 **Minimizar privilegios de cuenta y derechos de usuario**  
  
 Use hosts aislados para proporcionar a los adaptadores que se ejecutan en procesos externos acceso a la cantidad mínima de los recursos necesarios para interactuar con BizTalk Server. Para una implementación segura, debe proporcionar el contexto de usuario para los privilegios mínimos de procesos externos.  
  
 **Recomendaciones de seguridad para el Asistente para publicación de BizTalk Web Services**  
  
 El directorio virtual creado por el Asistente para publicar servicios Web de BizTalk heredará las listas de control de acceso (ACL) y los requisitos de autenticación del directorio virtual principal o del sitio Web. Si el directorio virtual principal o el sitio Web permiten el acceso anónimo, el Asistente para publicar servicios Web de BizTalk quitará esa capacidad al crear el directorio virtual.  
  
 La siguiente contiene notas de seguridad y recomendaciones para [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)].  
  
## <a name="next"></a>Siguiente
  
[Cómo habilitar ASP.NET para servicios Web publicados](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)