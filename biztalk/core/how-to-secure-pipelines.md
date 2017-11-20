---
title: "Cómo proteger canalizaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 903e9faec81ce58aac243fb7a22bac6678a81a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-secure-pipelines"></a><span data-ttu-id="af111-102">Cómo proteger las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="af111-102">How to Secure Pipelines</span></span>

## <a name="authentication-trusted"></a><span data-ttu-id="af111-103">Autenticación de confianza</span><span class="sxs-lookup"><span data-stu-id="af111-103">Authentication trusted</span></span>
<span data-ttu-id="af111-104">Los hosts se pueden marcar en la consola de administración como **autenticación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="af111-104">Hosts can be marked in the administration console as **Authentication Trusted**.</span></span> <span data-ttu-id="af111-105">Un host con Autenticación de confianza supone que Microsoft BizTalk Server confiará en las propiedades de seguridad enviadas en el contexto del mensaje de un mensaje de este host.</span><span class="sxs-lookup"><span data-stu-id="af111-105">Denoting a host as Authentication Trusted means that the Microsoft BizTalk Server will trust the security-related properties sent on the message context of a message from that host.</span></span> <span data-ttu-id="af111-106">Las propiedades relacionadas con la seguridad en el contexto del mensaje son los **OriginatorPID**, que corresponde a la propiedad de contexto de mensaje BTS. Sourcepartyid de esta y el **OriginatorSID**, que corresponde a la propiedad de contexto de mensaje **BTS. WindowsUser**.</span><span class="sxs-lookup"><span data-stu-id="af111-106">The security-related properties on the message context are the **OriginatorPID**, which corresponds to the message context property BTS.SourcePartyID, and the **OriginatorSID**, which corresponds to the message context property **BTS.WindowsUser**.</span></span> <span data-ttu-id="af111-107">Para obtener más información, consulte **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="af111-107">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="af111-108">Un host que está marcado como **autenticación de confianza** tiene permiso para indicar que el host de confianza está agregando un mensaje a la cola de alguien que no es él como remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="af111-108">A host that is marked as **Authentication Trusted** is allowed to indicate that the trusted host is adding a message to the queue from someone other than itself as the sender of the message.</span></span> <span data-ttu-id="af111-109">En otras palabras, los hosts que no están marcados como **autenticación de confianza** no tiene permiso para agregar un mensaje a la cola de un remitente del mensaje que ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="af111-109">In other words, hosts that are not marked as **Authentication Trusted** are not allowed to add a message to the queue from a message sender other than themselves.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af111-110">El componente de canalización de descodificador de MIME/SMIME no comprueba la fecha de caducidad de los certificados de descifrado.</span><span class="sxs-lookup"><span data-stu-id="af111-110">The MIME/SMIME Decoder pipeline component does not check the expiration date of decryption certificates.</span></span> <span data-ttu-id="af111-111">Sin embargo, sí comprueba la fecha de caducidad de los certificados de firma.</span><span class="sxs-lookup"><span data-stu-id="af111-111">However, it does check the expiration date of signing certificates.</span></span>  
  
 <span data-ttu-id="af111-112">Para obtener información acerca de la codificación y descodificación de mensajes enviados a través de SMTP o HTTP, vea [componente de canalización de codificador de MIME-SMIME](../core/mime-smime-encoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="af111-112">For information about encoding and decoding messages sent over SMTP or HTTP, see [MIME-SMIME Encoder Pipeline Component](../core/mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="af111-113">Consulte también [componente de canalización de descodificador de MIME-SMIME](../core/mime-smime-decoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="af111-113">Also see [MIME-SMIME Decoder Pipeline Component](../core/mime-smime-decoder-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="af111-114">Para obtener información acerca de la comprobación de firma cuando se trabaja con terceros, vea [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="af111-114">For information about signature verification when dealing with third parties, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span> <span data-ttu-id="af111-115">Consulte también [cómo crear un acuerdo](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span><span class="sxs-lookup"><span data-stu-id="af111-115">Also see [How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af111-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="af111-116">See Also</span></span>  
 <span data-ttu-id="af111-117">[Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="af111-117">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="af111-118">Desarrollar componentes de canalización personalizado</span><span class="sxs-lookup"><span data-stu-id="af111-118">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)