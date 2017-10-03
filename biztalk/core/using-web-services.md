---
title: Con los servicios Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236acb42c010effe5c3d45cde1daaf9a7097ede5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-web-services"></a>Uso de servicios web
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad integrada para servicios Web. BizTalk Server permite reutilizar y agregar todos los servicios Web existentes en las orquestaciones. Las orquestaciones también se publican o se exponen como servicios Web para diferenciar la lógica de servicios Web de la lógica de procesos empresariales.  
  
 BizTalk Server incorpora la compatibilidad con adaptadores nativos en servicios Web. La compatibilidad con adaptadores nativos proporciona escalabilidad, tolerancia a errores y capacidades de seguimiento para servicios Web sin tener que escribir una sola línea de código. Para obtener información acerca del adaptador SOAP, vea [adaptador de SOAP](../core/soap-adapter.md).  
  
 La compatibilidad de servicios Web de BizTalk Server se divide en dos categorías: consumo o llamada a servicios Web y publicación o creación de servicios Web.  
  
 Antes de consumir o publicar un servicio Web, debe estar familiarizado con los servicios Web XML en ASP.NET. Para obtener información sobre los conceptos básicos de los servicios Web XML, vea el artículo "XML Web Services Basics" en [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).  
  
 **Consumir servicios Web**  
  
 Se pueden consumir (llamar) servicios Web procedentes de una orquestación. Es posible agregar varios servicios Web a una única orquestación para completar todo un proceso empresarial.  
  
 **Publicar servicios Web**  
  
 Se pueden publicar servicios Web mediante el Asistente para publicar servicios Web de BizTalk. Las orquestaciones y los adaptadores de envío pueden usar estos servicios Web publicados.  
  
 **Usar encabezados SOAP**  
  
 BizTalk Server proporciona compatibilidad para encabezados SOAP definidos y desconocidos. BizTalk Server crea una propiedad de contexto para cada encabezado SOAP definido en el servicio Web.  
  
 **Estándares de servicios Web**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe trabajar con los estándares de servicios web al enviar y recibir. No todos los estándares se han probado. Normalmente, los estándares admitidos por WCF también son compatibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los estándares de ejemplo son:  
  
-   WS-ReliableMessaging  
  
-   WS-Security  
  
-   WS-SecureConversation  
  
-   WS-Trust  
  
-   WS-Federation  
  
-   WS-Addressing  
  
-   WS-Policy  
  
-   WS-MetadataExchange  
  
-   WS-Coordination  
  
-   WS-Atomic  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consumir servicios Web](../core/consuming-web-services.md)  
  
-   [Publicar servicios Web](../core/publishing-web-services.md)  
  
-   [Usar encabezados SOAP](../core/using-soap-headers.md)