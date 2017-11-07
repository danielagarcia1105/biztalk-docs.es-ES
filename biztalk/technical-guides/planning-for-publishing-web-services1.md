---
title: "Publicar servicios web de planeación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b571c3aa-874b-43f7-af2e-5a71113a93dd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34539704a0725a96464fae03226fb88cdd6660c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="planning-for-publishing-web-services"></a>Planificación para publicar servicios Web
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]proporciona compatibilidad integrada para servicios Web. Permite reutilizar y agregar los servicios Web existentes en las orquestaciones.  

## <a name="overview"></a>Información general
 También puede publicar (exponer) lógica de la lógica de procesos empresariales, lo que permite actualizar o reemplazar la lógica de negocios según sea necesario sin tocar el código utilizado para la lógica de servicio Web de servicios de las orquestaciones como servicios Web para diferenciar la Web. Esta funcionalidad se conoce como implementación de "código modular". Por lo general se considera una práctica recomendada de implementar código modular siempre que sea posible. Publicación de servicios Web requiere que habilite servicios Web y publicar una orquestación o un esquema como un servicio Web mediante el Asistente para publicación de servicios Web de BizTalk.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]implementa la compatibilidad con adaptadores nativos en servicios Web mediante el uso del adaptador de SOAP. La compatibilidad con adaptadores nativos proporciona escalabilidad, tolerancia a errores y capacidades de seguimiento para servicios Web sin tener que escribir una sola línea de código. Para obtener más información acerca del adaptador SOAP, vea [adaptador de SOAP](../core/soap-adapter.md).  
  
Planeación de servicios Web puede dividirse en dos categorías, planificación de publicación de servicios Web y para consumir servicios Web. En este tema se describe los pasos que debe seguir para publicar servicios Web.  
  
## <a name="enabling-web-services"></a>Habilitar los servicios Web  
 Para publicar servicios Web, debe configurar cuentas de grupos, de los Servicios de Internet Information Server (IIS), de hosts aislados de BizTalk y de usuarios de Windows. Esta sección proporciona información general acerca de cómo habilitar los servicios web. Para obtener más información acerca de cómo habilitar los servicios Web, consulte la documentación de IIS.  
  
### <a name="internet-information-services"></a>Internet Information Services
 Puede publicar servicios Web en sistemas de Windows que tengan IIS configurado con ASP.NET. En IIS, todos los servicios Web se ejecutan dentro del proceso de trabajo ASP.NET.  
  
 IIS usa grupos de aplicaciones para el procesamiento de solicitudes de servicio Web. IIS admite varios grupos de aplicaciones y cada proceso del grupo de aplicaciones puede ejecutarse en un contexto de usuario diferente.  
  
### <a name="biztalk-isolated-hosts"></a>Hosts aislados de BizTalk  
 Para habilitar los servicios Web, debe crear al menos un host aislado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los hosts aislados representan procesos externos, como las extensiones ISAPI y procesos ASP.NET que BizTalk Server no crea ni controlar. Estos tipos de procesos externos deben alojar determinados adaptadores, como los de HTTP y SOAP.  
  
 El Administrador de configuración de BizTalk Server crea BizTalkServerIsolatedHost [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa como el host aislado predeterminado. De forma predeterminada, el nombre del grupo de Windows asociado a este host es Usuarios de hosts aislados de BizTalk. Para obtener más información sobre los hosts y las instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
 Una instancia de host aislado sólo puede ejecutar un adaptador. Si configura los controladores de recepción de los adaptadores HTTP y SOAP con un host aislado, debe crear dos grupos de aplicaciones, uno para cada adaptador.  
  
 Por ejemplo, si tiene pensado configurar dos hosts aislados, como se indica a continuación:  
  
|Nombre de Host aislado|Ubicaciones de recepción|  
|------------------------|-----------------------|  
|Host aislado 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1 **Nota:** el **Host aislado 1** se utiliza para recibir controladores de adaptadores de SOAP y HTTP.|  
|Host aislado 2|HTTP_ReceiveLocation2|  
  
 Puede crear cuatro directorios virtuales, uno para cada ubicación de recepción, como se indica a continuación:  
  
|Ubicación de recepción|Directorio virtual|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 A continuación, debe crear al menos tres grupos de aplicaciones para los directorios virtuales como sigue:  
  
> [!NOTE]  
>  Debe crear al menos un grupo de aplicaciones para cada host aislado.  
  
|Directorios virtuales|Grupo de aplicaciones|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|No se requiere un grupo de aplicaciones independiente, ya que todas las ubicaciones de recepción tienen el mismo host aislado (host aislado 1) y el mismo protocolo.|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|No se requiere un grupo de aplicaciones independiente, ya que la ubicación de recepción usa un protocolo diferente (SOAP) de otras ubicaciones de recepción del mismo host (host aislado 1).|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|Se requiere un grupo de aplicaciones independiente, ya que la ubicación de recepción se ejecuta en un host distinto del host aislado 1.|  
  
 A medida que cree los grupos de aplicaciones, tenga en cuenta los siguientes puntos importantes:  
  
-   Debe agregar la cuenta de usuario para los grupos de aplicaciones a los grupos de dominio o locales correspondiente de los hosts aislados. Vea [grupo de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
-   Debe coincidir con la cuenta de usuario entre una instancia de host aislado y el grupo de aplicaciones correspondiente según las tablas anteriores. Para obtener más información sobre la relación entre cuentas de usuario de los grupos de instancia y de aplicación de host aislado, consulte [cómo cambiar las cuentas de servicio y las contraseñas](../core/how-to-change-service-accounts-and-passwords.md).  
  
### <a name="database-access-for-single-server-installations"></a>Acceso de base de datos para las instalaciones de servidor único  
 Si BizTalk Server y la base de datos de administración de BizTalk se encuentran en el mismo servidor, debe establecer el contexto de usuario del proceso de trabajo ASP.NET o el grupo de aplicaciones de IIS a la cuenta de usuario ASPNET local o a una cuenta de usuario local o de dominio que tenga los privilegios mínimos.  
  
### <a name="database-access-for-multiple-server-installations"></a>Acceso de base de datos para varias instalaciones de servidor  
 Si BizTalk Server y la base de datos de administración de BizTalk se encuentran en distintos servidores, debe cambiar el contexto de usuario del proceso de trabajo ASP.NET o el grupo de aplicaciones de IIS a una cuenta de usuario de dominio.  
  
 Al implementar una implementación de varios servidores, los grupos de Windows de hosts aislados deben existir en el dominio al que pertenecen los servidores de base de datos de BizTalk a.  
  
### <a name="minimizing-account-privileges-and-user-rights"></a>Minimizar privilegios de cuenta y derechos de usuario  
 Utilice hosts aislados para proporcionar a los adaptadores que se ejecutan en procesos externos acceso a la cantidad mínima de los recursos necesarios para interactuar con BizTalk Server. Para una implementación más segura, debe proporcionar el contexto de usuario para los procesos externos privilegios mínimos.  
  
### <a name="security-recommendations-for-biztalk-web-services-publishing-wizard"></a>Recomendaciones de seguridad para el Asistente de publicación de servicios Web de BizTalk  
 El directorio virtual creado por el Asistente para publicar servicios Web de BizTalk heredará las listas de control de acceso (ACL) y los requisitos de autenticación del directorio virtual principal o del sitio Web. Si el directorio virtual principal o el sitio Web permiten el acceso anónimo, el Asistente para publicar servicios Web de BizTalk quitará esa capacidad al crear el directorio virtual.  
  
### <a name="enabling-aspnet-40-for-published-web-services"></a>Habilitar ASP.NET 4.0 para servicios Web publicados  
Vea [cómo habilitar ASP.NET 4.0 para publican servicios Web](../core/how-to-enable-asp-net-4-0-for-published-web-services.md).  
  
## <a name="using-the-biztalk-web-services-publishing-wizard"></a>Usar el Asistente para publicar los servicios Web de BizTalk  
 Para obtener más información acerca de cómo publicar una orquestación como servicio Web, consulte [publicar una orquestación como un servicio Web](../core/publishing-an-orchestration-as-a-web-service.md).  
  
 Para obtener más información acerca de cómo publicar esquemas como servicios Web, consulte [publicar esquemas como servicios Web](../core/publishing-schemas-as-a-web-service.md).  
  
## <a name="planning-for-publishing-wcf-services"></a>Planificación para publicar servicios WCF  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]incluye compatibilidad integrada para Windows Communication Foundation (WCF). [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]permite reutilizar y agregar todos los servicios WCF existentes en las orquestaciones. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]También incorpora compatibilidad con adaptadores nativos en servicios WCF. La compatibilidad con adaptadores nativos proporciona escalabilidad, tolerancia a errores y capacidades de seguimiento para servicios WCF sin tener que escribir código. Para obtener información acerca de los adaptadores WCF, vea [adaptadores de WCF](../core/wcf-adapters.md).  
  
 Para obtener más información acerca de cómo planear los servicios WCF en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [publicar servicios WCF](../core/publishing-wcf-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Planificación del consumo de servicios web](../technical-guides/planning-for-consuming-web-services.md)
