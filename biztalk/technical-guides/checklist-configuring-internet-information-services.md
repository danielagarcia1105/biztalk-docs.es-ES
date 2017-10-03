---
title: "Lista de comprobación: Configurar Internet Information Services | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 186f82c0-bd50-4c79-a403-8b0d91cc68d6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfb3323bd122fd9dba007321b4ffef90bdbe7214
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-configuring-internet-information-services"></a>Lista de comprobación: Configurar Internet Information Services
Este tema enumeran los pasos que deben seguirse al preparar los servicios de Internet Information Server (IIS) para su uso en producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Configurar IIS para publicar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y los servicios de WCF|: Vea ["Habilitar servicios Web"](http://go.microsoft.com/fwlink/?LinkId=153335) (http://go.microsoft.com/fwlink/?LinkId=153335) en la documentación de BizTalk Server.<br />: Vea ["Configurar IIS para la recepción adaptadores de WCF aislados"](http://go.microsoft.com/fwlink/?LinkId=202825)(http://go.microsoft.com/fwlink/?LinkId=202825) en la documentación de BizTalk Server.|  
|Compruebe que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y servicios WCF funcionan correctamente.|: Vea ["Testing Publicar Web Services"](http://go.microsoft.com/fwlink/?LinkId=153336) (http://go.microsoft.com/fwlink/?LinkId=153336) en la documentación de BizTalk Server.<br />: Vea ["Cómo a unos .NET a prueba un WCF servicio publicado con el BizTalk WCF servicio publicación Asistente para crear aplicaciones"](http://go.microsoft.com/fwlink/?LinkId=202830) (http://go.microsoft.com/fwlink/?LinkId=202830) en la documentación de BizTalk Server.|  
|Bloquear [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web:<br /><br /> -Desactivar el conmutador de depuración en el archivo web.config o machine.config.<br />-Configurar para que POST es el verbo solo permitido.|: Vea el artículo de Microsoft Knowledge Base 815145, ["Cómo: bloquear una aplicación Web ASP.NET o servicio Web"](http://go.microsoft.com/fwlink/?LinkId=153337) (http://go.microsoft.com/fwlink/?LinkId=153337).<br />: Vea ["ASP.NET Edit Rule Dialog Box"](http://go.microsoft.com/fwlink/?LinkID=64566) (http://go.microsoft.com/fwlink/?LinkID=64566) en la documentación de .NET Framework 2.0.|  
|Configurar el equilibrio de carga mediante el uso de NLB (u otro equilibrador de carga) para equilibrar la carga entre los servicios Web de BizTalk Server y servicios WCF.|-   **Para Windows Server 2008**: vea ["Guía de implementación de equilibrio de carga de red"](http://go.microsoft.com/fwlink/?LinkId=153139) (http://go.microsoft.com/fwlink/?LinkId=153139).<br />-   **Para Windows Server 2003**: vea ["equilibrio de carga de red: prácticas recomendadas de configuración para Windows 2000 y Windows Server 2003"](http://go.microsoft.com/fwlink/?LinkID=69529) (http://go.microsoft.com/fwlink/?LinkID=69529).|  
|Cambiar la configuración de IIS y ASP.NET para los servicios Web para la optimización. **Nota:** ASP.NET 2.0 incluye ajuste automático, por lo que modificar esta configuración no debería ser necesario para el archivo web.config de los sitios Web de ASP.NET 2.0 donde está habilitada la configuración automática en el \<processModel > sección. "autoConfig = true" es la configuración predeterminada.|Revise la "configuración de ASP.NET que puede afectar al rendimiento del adaptador SOAP o HTTP" sección del tema ["Configuración de parámetros que afectan al rendimiento del adaptador"](http://go.microsoft.com/fwlink/?LinkId=153338) (http://go.microsoft.com/fwlink/?LinkId=153338) en la documentación de BizTalk Server.|  
|Implemente un enfoque para la publicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios Web y los servicios de WCF.|: Vea [publicar servicios Web con Internet y servicios WCF](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md).<br />: Vea ["Publicar servicios WCF"](http://go.microsoft.com/fwlink/?LinkId=202827) (http://go.microsoft.com/fwlink/?LinkId=202827) en la documentación de BizTalk Server.|  
|Siga las prácticas recomendadas para optimizar el rendimiento de IIS.|Vea ["Mejores formas de diez para bombear el rendimiento de IIS"](http://go.microsoft.com/fwlink/?LinkId=109107) (http://go.microsoft.com/fwlink/?LinkId=109107).|  
|Siga las prácticas recomendadas para la escritura de aplicaciones web de IIS de alto rendimiento.|Vea ["Aplicaciones Web de 10 sugerencias para la escritura de alto rendimiento"](http://go.microsoft.com/fwlink/?LinkId=98290) (http://go.microsoft.com/fwlink/?LinkId=98290).|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Publicar servicios Web de conexión a Internet y servicios de WCF](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)