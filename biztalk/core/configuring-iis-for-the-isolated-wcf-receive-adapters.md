---
title: Configurar IIS para WCF aislado adaptadores de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1515a69ab6a9150668db4f3415f0483dd1ce4e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233372"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a>Configurar IIS para los adaptadores de recepción WCF aislados
Para publicar los servicios WCF mediante el asistente para publicación de Servicio WCF de BizTalk, debe configurar Servicios de Internet Information Server (IIS), hosts aislados de BizTalk y las cuentas de grupo de usuarios de Windows. En esta sección se tratan los problemas relacionados con la configuración de IIS para la publicación de servicios WCF con adaptadores de recepción WCF aislados como el adaptador de recepción WCF-BasicHttp, adaptador de recepción WCF-BasicHttp y el adaptador de WCF-CustomIsolated. Para obtener información general sobre el hospedaje de servicios WCF en IIS, vea "Hosting in IIS" en [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700).  
  
## <a name="considerations-when-configuring-iis"></a>Consideraciones para configurar IIS  
 **Servicios de Internet Information Server 7.0 y 7.5**  
  
 Puede utilizar IIS 7.0 y 7.5 configurado con ASP.NET 4.0 para publicar servicios WCF con adaptadores de recepción WCF aislados.  
  
 Tanto IIS 7.0 (para Windows Server 2008 SP2) como IIS 7.5 (para Windows Server 2008 R2) usan los grupos de aplicaciones de IIS para procesar las solicitudes de servicios web. IIS 7.0 es compatible con varios grupos de aplicaciones. Cada proceso de grupo de aplicaciones puede ejecutarse en un contexto de usuario distinto.  
  
 **Hosts aislados de BizTalk**  
  
 Para alojar los servicios WCF con adaptadores de recepción WCF aislados, debe crear al menos un host aislado en el servidor BizTalk Server. Para obtener más información acerca de cómo configurar los hosts aislados de BizTalk, vea "Hosts aislados de BizTalk" en [habilitar servicios Web](../core/enabling-web-services.md).  
  
 **Acceso de base de datos para varias instalaciones de servidor**  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la base de datos de administración de BizTalk se encuentran en distintos servidores, debe cambiar el contexto de usuario del grupo de aplicaciones de ISS a una cuenta de usuario de dominio.  
  
 Cuando se realiza una implementación de varios servidores, los grupos de Windows de hosts aislados deben existir en el dominio al que pertenecen los servidores de base de datos de BizTalk.  
  
 **Minimizar privilegios de cuenta y derechos de usuario**  
  
 Utilice hosts aislados para proporcionar a los adaptadores que se ejecutan en procesos externos acceso a la cantidad mínima de los recursos necesarios para interactuar con BizTalk Server. Para una implementación segura, debe proporcionar el contexto de usuario para los privilegios mínimos de procesos externos.  
  
 **Recomendaciones de seguridad para el Asistente para publicación de servicios Web de BizTalk**  
  
 El directorio virtual que crea el asistente para publicación de Servicio WCF de BizTalk  
  
## <a name="see-also"></a>Vea también  
 [Publicar servicios WCF](../core/publishing-wcf-services.md)