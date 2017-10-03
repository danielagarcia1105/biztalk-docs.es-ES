---
title: "Cómo asignar Values2 de propiedad de contexto de mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f0e19a425a4842e3bfac150d1cac851e4686f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="48f3b-102">Cómo asignar valores de propiedad de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="48f3b-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="48f3b-103">Para administrar la sesión de conexión de J.D. Edwards OneWorld a partir de una orquestación de BizTalk, debe agregar la referencia a Microsoft.BizTalk.Adapters.JDEProperties.dll al proyecto.</span><span class="sxs-lookup"><span data-stu-id="48f3b-103">To manage the JD Edwards OneWorld connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="48f3b-104">Este ensamblado se encuentra en %SystemDrive%\Archivos de programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span><span class="sxs-lookup"><span data-stu-id="48f3b-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="48f3b-105">Tras hacer referencia a este esquema de propiedad, otras propiedades de contexto son accesibles para varias herramientas de desarrollo de BizTalk, por ejemplo, la forma Asignación de mensajes en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="48f3b-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="48f3b-106">Para obtener acceso a una propiedad de contexto, especifique una de las disponibles en el espacio de nombres de J.D. Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="48f3b-106">To access a context property, you specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span> <span data-ttu-id="48f3b-107">Para leer una propiedad de contexto de un mensaje recibido de un puerto enlazado con el adaptador de BizTalk para JD Edwards OneWorld, use la sintaxis, mensaje (JDE. Propiedad), en una expresión.</span><span class="sxs-lookup"><span data-stu-id="48f3b-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="48f3b-108">Para obtener una lista de propiedades, consulte Administración de sesiones de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="48f3b-108">Refer to JD Edwards OneWorld Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="48f3b-109">En BizTalk, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="48f3b-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-a-message-context-property-value"></a><span data-ttu-id="48f3b-110">Procedimiento para asignar un valor de propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="48f3b-110">To assign a message context property value</span></span>  
  
1.  <span data-ttu-id="48f3b-111">Crear un nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="48f3b-111">Create a new message.</span></span>  
  
2.  <span data-ttu-id="48f3b-112">Establecer el contenido del mensaje, por ejemplo mediante la asignación de un mensaje existente.</span><span class="sxs-lookup"><span data-stu-id="48f3b-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3.  <span data-ttu-id="48f3b-113">Establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="48f3b-113">Set the properties.</span></span>  
  
 <span data-ttu-id="48f3b-114">Para asignar propiedades de contexto a un mensaje destinado a un puerto de envío enlazado con el adaptador de Microsoft BizTalk para J.D. Edwards OneWorld, use el operador de asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="48f3b-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the message assignment operator.</span></span> <span data-ttu-id="48f3b-115">Después, especifique una de las propiedades de contexto disponibles en el espacio de nombres de J.D. Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="48f3b-115">Then, specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span>  
  
 <span data-ttu-id="48f3b-116">La sintaxis es:`Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="48f3b-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f3b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="48f3b-117">See Also</span></span>  
 <span data-ttu-id="48f3b-118">[Usar propiedades de contexto de mensaje](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="48f3b-118">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="48f3b-119">[Administración de sesiones](../core/about-session-management1.md) </span><span class="sxs-lookup"><span data-stu-id="48f3b-119">[About Session Management](../core/about-session-management1.md) </span></span>  
 [<span data-ttu-id="48f3b-120">Tutorial: Usar el adaptador de BizTalk para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="48f3b-120">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)