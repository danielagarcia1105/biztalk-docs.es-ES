---
title: "Cómo determinar un tipo de parte de mensaje Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd01d549ffbc6c299124b63df73b82f874cb4d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-determine-a-web-message-part-type"></a><span data-ttu-id="535c4-102">Cómo determinar un tipo de parte de mensaje web</span><span class="sxs-lookup"><span data-stu-id="535c4-102">How to Determine a Web Message Part Type</span></span>
<span data-ttu-id="535c4-103">Se puede determinar si un tipo de parte de un mensaje Web es un tipo .NET primitivo o un tipo de esquema mediante la ventana Propiedades de un tipo de mensaje Web concreto.</span><span class="sxs-lookup"><span data-stu-id="535c4-103">You can determine if a Web message part type is a primitive .NET type or a schema type by using the Properties window for a given Web message type.</span></span>  
  
### <a name="to-determine-a-web-message-part-type"></a><span data-ttu-id="535c4-104">Para determinar un tipo de parte de mensaje Web</span><span class="sxs-lookup"><span data-stu-id="535c4-104">To determine a Web message part type</span></span>  
  
1.  <span data-ttu-id="535c4-105">Con una orquestación abierta, en el **vista** menú, haga clic en **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="535c4-105">With an orchestration open, on the **View** menu, click **Other Windows**,and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="535c4-106">Expanda el **tipos de mensaje de varias partes** nodo y, a continuación, expanda un tipo de mensaje Web.</span><span class="sxs-lookup"><span data-stu-id="535c4-106">Expand the **Multi-part Message Types** node, and then expand a Web message type.</span></span>  
  
3.  <span data-ttu-id="535c4-107">Seleccione una parte de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="535c4-107">Select a message part.</span></span>  
  
     <span data-ttu-id="535c4-108">Una firma de parte de mensaje Web que comienza por  **\<* espacio de nombres predeterminado del proyecto*>.\< *Nombre de referencia web*>. Referencia. \< *raíz del esquema*> ** es un tipo de esquema.</span><span class="sxs-lookup"><span data-stu-id="535c4-108">A Web message part signature that begins as **\<*project default namespace*>.\<*Web reference name*>.Reference.\<*schema root*>** is a schema type.</span></span> <span data-ttu-id="535c4-109">El  **\<* raíz del esquema*> ** parte del tipo es el elemento raíz del esquema de referencia Web que construye la parte del mensaje Web.</span><span class="sxs-lookup"><span data-stu-id="535c4-109">The **\<*schema root*>** part of the type is the root element of the Web reference schema that constructs the Web message part.</span></span> <span data-ttu-id="535c4-110">En caso contrario, la firma de la parte de mensaje es un tipo .NET primitivo como **System.String** o **System.Int32**.</span><span class="sxs-lookup"><span data-stu-id="535c4-110">Otherwise, the message part signature is a primitive .NET type such as **System.String** or **System.Int32**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535c4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="535c4-111">See Also</span></span>  
 [<span data-ttu-id="535c4-112">Construcción de mensajes Web</span><span class="sxs-lookup"><span data-stu-id="535c4-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)