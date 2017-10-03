---
title: "Adaptador de WCF preguntas más frecuentes: Los extremos WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccc94b7d-b8a6-4c24-907e-922fd885b874
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d09bb2fd72d9b1882b4e0a9eb329da7e080e6fe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-wcf-endpoints"></a>P+F del adaptador WCF: Los extremos WCF
## <a name="what-are-two-endpoints-options-can-be-created-by-the-biztalk-wcf-service-publishing-wizard"></a>¿Qué dos opciones de extremos puede crear el Asistente para publicación de Servicio WCF de BizTalk?  
 Al ejecutar el Asistente para publicación de Servicio WCF de BizTalk, tiene la opción de crear un extremo de Servicio WCF o un extremo de solo metadatos de WCF (MEX).  
  
 Un extremo de servicio crea una ubicación web real hospedada en IIS que muestra la funcionalidad de un Servicio WCF real. Únicamente los adaptadores aislados (WCF-WsHttp, WCF-BasicHttp y WCF-CustomIsolated) se pueden usar para extremos de servicio. La funcionalidad de este tipo de extremo se implementa mediante una orquestación o un esquema que se publica como Servicio WCF.  
  
 Un extremo de solo metadatos es aquél cuya funcionalidad se implementa a través de una ubicación de recepción de BizTalk.  Usa IIS y un adaptador de recepción de WCF en curso en lugar de una orquestación expuesta o un código de Servicio WCF real. Uso del Asistente para generar un punto de conexión de solo metadatos se expone una manera más fácil de proporcionar información de integración en ubicaciones de recepción mediante un adaptador WCF en curso que hacerlo manualmente mediante svcutil.exe. Mediante svcutil.exe, tendrá que encontrar una manera para reenviar los metadatos para el consumidor del servicio, por lo que puede llamarse.  
  
## <a name="why-would-i-use-a-metadata-only-endpoint-in-biztalk-server"></a>¿Por qué debería usar un extremo de solo metadatos en BizTalk Server?  
 Con los extremos de solo metadatos, la implementación del servicio no existe en un Servicio WCF real. En vez de ello, la funcionalidad se implementa en una ubicación de recepción de BizTalk, que se llama igual que un Servicio WCF con un extremo de servicio. Por ejemplo, puede tener dos esquemas y una asignación para tomar un campo de un mensaje y convertirlo a mayúsculas. En este caso el servicio se publica en los metadatos como “ConvertToUpper”. Sin embargo, la funcionalidad del servicio se implementa en la ubicación de recepción y no en el código o a través de una orquestación.  
  
 Un extremo de WCF se compone de una dirección, un enlace y un contrato. Cuando el asistente crea un extremo de solo metadatos, obtiene los detalles de la dirección y el enlace de la ubicación de recepción que ya existe. La información de contrato se define mediante esquemas que pueden existir en una orquestación de BizTalk, o puede crearlas manualmente mediante el asistente. Si elige **publicar orquestaciones de BizTalk como un servicio WCF**, el punto de conexión de solo metadatos usa los tipos de mensaje y el puerto desde el ensamblado de orquestaciones para definir el contrato.  
  
 Si elige **publicar esquemas como servicio WCF**, el asistente le permite definir una definición de servicio especificando los nombres de servicio y la operación con los datos existentes y los esquemas de salida. El asistente crea un archivo .svc y un directorio virtual IIS para que se puedan examinar los metadatos después de publicarlos. El Asistente para publicación de servicio WCF de BizTalk también crea un archivo web.config con su atributo httpGetEnabled del \<serviceMetadata > elemento establecido en true. Esto publica los metadatos para que se puedan examinar. Si opta por publicar los metadatos del servicio de ubicación de recepción de BizTalk, que pueden tener acceso a datos a través de una solicitud GET a través de HTTP mediante un `?wsdl` al final de la dirección URL para el servicio.  
  
## <a name="are-service-endpoints-hosted-in-iis-and-why"></a>¿Los extremos de servicio se hospedan en IIS? ¿Por qué?  
 Sí, un extremo de servicio se hospeda en IIS y usa uno de los tres adaptadores aislados:  
  
-   WCF-WsHttp  
  
-   WCF-BasicHttp  
  
-   WCF-CustomIsolated  
  
 Un extremo de servicio difiere de un extremo de solo metadatos en el sentido que su funcionalidad se puede llamar directamente como un Servicio WCF. El uso del Asistente para publicación de Servicio WCF de BizTalk para crear un extremo de servicio da como resultado una nueva ubicación de recepción en la aplicación de BizTalk especificada. Define un URI al que la orquestación puede obtener acceso a través de IIS.  
  
## <a name="when-creating-a-service-endpoint-why-would-i-select-to-publish-schemas-as-a-wcf-service"></a>Al crear un extremo de servicio, ¿por qué debería seleccionar “Publicar esquemas como Servicio WCF”?  
 Elija la publicación de esquemas como Servicio WCF si la ubicación de recepción de WCF forma parte de una aplicación de BizTalk que usa únicamente la mensajería de BizTalk. Esto significa que no se usan orquestaciones y que toda la funcionalidad se expondrá mediante la ubicación de recepción y los puertos de envío. Los esquemas se publican para especificar la información de contrato. Esta información se puede obtener de un ensamblado de esquema o incluso de un ensamblado de orquestación (aunque la orquestación no se use para este extremo).