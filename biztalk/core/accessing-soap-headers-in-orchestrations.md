---
title: Obtener acceso a los encabezados SOAP en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, properties
- orchestrations, SOAP headers
ms.assetid: 91fe053a-3f16-497c-b4bb-5fb54bec62e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 516b2bcc57bef507a028f30c61fd329a5fd7a598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225924"
---
# <a name="accessing-soap-headers-in-orchestrations"></a>Obtener acceso a los encabezados SOAP en orquestaciones
Puede obtener acceso a las propiedades de contexto de encabezados SOAP en orquestaciones para encabezados SOAP definidos y desconocidos. Para obtener más información sobre propiedades de contexto y esquemas de propiedades, vea [esquemas de propiedades](../core/property-schemas.md).  
  
## <a name="defined-soap-header-context-properties"></a>Propiedades de contexto de encabezado SOAP definidas  
 Las propiedades de contexto de encabezado SOAP definidas en orquestaciones requieren un esquema de propiedad. El esquema de propiedad debe tener el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**y el **Property Schema Base** propiedad establecida en  **MessageContextPropertyBase**. Cada nombre de elemento raíz en el esquema de propiedad debe coincidir con el nombre del elemento raíz del encabezado SOAP definido. A continuación, puede tener acceso a los valores de las propiedades de contexto mediante el espacio de nombres del esquema de propiedad y el nombre de propiedad. El espacio de nombres del esquema de propiedad es diferente del espacio de nombres de destino mencionados anteriormente. Aunque el espacio de nombres del esquema de propiedad puede ser cualquier cadena, normalmente es el nombre del proyecto.  
  
 En el ejemplo siguiente se muestra el acceso a la propiedad de contexto del encabezado SOAP para un espacio de nombres del esquema de propiedad **SOAPHeader**y el nombre de propiedad **OrigDest**:  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  Los encabezados SOAP definidos se tratan como encabezados "in" o "out". Si el asistente define el mismo encabezado SOAP para el mensaje de solicitud y de respuesta, el asistente no devolverá automáticamente el valor entrante en la respuesta. Debe copiar explícitamente la propiedad de contexto del encabezado SOAP del mensaje de solicitud en la propiedad de contexto del encabezado SOAP del mensaje de respuesta.  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a>Copiar la propiedad de contexto del encabezado SOAP del mensaje entrante  
 Puede copiar la propiedad de contexto del encabezado SOAP de un mensaje entrante en la misma propiedad de contexto del encabezado SOAP del mensaje de respuesta.  
  
 El siguiente ejemplo muestra cómo copiar la propiedad de contexto del encabezado SOAP:  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 Cuando se crean encabezados SOAP para la respuesta SOAP, asegúrese de que crea los encabezados SOAP correctamente. El adaptador de SOAP no comprueba el contenido de las propiedades de contexto del encabezado SOAP. Si los valores de los encabezados SOAP de respuesta son incorrectos, el adaptador de SOAP no podrá enviar el mensaje de respuesta al consumidor del servicio Web.  
  
## <a name="unknown-soap-header-context-property"></a>Propiedad de contexto de encabezado SOAP desconocida  
 La propiedad de contexto de encabezado SOAP desconocida no requiere un esquema de propiedad. Puede tener acceso a esta propiedad de contexto global **SOAP. UnknownHeaders**.  
  
 En el ejemplo siguiente se muestra el acceso a la propiedad de contexto de encabezado SOAP desconocida **SOAP. UnknownHeaders**:  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 Los valores contenidos en las propiedades de contexto son cadenas que contienen datos XML. La manera más sencilla de obtener acceso a estos datos consiste en usar el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** y dar forma a cargar la cadena en un **XmlDocument** y usar Consultas XPATH para tener acceso a campos específicos. Para obtener más información, creación de documentos XML en el Editor de expresiones de BizTalk, consulte [lenguaje XLANG s](../core/xlang-s-language.md).  
  
 Las propiedades de contexto están asociadas con un mensaje concreto. El motor de mensajería no asigna automáticamente los valores de los encabezados SOAP desconocidos desde el mensaje de solicitud al mensaje de respuesta. Al crear el mensaje de respuesta para un servicio Web, debe establecer específicamente los valores del encabezado SOAP. El comando siguiente es el método más sencillo de establecer una propiedad de contexto del encabezado SOAP:  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 También puede conseguirlo mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto.  
  
> [!NOTE]
>  Si el **SOAP. UnknownHeaders** propiedad es nula, BizTalk devuelve automáticamente los encabezados desconocidos recibidos en la solicitud SOAP en la respuesta SOAP. Si el **SOAP. UnknownHeaders** propiedad de contexto del mensaje de respuesta no es null, a continuación, BizTalk devuelve ese valor a la respuesta SOAP.  
  
## <a name="see-also"></a>Vea también  
 [Encabezados SOAP con servicios Web publicados](../core/soap-headers-with-published-web-services.md)