---
title: POP3 Propiedades y esquema de propiedades de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, POP3 adapters
- Subject properties [POP3 adapters]
- Date properties [POP3 adapters]
- From properties [POP3 adapters]
- To properties [POP3 adapters]
- POP3 adapters, properties
- configuring [POP3 adapters], schemas
- configuring [POP3 adapters], properties
- CC properties [POP3 adapters]
- Headers properties [POP3 adapters]
- ReplyTo properties [POP3 adapters]
- DispositionNotificationTo properties [POP3 adapters]
ms.assetid: 7a10ae1f-dbcf-4c05-9a50-2503895960f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b976aba7161272ebdc65da2b5bcd2067c8cd3a5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264172"
---
# <a name="pop3-adapter-property-schema-and-properties"></a>POP3 Propiedades y esquema de propiedades de adaptador
La tabla siguiente enumera las propiedades del esquema de propiedades del adaptador de POP3.  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties  
  
|**Nombre**|**Tipo**|**Description**|  
|--------------|--------------|---------------------|  
|**Asunto**|xs:string|Especifica el contenido que aparece en el **asunto** encabezado del mensaje|  
|**De**|xs:string|Especifica la dirección de correo electrónico que aparece en el **de** campo de encabezado de mensaje de correo electrónico.|  
|**Para**|xs:string|Especifica la dirección de correo electrónico aparecen en la **a** campo de encabezado de mensaje de correo electrónico.|  
|**ReplyTo**|xs:string|Especifica la dirección de correo electrónico que aparece en el **ReplyTo** campo de encabezado de mensaje de correo electrónico.|  
|**CC**|xs:string|Especifica la dirección de correo electrónico aparecen en la **CC** campo de encabezado de mensaje de correo electrónico.|  
|**Fecha**|xs:string|Especifica el contenido que aparece en el **fecha** campo de encabezado de mensaje de correo electrónico.|  
|**DispositionNotificationTo**|xs:string|Especifica el contenido que aparece en el **DispositionNotificationTo** campo de encabezado de mensaje de correo electrónico.|  
|**Encabezados**|xs:string|Especifica el contenido de todos los campos de encabezado del mensaje de correo electrónico.|  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de POP3](../core/configuring-the-pop3-adapter.md)