---
title: "Creación de esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac019276923467fe2d95f5a0a0b4a7b53513e9c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-schemas"></a><span data-ttu-id="5b755-102">Creación de esquemas</span><span class="sxs-lookup"><span data-stu-id="5b755-102">Creating Schemas</span></span>
<span data-ttu-id="5b755-103">Puede usar el Editor de BizTalk para crear dos tipos de esquemas: esquemas y esquemas de propiedades de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5b755-103">You can use BizTalk Editor to create two types of schemas: message schemas and property schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b755-104">Hay varios tipos de esquemas de mensaje, como esquemas de mensaje XML, esquema de mensaje de archivo sin formato y esquemas de sobres.</span><span class="sxs-lookup"><span data-stu-id="5b755-104">There are several types of message schemas, including XML message schemas, flat file message schemas, and envelope schemas.</span></span>  
  
 <span data-ttu-id="5b755-105">Los esquemas de mensaje definen la estructura y restringen el contenido de los mensajes que tiene previsto intercambiar con los socios comerciales o las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5b755-105">Message schemas define the structure and constrain the content of messages that you expect to send to, and receive from, your trading partners or applications.</span></span> <span data-ttu-id="5b755-106">Esquemas de mensaje son los tipos más comunes de esquemas que se va a usar con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b755-106">Message schemas are the most common types of schemas that you will use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5b755-107">puede crear esquemas de mensaje XML para los documentos empresariales y los sobres utilizados para contenerlos, y mediante el uso de la extensión de archivo sin formato en el Editor de BizTalk, se pueden crear esquemas de mensaje de archivo sin formato, incluyendo los esquemas para encabezados, cuerpos y finalizadores.</span><span class="sxs-lookup"><span data-stu-id="5b755-107"> can create XML message schemas for both business documents and the envelopes used to contain them, and through the use of the Flat File Extension to BizTalk Editor, it can create flat file message schemas, including schemas for headers, bodies and trailers.</span></span>  
  
 <span data-ttu-id="5b755-108">Los esquemas de propiedades son un tipo especial de esquema.</span><span class="sxs-lookup"><span data-stu-id="5b755-108">Property schemas are a special type of schema.</span></span> <span data-ttu-id="5b755-109">Proporcionan una plantilla de validación para los datos de campos y registros que se promocionan desde un mensaje de instancia en lo que se conoce como el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5b755-109">Property schemas provide a validation template for field and/or record data that is promoted from within an instance message into what is known as the message context.</span></span> <span data-ttu-id="5b755-110">La finalidad de los esquemas de propiedades es ofrecer una definición formal y segura de los tipos de datos que se van a promocionar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b755-110">The purpose of property schemas is to provide a formal, strongly typed definition of the data to be promoted at run time.</span></span>  
  
 <span data-ttu-id="5b755-111">Promoción de propiedades ofrece un mecanismo centralizado de extraer bloques principales de información, definidos por el usuario, desde dentro de un mensaje de instancia y hacerla más fácilmente accesible a los componentes de BizTalk Server manipulan el mensaje a medida que pasa a través de BizTalk Servidor.</span><span class="sxs-lookup"><span data-stu-id="5b755-111">Property promotion provides a centralized mechanism for pulling key pieces of information, defined by you, from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span> <span data-ttu-id="5b755-112">Un uso habitual de las propiedades promocionadas es hacer corresponder una instancia de mensaje con una suscripción, lo que permite enrutar adecuadamente el mensaje para procesarlo.</span><span class="sxs-lookup"><span data-stu-id="5b755-112">One common use of promoted properties is in matching a message instance to a subscription, allowing the message to be properly routed for processing.</span></span>  
  
 <span data-ttu-id="5b755-113">En esta sección se describen los modos que puede utilizar para crear distintos tipos de esquemas en BizTalk Server y se explican cuestiones relacionadas con varios tipos de esquemas.</span><span class="sxs-lookup"><span data-stu-id="5b755-113">This section describes the ways in which you can create different types of schemas within BizTalk Server, and presents related subjects that pertain to multiple types of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b755-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5b755-114">In This Section</span></span>  
  
-   [<span data-ttu-id="5b755-115">Administrar esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="5b755-115">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)  
  
-   [<span data-ttu-id="5b755-116">Administrar los nodos de un esquema</span><span class="sxs-lookup"><span data-stu-id="5b755-116">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)  
  
-   [<span data-ttu-id="5b755-117">Promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="5b755-117">Promoting Properties</span></span>](../core/promoting-properties.md)