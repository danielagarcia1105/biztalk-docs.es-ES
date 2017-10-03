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
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a><span data-ttu-id="bbafe-102">Escribir propiedades de contexto AS2 para la resolución de entidades salientes</span><span class="sxs-lookup"><span data-stu-id="bbafe-102">Writing AS2 Context Properties for Outbound Party Resolution</span></span>
<span data-ttu-id="bbafe-103">La resolución del acuerdo del mensaje saliente AS2 puede llevarse a cabo usando la propiedad de contexto AS2To o la propiedad AS2To de la propiedad de contexto `Http.UserHttpHeaders`.</span><span class="sxs-lookup"><span data-stu-id="bbafe-103">Agreement resolution of outbound AS2 message can be performed using the AS2To context property or the AS2To property in the `Http.UserHttpHeaders` context property.</span></span> <span data-ttu-id="bbafe-104">No obstante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no escribe la propiedad AS2To en el contexto al recibir un mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="bbafe-104">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not write the AS2To property to the context upon receiving an AS2 message.</span></span> <span data-ttu-id="bbafe-105">Si desea realizar la resolución de contrato en la propiedad de contexto AS2To o UserHttpHeaders, deberá escribir una orquestación personalizada o un componente de canalización personalizado para ello.</span><span class="sxs-lookup"><span data-stu-id="bbafe-105">If you want to perform agreement resolution on the AS2To or UserHttpHeaders context property, you have to write a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="bbafe-106">Solo será necesario si el puerto de envío no se encuentra vinculado al acuerdo.</span><span class="sxs-lookup"><span data-stu-id="bbafe-106">This is required only if the send port is not linked to the agreement.</span></span>  
  
 <span data-ttu-id="bbafe-107">En una orquestación personalizada, puede anexar AS2-To al comienzo de la propiedad de contexto `Http.UserHttpHeaders` existente usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="bbafe-107">In a custom orchestration, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code:</span></span>  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 <span data-ttu-id="bbafe-108">En un componente de canalización personalizado, puede anexar AS2-To al comienzo de la propiedad de contexto `Http.UserHttpHeaders` existente usando el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="bbafe-108">In a custom pipeline component, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code.</span></span> <span data-ttu-id="bbafe-109">Es necesario anexar AS2-To a la propiedad de contexto `Http.UserHttpHeaders` antes de que el componente As2Encoder procese el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bbafe-109">You need to append AS2-To to `Http.UserHttpHeaders` context property before the message is processed by the As2Encoder component.</span></span>  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 <span data-ttu-id="bbafe-110">Para obtener más información acerca de cómo promocionar el `EDIIntAS.AS2To` propiedad o el `BTS.UseHttpHeaders` propiedad en el contexto, vea "Promoción de propiedades de contexto de encabezado de AS2" en la [enviar un mensaje AS2 a través de un puerto de envío de archivo](../core/sending-an-as2-message-over-a-file-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="bbafe-110">For more information on promoting the `EDIIntAS.AS2To` property or the `BTS.UseHttpHeaders` property to the context, see "Promoting AS2 Header Context Properties" in the [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
 <span data-ttu-id="bbafe-111">El código que se pueden agregar a un componente de canalización personalizado para escribir los encabezados de HTTP. Propiedad de contexto UserHttpHeaders en el mensaje, vea [enviar un mensaje AS2 a través de un puerto de envío de archivo](../core/sending-an-as2-message-over-a-file-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="bbafe-111">For code that you can add to a custom pipeline component to write the headers from the HTTP.UserHttpHeaders context property into the message, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbafe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbafe-112">See Also</span></span>  
 [<span data-ttu-id="bbafe-113">Desarrollar y configurar soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bbafe-113">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)