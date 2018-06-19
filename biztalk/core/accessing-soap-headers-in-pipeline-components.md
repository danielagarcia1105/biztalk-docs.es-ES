---
title: Obtener acceso a los encabezados SOAP en componentes de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
ms.assetid: a2fb074e-0fde-487e-a6ec-7e2b543b7c8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e484b221df54f00b02f20ef89466fed6b99cd69d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225100"
---
# <a name="accessing-soap-headers-in-pipeline-components"></a>Obtener acceso a los encabezados SOAP en componentes de canalización
Puede obtener acceso a las propiedades de contexto de encabezados SOAP en componentes de canalización. Usar una combinación de nombre de la propiedad de contexto y el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.  
  
 En el ejemplo de código siguiente se obtiene el encabezado SOAP de solicitud en un componente de canalización de recepción para la propiedad **OrigDest**:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("OrigDest",    "http://schemas.microsoft.com/BizTalk/2003/SOAPHeader").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).  
  
## <a name="see-also"></a>Vea también  
 [Encabezados SOAP con servicios Web publicados](../core/soap-headers-with-published-web-services.md)