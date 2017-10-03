---
title: Construir mensajes Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, about Web messages
- Web messages, message types
- Web services, Web messages
- Web messages, parts
- Web messages
- messages, Web messages
ms.assetid: ca1792be-5fba-4f5d-a88e-b854f6a8ce33
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c344bbb836a6524ec1fd2656a5ba3f8bc8fad7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="constructing-web-messages"></a><span data-ttu-id="e5c09-102">Construcción de mensajes Web</span><span class="sxs-lookup"><span data-stu-id="e5c09-102">Constructing Web Messages</span></span>
<span data-ttu-id="e5c09-103">Construirá un mensaje Web a partir de un tipo de mensaje Web.</span><span class="sxs-lookup"><span data-stu-id="e5c09-103">You construct a Web message from a Web message type.</span></span> <span data-ttu-id="e5c09-104">Al agregar una referencia Web, BizTalk crea tipos de mensajes Web de forma automática basándose en los métodos Web del servicio Web agregado.</span><span class="sxs-lookup"><span data-stu-id="e5c09-104">When you add a Web reference, BizTalk automatically creates Web message types, which BizTalk creates based on the Web methods from the added Web service.</span></span> <span data-ttu-id="e5c09-105">Cuando se agrega un mensaje Web a la orquestación, se establece el tipo de mensaje como uno de los tipos de mensajes Web.</span><span class="sxs-lookup"><span data-stu-id="e5c09-105">You add a Web message to your orchestration, setting the message type to one of the Web message types.</span></span> <span data-ttu-id="e5c09-106">Las partes individuales de mensaje se crean en función de los tipos de esquemas o los tipos .NET primitivos.</span><span class="sxs-lookup"><span data-stu-id="e5c09-106">You create individual message parts based on primitive .NET or schema types.</span></span> <span data-ttu-id="e5c09-107">Aun así, es posible construir un mensaje Web que no contenga partes de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5c09-107">You can construct a Web message that contains no message parts.</span></span>  
  
 <span data-ttu-id="e5c09-108">**Tipos de mensajes Web**</span><span class="sxs-lookup"><span data-stu-id="e5c09-108">**Web message types**</span></span>  
  
 <span data-ttu-id="e5c09-109">Los tipos de mensajes Web, definidos en el archivo Reference.odx, son idénticos a un tipo de mensaje normal, con la excepción de que no se pueden modificar, cambiar de nombre o eliminar.</span><span class="sxs-lookup"><span data-stu-id="e5c09-109">Web message types, defined in the Reference.odx, are identical to a normal message type, except you cannot modify, rename or delete them.</span></span> <span data-ttu-id="e5c09-110">Para poder eliminar un tipo de mensaje Web, debe eliminar la referencia Web del proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e5c09-110">To delete a Web message type, you must remove the Web reference from your BizTalk project.</span></span>  
  
 <span data-ttu-id="e5c09-111">El proyecto de BizTalk crea un tipo de mensaje Web de solicitud y uno de respuesta para cada método Web del servicio Web agregado.</span><span class="sxs-lookup"><span data-stu-id="e5c09-111">BizTalk project creates one request and one response Web message type for each Web method in the added Web service.</span></span> <span data-ttu-id="e5c09-112">Si el método Web es una operación unidireccional, BizTalk sólo crea un tipo de mensaje Web de solicitud.</span><span class="sxs-lookup"><span data-stu-id="e5c09-112">If the Web method is a one-way operation, BizTalk only creates a request Web message type.</span></span> <span data-ttu-id="e5c09-113">Un tipo de mensaje Web de solicitud contiene una parte de mensaje para cada parámetro de entrada del método Web.</span><span class="sxs-lookup"><span data-stu-id="e5c09-113">A request Web message type contains one message part for each input parameter of the Web method.</span></span> <span data-ttu-id="e5c09-114">Un tipo de mensaje Web de respuesta contiene una parte de mensaje para el valor devuelto y otra para el parámetro de salida del método Web.</span><span class="sxs-lookup"><span data-stu-id="e5c09-114">A response Web message type contains one message part for the return value and one message part for each output parameter of the Web method.</span></span>  
  
 <span data-ttu-id="e5c09-115">Dependiendo del parámetro del método Web (de entrada o salida), BizTalk crea un tipo de mensaje Web a partir de un tipo de esquema o de un tipo .NET primitivo.</span><span class="sxs-lookup"><span data-stu-id="e5c09-115">Depending on the Web method parameter (input or output), BizTalk creates a Web message type from a primitive .NET type or a schema type.</span></span> <span data-ttu-id="e5c09-116">Si el parámetro del método Web es un tipo .NET primitivo, la parte de mensaje utiliza un tipo .NET primitivo.</span><span class="sxs-lookup"><span data-stu-id="e5c09-116">If the Web method parameter is a primitive .NET type, the message part uses a primitive .NET type.</span></span> <span data-ttu-id="e5c09-117">Si el parámetro del método Web es un tipo de esquema, BizTalk agrega el tipo de esquema al proyecto de BizTalk como un esquema de Reference.xsd.</span><span class="sxs-lookup"><span data-stu-id="e5c09-117">If the Web method parameter is a schema type, BizTalk adds the schema type to the BizTalk project as a schema in Reference.xsd.</span></span> <span data-ttu-id="e5c09-118">El esquema constituye la base de la parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5c09-118">The schema is the basis for the message part.</span></span> <span data-ttu-id="e5c09-119">Los esquemas Reference.xsd se encuentran en la carpeta de referencias Web.</span><span class="sxs-lookup"><span data-stu-id="e5c09-119">You can find Reference.xsd in the Web references folder.</span></span>  
  
 <span data-ttu-id="e5c09-120">No obstante, también puede crear tipos .NET de esquema y primitivos realizando una llamada a la clase .NET.</span><span class="sxs-lookup"><span data-stu-id="e5c09-120">Alternatively, you can create both primitive and schema .NET types by calling a .NET class.</span></span> <span data-ttu-id="e5c09-121">Para obtener más información sobre cómo crear tipos de mensaje mediante una clase. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="e5c09-121">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
 <span data-ttu-id="e5c09-122">**Mensajes Web**</span><span class="sxs-lookup"><span data-stu-id="e5c09-122">**Web messages**</span></span>  
  
 <span data-ttu-id="e5c09-123">Los mensajes Web son los mensajes que los usuarios utilizan al consumir un servicio Web (o al llamarlo).</span><span class="sxs-lookup"><span data-stu-id="e5c09-123">Web messages are the messages you use when you consume (call) a Web service.</span></span> <span data-ttu-id="e5c09-124">Para agregar un mensaje Web a una orquestación, debe seguir el mismo procedimiento que al agregar un mensaje normal, con la excepción de que el tipo de mensaje se establece en uno de los tipos de mensajes Web que BizTalk ha creado al agregarse una referencia Web.</span><span class="sxs-lookup"><span data-stu-id="e5c09-124">You add a Web message to an orchestration the same way that you add a regular message, except that you set the message type to one of the Web message types that BizTalk created when you added a Web reference.</span></span>  
  
 <span data-ttu-id="e5c09-125">**Partes de mensaje**</span><span class="sxs-lookup"><span data-stu-id="e5c09-125">**Message parts**</span></span>  
  
 <span data-ttu-id="e5c09-126">Después de crear el mensaje Web, debe construirse las partes individuales de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5c09-126">After you create the Web message, you construct the individual message parts.</span></span> <span data-ttu-id="e5c09-127">Si su parte de mensaje utiliza un tipo .NET primitivo, se utiliza un **asignación de mensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="e5c09-127">If your message part uses a primitive .NET type, you use a **Message Assignment** shape.</span></span> <span data-ttu-id="e5c09-128">Si su parte de mensaje utiliza un tipo de esquema, se utiliza un **transformar** forma o **asignación de mensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="e5c09-128">If your message part uses a schema type, you use a **Transform** shape or **Message Assignment** shape.</span></span> <span data-ttu-id="e5c09-129">Para obtener más información, consulte [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="e5c09-129">For more information, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5c09-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e5c09-130">In This Section</span></span>  
  
-   [<span data-ttu-id="e5c09-131">Cómo agregar mensajes Web</span><span class="sxs-lookup"><span data-stu-id="e5c09-131">How to Add Web Messages</span></span>](../core/how-to-add-web-messages.md)  
  
-   [<span data-ttu-id="e5c09-132">Cómo determinar un tipo de parte de mensaje Web</span><span class="sxs-lookup"><span data-stu-id="e5c09-132">How to Determine a Web Message Part Type</span></span>](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [<span data-ttu-id="e5c09-133">Cómo construir una parte de mensaje Web desde un tipo .NET primitivo</span><span class="sxs-lookup"><span data-stu-id="e5c09-133">How to Construct a Web Message Part from a Primitive .NET Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [<span data-ttu-id="e5c09-134">Cómo construir una parte de mensaje Web desde un tipo de esquema</span><span class="sxs-lookup"><span data-stu-id="e5c09-134">How to Construct a Web Message Part from a Schema Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [<span data-ttu-id="e5c09-135">Cómo construir un mensaje Web sin partes de mensaje</span><span class="sxs-lookup"><span data-stu-id="e5c09-135">How to Construct a Web Message with No Message Parts</span></span>](../core/how-to-construct-a-web-message-with-no-message-parts.md)