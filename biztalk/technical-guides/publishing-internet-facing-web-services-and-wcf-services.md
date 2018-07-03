---
title: Publicar servicios Web con Internet y servicios WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a0478e43f87dfbf29f736fde062c67fb4a94cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009205"
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a>Publicación de servicios Web con conexión a Internet y los servicios de WCF
Puede usar varios enfoques para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y servicios WCF en Internet:  
  
- Use reglas de proxy inverso de una red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada).  
  
- Coloque los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que publicar los servicios Web o servicios WCF en el dominio de la red perimetral.  
  
- Usar la funcionalidad de BizTalk Server en la nube habilitador para publicar los servicios Web o servicios WCF como un punto de conexión de Azure AppFabric Service Bus relay.  
  
## <a name="using-a-reverse-proxy"></a>Usar a un Proxy inverso  
 Esto ha sido el enfoque tradicional para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y servicios de WCF. Uso de reglas de proxy inverso en la red perimetral obvia la necesidad que tienen servidores BizTalk Server ubicado en la red perimetral. Las reglas de proxy inverso simplemente reenvían las solicitudes HTTP y SOAP desde la red perimetral a los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el dominio de intranet.  
  
 Para obtener más información sobre el uso de un proxy inverso, consulte los siguientes temas de Ayuda de BizTalk Server:  
  
-   ["Arquitectura de ejemplo: adaptadores SOAP y HTTP"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339).  
  
-   ["TMA de ejemplo: adaptadores SOAP y HTTP"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340).  
  
-   ["Arquitectura distribuida grande"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341).  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a>Uso de los equipos que ejecutan BizTalk Server en la red perimetral  
 Esto no es el método preferido para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services o servicios WCF en Internet ya que requiere que los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se encuentren en la red perimetral. Sin embargo, cuando un proxy inverso no está disponible en la red perimetral, puede usar este enfoque.  
  
 Este enfoque requiere que el dominio de la red perimetral para dar de alta en una confianza unidireccional con el dominio de intranet (pero el dominio de la intranet no confía en el dominio de la red perimetral). Los grupos de la aplicación IIS que hospedan que los servicios Web o servicios WCF en el dominio de red perimetral deben ejecutar bajo una cuenta de dominio de intranet que está en el grupo de dominio "Usuarios de hosts aislados de BizTalk". Esto proporciona el grupo de aplicaciones, los derechos necesarios para publicar mensajes en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes.  
  
 Debe abrir puertos específicos en el firewall para dar cabida a esto. Para obtener más información acerca de los puertos necesarios, consulte ["Puertos para la recepción y enviar servidores"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación.  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a>Exposición de aplicaciones de BizTalk en la nube con AppFabric Connect para servicios  
 Consulte el artículo [exponer aplicaciones de BizTalk en la nube con AppFabric Connect para servicios](http://go.microsoft.com/fwlink/?LinkID=204700) (http://go.microsoft.com/fwlink/?LinkID=204700) para obtener más información sobre cómo exponer aplicaciones de BizTalk como servicios WCF en la nube.  
  
## <a name="see-also"></a>Vea también  
 [Planificación para publicar Web Services1](../technical-guides/planning-for-publishing-web-services1.md)