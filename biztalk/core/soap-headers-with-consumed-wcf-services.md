---
title: Encabezados SOAP con servicios WCF consumidos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- SOAP headers, WCF services
- consuming, SOAP headers
- WCF services, SOAP headers
- SOAP headers, consuming [WCF services]
ms.assetid: 0582ee26-b549-4b50-b365-36824010dab0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f60e0ae7f9cf2e6a224ce9d919c7c4d5e6f3119c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="soap-headers-with-consumed-wcf-services"></a>Encabezados SOAP con servicios WCF consumidos
Para enviar un mensaje a un servicio WCF con encabezados SOAP personalizados, estos encabezados se deben establecer en la orquestación (en forma de expresión, por ejemplo) y los componentes de canalización (en código) como la propiedad de contexto **OutboundCustomHeaders**. Esta propiedad se encuentra en el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**y contiene representaciones de cadena de los encabezados SOAP personalizados.  
  
 Los datos en el mensaje saliente de XML siguiente muestran un ejemplo de la representación de cadena de encabezados SOAP personalizados para la **OutboundCustomHeaders** propiedad:  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 Los encabezados SOAP entrantes también contienen representaciones de cadenas de los encabezados SOAP. Los valores son parecidos a la creación de un encabezado SOAP de solicitud.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Usar encabezados SOAP en mensajes WCF con orquestaciones](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [Usar encabezados SOAP en mensajes WCF con componentes de canalización](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Encabezados SOAP con servicios WCF publicados](../core/soap-headers-with-published-wcf-services.md)