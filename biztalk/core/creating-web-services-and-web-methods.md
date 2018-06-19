---
title: Creación de servicios Web y métodos Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74065489e427ae0612897f1f333e3c8e154a535f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238388"
---
# <a name="creating-web-services-and-web-methods"></a>Creación de servicios Web y métodos Web
Al publicar esquemas como servicio Web, controla la creación de servicios y métodos Web en el Asistente para publicar servicios Web de BizTalk. Se puede cambiar el nombre de la descripción del servicio Web, el servicio y el método Web dentro del árbol disponible en la página Servicios Web. Puede agregar y quitar servicios y métodos Web. El asistente usa los nombres de elementos raíz de los esquemas de solicitud seleccionados como el nombre del parámetro de entrada. El valor de retorno del método Web devuelve el esquema de respuesta.  
  
> [!NOTE]
>  Los clientes Web ASP.NET pueden cambiar la firma del método Web mediante la combinación de parámetros de entrada y salida del mismo tipo. Por ejemplo, un cliente Web de ASP.NET puede cambiar un método Web de BizTalk desde **string myService (parte de la cadena)** a **void myService (parte de cadena ref)**.  
  
> [!NOTE]
>  Si la recepción puerto está definido como unidireccional, el tipo de respuesta de método Web es **void** y no se devuelve información al cliente Web. La orquestación y el adaptador de SOAP no devuelven excepciones iniciadas al cliente Web.  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Convenciones de nomenclatura de servicios Web para orquestaciones publicadas  
 El Asistente para publicar servicios Web de BizTalk genera nombres de archivos de servicios Web (.asmx) basados en las descripciones que haya definido en la página Servicio Web. La siguiente tabla muestra los valores predeterminados para los nombres de archivos de servicios Web.  
  
|Servicio Web generado|Nombre de archivo|  
|---------------------------|---------------|  
|BizTalkWebService|Nombre de proyecto del servicio Web de Visual Studio|  
|WebService1|Nombre del archivo del servicio Web (.asmx)|  
|WebMethod1|Nombre del método Web|  
  
 El servicio Web generado no refleja los nombres de los nodos restantes.  
  
## <a name="see-also"></a>Vea también  
 [Publicar esquemas como servicios Web](../core/publishing-schemas-as-a-web-service.md)   
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar esquemas como servicios Web](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)