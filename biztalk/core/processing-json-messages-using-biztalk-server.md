---
title: Procesamiento de mensajes JSON con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db57847964c7e3da452675945b7d4557ae7cbc85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986349"
---
# <a name="processing-json-messages-using-biztalk-server"></a><span data-ttu-id="fcb87-102">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fcb87-102">Processing JSON messages using BizTalk Server</span></span>
> [!NOTE]
>  <span data-ttu-id="fcb87-103">Este tutorial solo se aplica a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fcb87-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="fcb87-104">En este tutorial se muestra cómo procesar mensajes JSON con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcb87-104">This tutorial demonstrates how to process JSON messages using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="fcb87-105">El tutorial usa componentes de canalización personalizados, ahora disponibles con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fcb87-105">The tutorial uses custom pipeline components, now available with BizTalk Server.</span></span> <span data-ttu-id="fcb87-106">Estos componentes de canalización convierten el mensaje JSON en XML mientras se recibe el mensaje en la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y convierten el mensaje de XML a JSON mientras se envía.</span><span class="sxs-lookup"><span data-stu-id="fcb87-106">These pipeline components convert the JSON message to XML (while receiving the message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration, and converts the message from XML to JSON while sending the message out.</span></span>  
  
## <a name="what-does-this-tutorial-do"></a><span data-ttu-id="fcb87-107">¿Qué hace este tutorial?</span><span class="sxs-lookup"><span data-stu-id="fcb87-107">What does this tutorial do?</span></span>  
 <span data-ttu-id="fcb87-108">Para mostrar el procesamiento de JSON, creamos un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que hace lo siguiente, en el orden especificado:</span><span class="sxs-lookup"><span data-stu-id="fcb87-108">To demonstrate JSON processing, we create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that does the following, in the given order:</span></span>  
  
1. <span data-ttu-id="fcb87-109">Recibe un pedido de compra JSON y, en la canalización de recepción, usa un componente descodificador de JSON para transformar el mensaje JSON en un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="fcb87-109">Receives a JSON purchase order and in the receive pipeline, uses a JSON decoder component to transform the JSON message to XML message.</span></span>  
  
2. <span data-ttu-id="fcb87-110">Transforma el pedido de compra XML en una factura XML usando una asignación.</span><span class="sxs-lookup"><span data-stu-id="fcb87-110">Transforms the XML purchase order into an XML invoice using a map.</span></span>  
  
3. <span data-ttu-id="fcb87-111">En la canalización de envío, usa un codificador JSON para transformar la factura XML en una factura JSON y la envía.</span><span class="sxs-lookup"><span data-stu-id="fcb87-111">In the send pipeline, uses a JSON encoder to transform the XML invoice into a JSON invoice and sends it out.</span></span>  
  
   <span data-ttu-id="fcb87-112">![Procesamiento de mensajes JSON en BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")</span><span class="sxs-lookup"><span data-stu-id="fcb87-112">![Processing JSON messages in BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="fcb87-113">Cómo usar este tutorial</span><span class="sxs-lookup"><span data-stu-id="fcb87-113">How to use this tutorial?</span></span>  
 <span data-ttu-id="fcb87-114">En este tutorial se basa en un ejemplo (**BTSJSON**) que puede descargarse desde el [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197).</span><span class="sxs-lookup"><span data-stu-id="fcb87-114">This tutorial is built around a sample (**BTSJSON**) that can be downloaded from the [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197).</span></span> <span data-ttu-id="fcb87-115">Puede usar el ejemplo y seguir este tutorial para comprender cómo se ha compilado el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fcb87-115">You could use the sample and go through this tutorial to understand how the sample was built.</span></span> <span data-ttu-id="fcb87-116">O bien, puede usar este tutorial para crear su propia solución desde cero.</span><span class="sxs-lookup"><span data-stu-id="fcb87-116">Or, you could use this tutorial to create your own solution ground-up.</span></span> <span data-ttu-id="fcb87-117">El tutorial está pensado para la segunda opción, de forma que pueda comprender cómo se compiló esta solución.</span><span class="sxs-lookup"><span data-stu-id="fcb87-117">This tutorial is targeted towards the second approach so that you understand how this solution was built.</span></span> <span data-ttu-id="fcb87-118">También, en la medida de lo posible, el tutorial es coherente con el ejemplo y usa los mismos nombres para los artefactos (por ejemplo, esquemas, transformaciones) que se usan en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fcb87-118">Also, as much as possible, the tutorial is consistent with the sample and uses the same names for artifacts (for example, schemas, transforms) as used in the sample.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcb87-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fcb87-119">In This Section</span></span>  
  
-   [<span data-ttu-id="fcb87-120">Generar un esquema XSD para mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="fcb87-120">Generate an XSD schema for JSON message</span></span>](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [<span data-ttu-id="fcb87-121">Crear canalizaciones personalizadas para procesar mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="fcb87-121">Create custom pipelines to process JSON messages</span></span>](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [<span data-ttu-id="fcb87-122">Crear una orquestación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fcb87-122">Create a BizTalk Server orchestration</span></span>](../core/create-a-biztalk-server-orchestration.md)  
  
-   [<span data-ttu-id="fcb87-123">Implementar y probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fcb87-123">Deploy and test the application</span></span>](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="fcb87-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcb87-124">See Also</span></span>  
 [<span data-ttu-id="fcb87-125">Tutoriales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fcb87-125">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)