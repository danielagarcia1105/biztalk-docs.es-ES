---
title: Cómo asignar Values2 de propiedad de contexto de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afb08895ba841ce2e99399ea9590b05394102472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006389"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="903f3-102">Cómo asignar valores de propiedad de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="903f3-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="903f3-103">Para administrar la sesión de conexión de J.D. Edwards OneWorld a partir de una orquestación de BizTalk, debe agregar la referencia a Microsoft.BizTalk.Adapters.JDEProperties.dll al proyecto.</span><span class="sxs-lookup"><span data-stu-id="903f3-103">To manage the JD Edwards OneWorld connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="903f3-104">Este ensamblado se encuentra en %SystemDrive%\Archivos de programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span><span class="sxs-lookup"><span data-stu-id="903f3-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="903f3-105">Tras hacer referencia a este esquema de propiedad, otras propiedades de contexto son accesibles para varias herramientas de desarrollo de BizTalk, por ejemplo, la forma Asignación de mensajes en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="903f3-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="903f3-106">Para obtener acceso a una propiedad de contexto, especifique una de las disponibles en el espacio de nombres de J.D. Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="903f3-106">To access a context property, you specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span> <span data-ttu-id="903f3-107">Para leer una propiedad de contexto de un mensaje recibido desde un puerto enlazado con el adaptador de Microsoft BizTalk para JD Edwards OneWorld, use la sintaxis, el mensaje (JDE. Propiedad), en una expresión.</span><span class="sxs-lookup"><span data-stu-id="903f3-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="903f3-108">Para obtener una lista de propiedades, consulte Administración de sesiones de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="903f3-108">Refer to JD Edwards OneWorld Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="903f3-109">En BizTalk, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="903f3-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-a-message-context-property-value"></a><span data-ttu-id="903f3-110">Procedimiento para asignar un valor de propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="903f3-110">To assign a message context property value</span></span>  
  
1. <span data-ttu-id="903f3-111">Crear un nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="903f3-111">Create a new message.</span></span>  
  
2. <span data-ttu-id="903f3-112">Establecer el contenido del mensaje, por ejemplo mediante la asignación de un mensaje existente.</span><span class="sxs-lookup"><span data-stu-id="903f3-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3. <span data-ttu-id="903f3-113">Establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="903f3-113">Set the properties.</span></span>  
  
   <span data-ttu-id="903f3-114">Para asignar propiedades de contexto a un mensaje destinado a un puerto de envío enlazado con el adaptador de Microsoft BizTalk para J.D. Edwards OneWorld, use el operador de asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="903f3-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the message assignment operator.</span></span> <span data-ttu-id="903f3-115">Después, especifique una de las propiedades de contexto disponibles en el espacio de nombres de J.D. Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="903f3-115">Then, specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span>  
  
   <span data-ttu-id="903f3-116">La sintaxis es: `Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="903f3-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903f3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="903f3-117">See Also</span></span>  
 <span data-ttu-id="903f3-118">[Uso de propiedades de contexto de mensaje](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="903f3-118">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="903f3-119">[Administración de sesiones](../core/about-session-management1.md) </span><span class="sxs-lookup"><span data-stu-id="903f3-119">[About Session Management](../core/about-session-management1.md) </span></span>  
 [<span data-ttu-id="903f3-120">Tutorial: Uso del adaptador de BizTalk para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="903f3-120">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)