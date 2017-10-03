---
title: "Escribir propiedades de contexto AS2 para la resolución de entidades salientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c89804c42554825e387d01ff592e3a628e8225b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a>Escribir propiedades de contexto AS2 para la resolución de entidades salientes
La resolución del acuerdo del mensaje saliente AS2 puede llevarse a cabo usando la propiedad de contexto AS2To o la propiedad AS2To de la propiedad de contexto `Http.UserHttpHeaders`. No obstante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no escribe la propiedad AS2To en el contexto al recibir un mensaje AS2. Si desea realizar la resolución de contrato en la propiedad de contexto AS2To o UserHttpHeaders, deberá escribir una orquestación personalizada o un componente de canalización personalizado para ello. Solo será necesario si el puerto de envío no se encuentra vinculado al acuerdo.  
  
 En una orquestación personalizada, puede anexar AS2-To al comienzo de la propiedad de contexto `Http.UserHttpHeaders` existente usando el siguiente código:  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 En un componente de canalización personalizado, puede anexar AS2-To al comienzo de la propiedad de contexto `Http.UserHttpHeaders` existente usando el siguiente código. Es necesario anexar AS2-To a la propiedad de contexto `Http.UserHttpHeaders` antes de que el componente As2Encoder procese el mensaje.  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 Para obtener más información acerca de cómo promocionar el `EDIIntAS.AS2To` propiedad o el `BTS.UseHttpHeaders` propiedad en el contexto, vea "Promoción de propiedades de contexto de encabezado de AS2" en la [enviar un mensaje AS2 a través de un puerto de envío de archivo](../core/sending-an-as2-message-over-a-file-send-port.md).  
  
 El código que se pueden agregar a un componente de canalización personalizado para escribir los encabezados de HTTP. Propiedad de contexto UserHttpHeaders en el mensaje, vea [enviar un mensaje AS2 a través de un puerto de envío de archivo](../core/sending-an-as2-message-over-a-file-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)