---
title: Publicar servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00136b64d5feaf552f77b92b3ad4442da4e447cc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710243"
---
# <a name="publish-wcf-services"></a>Publicar servicios WCF
Puede publicar una orquestación como un servicio WCF en BizTalk Server para ser llamado por los clientes de WCF.  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a>Publicar servicios WCF con los adaptadores WCF aislados 
  
 Es posible crear y publicar servicios WCF mediante el Asistente para publicación de Servicio WCF de BizTalk para adaptadores de WCF aislados, por ejemplo, el adaptador de WCF-BasicHttp, el adaptador de WCF-WSHttp y el adaptador de WCF-CustomIsolated. Esto crea una ubicación de recepción que existe como una aplicación fuera de proceso en IIS.  
  
 Antes de publicar un Servicio WCF con los adaptadores de WCF aislados, debe estar familiarizado con el modo en que los servicios WCF se alojan en Servicios de Internet Information Server (IIS).  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>Publicar metadatos de servicio para ubicaciones de recepción de WCF
  
 Cree los metadatos de servicio para ubicaciones de recepción WCF publicadas mediante el Asistente para publicación de Servicio WCF de BizTalk. Para generar el código de cliente del modelo de servicio de los documentos de metadatos publicados, que puede usar la herramienta Utilidad de metadatos del modelo de servicio (SvcUtil.exe) incluida en el Kit de desarrollo de Software (SDK) de Windows y componentes de tiempo de ejecución de .NET Framework.  
  
> [!IMPORTANT]
>  Antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk, debe habilitar los servicios WCF. Para obtener más información acerca de cómo habilitar servicios WCF para el sistema, consulte [configurar IIS para los adaptadores de recepción de WCF aislados](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Publicación de servicios WCF con los adaptadores de recepción WCF aislados](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Publicación de metadatos de servicio para los adaptadores de recepción WCF](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [Consideraciones al publicar servicios WCF con los adaptadores de recepción WCF](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [Encabezados SOAP con servicios WCF publicados](../core/soap-headers-with-published-wcf-services.md)  
  
-   [Iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)