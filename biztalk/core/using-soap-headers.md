---
title: Usar encabezados SOAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers
- SOAP headers, about SOAP headers
- Web services, SOAP headers
ms.assetid: 816618ff-ecd8-4f12-b9a9-dbe4203411d8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0671dabe7547d3f55b937a1de58241a35cb70b39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers"></a>Utilizar encabezados SOAP
Microsoft BizTalk Server proporciona compatibilidad para encabezados SOAP definidos y desconocidos. Los encabezados SOAP definidos son encabezados de Lenguaje de descripción de servicios Web (WSDL) que se encuentran indicados explícitamente en el servicio Web. Los encabezados SOAP desconocidos son encabezados de WSDL que no se encuentran indicados explícitamente en el servicio Web. Para obtener más información sobre el uso de encabezados SOAP, consulte "Using SOAP Headers" en la documentación de Microsoft .NET Framework en [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).  
  
 BizTalk Server crea una propiedad de contexto para cada encabezado SOAP definido en el servicio Web.  
  
> [!NOTE]
>  Los servicios Web consumidos sólo admiten encabezados SOAP definidos. No puede establecer encabezados desconocidos al consumir servicios Web.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md)  
  
-   [Encabezados SOAP con servicios Web publicados](../core/soap-headers-with-published-web-services.md)