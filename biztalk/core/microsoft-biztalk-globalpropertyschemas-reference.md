---
title: Referencia de Microsoft.BizTalk.GlobalPropertySchemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2acf3083-a0a9-483f-88bf-8023d9933e1e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0944bd74ff995d4288b787eae820b97270ae9d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="microsoftbiztalkglobalpropertyschemas-reference"></a>Referencia de Microsoft.BizTalk.GlobalPropertySchemas
El **Microsoft.BizTalk.GlobalPropertySchemas** espacio de nombres contiene esquemas de propiedad para las propiedades que usan varios componentes de BizTalk Server. Este espacio de nombres contiene propiedades del sistema que utiliza el motor de BizTalk, propiedades específicas de transporte que cada transporte utiliza para controlar la configuración y propiedades para configurar componentes de canalización.  

## <a name="namespace-schemas"></a>Esquemas de Namespace  

 La siguiente tabla muestra los esquemas de propiedad global incluidos en el **Microsoft.BizTalk.GlobalPropertySchemas** espacio de nombres.  
  
|Esquema de propiedades|Área de características y descripción|  
|---------------------|----------------------------------|  
|bts-btf2-properties.xsd|Esquema de propiedad.|  
|btf2-endpoints-header.xsd<br /><br /> btf2-envelope.xsd<br /><br /> btf2-manifest-header.xsd<br /><br /> btf2-process-header.xsd<br /><br /> btf2-properties-header.xsd<br /><br /> btf2-receipt-header.xsd<br /><br /> btf2-services-header.xsd|Esquemas que definen las construcciones de BizTalk Framework. Estos esquemas son específicos de los componentes de canalización de ensamblador y de desensamblador de BizTalk Framework.|  
|bts-system-properties.xsd|Esquema de propiedad del sistema. El motor de BizTalk utiliza la mayoría de las propiedades de este esquema. Puede utilizar algunas propiedades para enrutamiento de mensajes. Para obtener más información sobre las propiedades que puede utilizar para enrutar los mensajes, consulte **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|  
|bts-endpoint-properties.xsd|Esquema de propiedad interno.|  
|bts-mime-properties.xsd<br /><br /> bts-xmlnorm-properties.xsd|Esquemas de propiedad para componentes de canalización: componentes de canalización de MIME, XML, archivos planos y ensamblador de BizTalk Framework y desensamblador.|  
|bts-legacy-properties.xsd|BizTalk utiliza este esquema para actualizar [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] aplicaciones [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] aplicaciones.|  
|bts-messagetracking-properties.xsd|Motor de seguimiento utiliza este esquema.|  
|bts-file-properties.xsd<br /><br /> bts-ftp-properties.xsd<br /><br /> bts-http-properties.xsd<br /><br /> bts-pop3-properties.xsd<br /><br /> bts-smtp-properties.xsd<br /><br /> soap-encoding_1__1.xsd<br /><br /> soap-envelope_1__1.xsd<br /><br /> bts-soap-properties.xsd<br /><br /> bts-WindowsSharePointServices-properties.xsd|Esquemas de propiedad específicos de transporte. Los transportes utilizan estos esquemas para trasladar información y configuraciones de transporte específicas. Para obtener más información sobre los transportes, consulte [usando adaptadores](../core/using-adapters.md).|  
|XLANGsBizTalkProperties.xsd|El motor de orquestaciones utiliza este esquema.|  
  
## <a name="see-also"></a>Vea también  
 [Referencias de Namespace de BizTalk incluidos en los proyectos de BizTalk](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)