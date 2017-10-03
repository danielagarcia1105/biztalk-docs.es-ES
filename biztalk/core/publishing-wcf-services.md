---
title: Publicar servicios WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f72f2b300738f2e9a1a643e152048b64cf8f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-wcf-services"></a>Publicar servicios WCF
Se puede publicar una orquestación como un servicio WCF en [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ser llamado por los clientes de WCF.  
  
 **Publicar servicios WCF con adaptadores de WCF aislados**  
  
 Es posible crear y publicar servicios WCF mediante el Asistente para publicación de Servicio WCF de BizTalk para adaptadores de WCF aislados, por ejemplo, el adaptador de WCF-BasicHttp, el adaptador de WCF-WSHttp y el adaptador de WCF-CustomIsolated. Esto crea una ubicación de recepción que existe como una aplicación fuera de proceso en IIS.  
  
 Antes de publicar un Servicio WCF con los adaptadores de WCF aislados, debe estar familiarizado con el modo en que los servicios WCF se alojan en Servicios de Internet Information Server (IIS).  
  
 **La publicación de metadatos de servicio para ubicaciones de recepción de WCF**  
  
 Cree los metadatos de servicio para ubicaciones de recepción WCF publicadas mediante el Asistente para publicación de Servicio WCF de BizTalk. Para generar el código de cliente del modelo de servicio de los documentos de metadatos publicados puede usar la herramienta Utilidad de metadatos del modelo de servicio (SvcUtil.exe) incluida en el [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Kit de desarrollo de Software (SDK) para [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] y [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Componentes de tiempo de ejecución.  
  
> [!IMPORTANT]
>  Antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk, debe habilitar los servicios WCF. Para obtener más información acerca de cómo habilitar servicios WCF para el sistema, consulte [configurar IIS para los adaptadores de recepción de WCF aislados](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Publicar servicios WCF con WCF aislado adaptadores de recepción](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Adaptadores de recepción de la publicación de metadatos de servicio de WCF](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [Consideraciones al publicar servicios WCF con WCF adaptadores de recepción](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [Encabezados SOAP con servicios WCF publicados](../core/soap-headers-with-published-wcf-services.md)  
  
-   [Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)