---
title: Publicación de servicios Web con encabezados SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, pipelines
- SOAP headers, BizTalk Web Services Publishing Wizard
- pipelines, SOAP headers
- orchestrations, SOAP headers
ms.assetid: c362caff-b75f-4c1b-9013-d2b9c74f5c65
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7baf6af0e4505e448a854fe6def372614bfdaa49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269028"
---
# <a name="publishing-web-services-with-soap-headers"></a>Publicar servicios Web con encabezados SOAP
Al ejecutar el Asistente para publicar servicios Web de BizTalk, se agregan encabezados SOAP a los servicios Web. Al publicar un servicio Web que admite encabezados SOAP, los encabezados están disponibles para las orquestaciones y los componentes de canalización como propiedades de contexto que contienen representaciones de cadena de los encabezados SOAP.  
  
## <a name="defined-soap-headers"></a>Encabezados SOAP definidos  
 Al agregar un encabezado SOAP definido mediante el asistente, éste crea una propiedad de contexto con un nombre que se corresponde con el elemento raíz del encabezado SOAP. Todas las propiedades de contexto de encabezado SOAP definidas tienen el espacio de nombres **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**. Cuando el adaptador de SOAP convierte la solicitud SOAP en un mensaje de BizTalk, crea una propiedad de contexto de encabezado SOAP.  
  
 En el siguiente ejemplo se muestra una solicitud SOAP simple:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
       <soap:Header>  
             <OrigDest xmlns="http://SOAPHeaderWS.ItemAvailability">  
                    <Origination>Work</Origination>  
                    <Destination>Home</Destination>  
             </OrigDest>  
       </soap:Header>  
       <soap:Body>  
  
       </soap:Body>  
</soap:Envelope>  
```  
  
 Para la solicitud SOAP simple, el adaptador SOAP, cree un mensaje de BizTalk con una propiedad de contexto de encabezado SOAP **OrigDest** y la cadena.  
  
 El siguiente ejemplo muestra la cadena creada por el adaptador de SOAP:  
  
```  
"<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader"><Origination xmlns="">Home</Origination><Destination xmlns="">Work</Destination> </OrigDest>"  
```  
  
## <a name="unknown-soap-headers"></a>Encabezados SOAP desconocidos  
 Si decide admitir encabezados SOAP desconocidos en el asistente, el asistente crea una propiedad de contexto con el nombre **UnknownHeaders** y el espacio de nombres **http://schemas.microsoft.com/BizTalk/2003/soap-properties**. El **UnknownHeaders** propiedad de contexto contiene todos los encabezados SOAP desconocidos recibidos.  
  
 Por ejemplo, si recibe un encabezado SOAP desconocido con el nombre del elemento raíz, **CustomerGroup**, **UnknownHeaders** propiedad de contexto contiene la cadena:  
  
```  
"<?xml version="1.0" encoding="utf-16"?><UnknownHeaders><CustomerGroup xmlns="http://SOAPHeaderWS/CustomerGroup"><Id xmlns="">My Customer</Id>  
</CustomerGroup></UnknownHeaders>"  
```  
  
 Para obtener más información acerca de cómo agregar definido encabezados SOAP o admitir encabezados SOAP desconocidos, consulte [publicar una orquestación como un servicio Web](../core/publishing-an-orchestration-as-a-web-service.md). Consulte también [publicar esquemas como servicios Web](../core/publishing-schemas-as-a-web-service.md).  
  
## <a name="see-also"></a>Vea también  
 [Encabezados SOAP con servicios Web publicados](../core/soap-headers-with-published-web-services.md)