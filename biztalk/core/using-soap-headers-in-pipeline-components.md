---
title: "Usar encabezados SOAP en componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
- Web services, SOAP headers
- creating, SOAP headers
ms.assetid: 5b4a8902-e8f5-44a4-88f7-17f47a9deecd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c11b74aafe53150ced42d0c53a2e19a2c5080fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-pipeline-components"></a>Usar encabezados SOAP en componentes de canalización
Para obtener acceso a las propiedades de contexto del encabezado SOAP en componentes de canalización, utilice una combinación del contexto propiedad nombre y destino de espacio de nombres como se describe en [utilizar encabezados SOAP en orquestaciones](../core/using-soap-headers-in-orchestrations.md).  
  
 En el ejemplo de código siguiente se establece el encabezado SOAP de solicitud en un componente de canalización de envío para un nombre de propiedad **OrigDest**:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<?xml version=\"1.0\"?>  
          <OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </OrigDest>";  
inmsg.Context.Write("OrigDest","http://schemas.microsoft.com/BizTalk/2003/SOAPHeader", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).  
  
> [!NOTE]
>  Cuando consume servicios Web (llamada) de una orquestación, el adaptador de SOAP sólo admite canalizaciones de envío y de recepción de estilo de paso a través. Se puede usar una canalización personalizada, pero no puede contener componentes que modifican las partes del cuerpo del mensaje. Estos componentes incluyen el ensamblador de XML, desensamblador de XML y validador de XML.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones predeterminadas](../core/default-pipelines.md)   
 [Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md)