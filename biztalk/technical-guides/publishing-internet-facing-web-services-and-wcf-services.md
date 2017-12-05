---
title: Publicar servicios Web con Internet y servicios WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e466c4fc2a5f83f5a8445601235b53f44404a912
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a>Publicar servicios Web de conexión a Internet y servicios de WCF
Puede utilizar varios enfoques para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y servicios WCF a Internet:  
  
-   Usar reglas de proxy inverso en una red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada).  
  
-   Coloque los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que publican los servicios Web o servicios WCF en el dominio de la red perimetral.  
  
-   Utilizar la funcionalidad de habilitador de nube de BizTalk Server para publicar los servicios Web o servicios WCF como un extremo de retransmisión de Bus de servicio de AppFabric de Azure.  
  
## <a name="using-a-reverse-proxy"></a>Usar a un Proxy inverso  
 Esto ha sido el enfoque tradicional para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y los servicios de WCF. Usar reglas de proxy inverso en la red perimetral obvia la necesidad de tener servidores de BizTalk que se encuentran en la red perimetral. Las reglas de proxy inverso simplemente reenvían las solicitudes HTTP y SOAP desde la red perimetral a los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el dominio de la intranet.  
  
 Para obtener más información sobre el uso de un proxy inverso, vea los temas siguientes en la Ayuda de BizTalk Server:  
  
-   ["Ejemplo de arquitectura: adaptadores SOAP y HTTP"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339).  
  
-   ["TMA de ejemplo: adaptadores SOAP y HTTP"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340).  
  
-   ["Arquitectura distribuida grande"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341).  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a>Con equipos que ejecutan BizTalk Server en la red perimetral  
 Esto no es el método preferido para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services o los servicios WCF a Internet porque requiere equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se encuentra en la red perimetral. Sin embargo, cuando un proxy inverso no está disponible en la red perimetral, puede usar este enfoque.  
  
 Este enfoque requiere que el dominio de la red perimetral para dar de alta en una confianza unidireccional con el dominio de intranet (pero el dominio de la intranet no confía en el dominio de la red perimetral). Los grupos de la aplicación IIS que hospedan que los servicios Web o servicios WCF en el dominio de la red perimetral se deben ejecutar con una cuenta de dominio de intranet que está en el grupo de dominio "Usuarios de hosts aislados de BizTalk". Esto proporciona el grupo de aplicaciones, los derechos necesarios para publicar mensajes en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes.  
  
 Debe abrir puertos específicos en el firewall para dar cabida a este. Para obtener más información acerca de los puertos necesarios, consulte ["Puertos para la recepción y enviar servidores"](http://go.microsoft.com/fwlink/?LinkId=153342) (http://go.microsoft.com/fwlink/?LinkId=153342) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación.  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a>Exponer las aplicaciones de BizTalk en la nube con AppFabric Connect para los servicios  
 Vea el artículo [exponer las aplicaciones de BizTalk en la nube con AppFabric Connect para los servicios](http://go.microsoft.com/fwlink/?LinkID=204700) (http://go.microsoft.com/fwlink/?LinkID=204700) para obtener más información acerca de cómo exponer aplicaciones de BizTalk como servicios WCF en la nube.  
  
## <a name="see-also"></a>Vea también  
 [Planificación para publicar Web Services1](../technical-guides/planning-for-publishing-web-services1.md)