---
title: Consumir servicios Web con encabezados SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, consuming
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
ms.assetid: c2dfe7d8-e2f0-4bc6-b79c-354d06a7ffd6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45a3efa628e435092505fdc3884704baa15be34c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237812"
---
# <a name="consuming-web-services-with-soap-headers"></a>Consumir servicios Web con encabezados SOAP
Después de consumir un servicio Web con encabezados SOAP definidos, éstos pasan a estar disponibles para las orquestaciones y los componentes de canalización como propiedades de contexto. Estas propiedades de contexto contienen representaciones de cadenas de los encabezados SOAP. Para cada encabezado SOAP definido en el servicio Web, puede crear una propiedad de contexto mediante el nombre que corresponde al elemento raíz del encabezado SOAP. Todas las propiedades de contexto de encabezado SOAP definidas están en el **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** espacio de nombres.  
  
 En el ejemplo siguiente se muestra cómo crear una propiedad de contexto del encabezado SOAP **OrigDest** en el ejemplo de encabezado SOAP en [encabezados SOAP con los servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md):  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns=" http://SOAPHeaderWS.ItemAvailability">  
   <Origination xmlns="">Home</Origination>  
      <Destination xmlns="">Work</Destination>  
</OrigDest>  
```  
  
 Los encabezados SOAP de respuesta también contienen representaciones de cadena del encabezado SOAP definido. Los valores son parecidos a la creación de un encabezado SOAP de solicitud.  
  
## <a name="see-also"></a>Vea también  
 [Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md)