---
title: Formas de usar el contenido del mensaje para controlar el procesamiento de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0036b9b16faf64d0768d2d5cc7ce1f828cfbffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009365"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a><span data-ttu-id="d5d16-102">Modos de usar el contenido de los mensajes para controlar el procesamiento de los mensajes</span><span class="sxs-lookup"><span data-stu-id="d5d16-102">Ways to Use Message Content to Control Message Processing</span></span>
<span data-ttu-id="d5d16-103">Hay dos tipos de promoción de propiedades: **campos distintivos** y **campos de propiedades**, la última de las cuales utiliza esquemas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5d16-103">There are two types of property promotion: **Distinguished Fields** and **Property Fields**, the latter of which uses property schemas.</span></span> <span data-ttu-id="d5d16-104">En el Editor de BizTalk, administra estos dos tipos de promoción de propiedades mediante el **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la  **Esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="d5d16-104">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5d16-105">Existen algunas restricciones en cuanto a los valores que puede promocionar.</span><span class="sxs-lookup"><span data-stu-id="d5d16-105">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="d5d16-106">Para obtener más información, vea la tabla en [promocionar propiedades](../core/promoting-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d5d16-106">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
 <span data-ttu-id="d5d16-107">Debe decidir el tipo de promoción de propiedades que usará según los detalles de la situación concreta.</span><span class="sxs-lookup"><span data-stu-id="d5d16-107">You must decide which type of property promotion to use based on the details of your scenario.</span></span> <span data-ttu-id="d5d16-108">Tenga en cuenta las siguientes diferencias entre **campo distintivo** promoción de propiedades y **campo de propiedad** promoción de propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5d16-108">Consider the following distinctions between **Distinguished Field** property promotion and **Property Field** property promotion:</span></span>  
  
- <span data-ttu-id="d5d16-109">**Campos distintivos** no puede participar en el enrutamiento de mensajes y, por tanto, no aparecen en las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="d5d16-109">**Distinguished Fields** cannot participate in message routing and therefore they do not appear in the filter expressions.</span></span> <span data-ttu-id="d5d16-110">Solo están disponibles dentro del contexto de una orquestación, pero tienen menos sobrecarga al enviar o recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="d5d16-110">They are only available within the context of an orchestration but they have less overhead when sending and receiving messages.</span></span>  
  
- <span data-ttu-id="d5d16-111">**Campos distintivos** no tiene ninguna limitación de tamaño.</span><span class="sxs-lookup"><span data-stu-id="d5d16-111">**Distinguished Fields** do not have any size limitations.</span></span> <span data-ttu-id="d5d16-112">**Campos de propiedades** se limitan a 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d5d16-112">**Property Fields** are limited to 255 characters.</span></span>  
  
- <span data-ttu-id="d5d16-113">**Campos distintivos** no requieren artefactos independientes para crearse, mientras que **campos de propiedades** requieren la creación y mantenimiento de un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5d16-113">**Distinguished Fields** do not require any separate artifacts to be created whereas **Property Fields** require the creation and maintenance of a property schema.</span></span>  
  
  <span data-ttu-id="d5d16-114">Considerando estas consideraciones, debe promocionar nodos como **campos de propiedades** solo cuando se va a usar las propiedades promocionadas para el enrutamiento de mensajes o con fines de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5d16-114">Drawing upon these considerations, you should promote nodes as **Property Fields** only when you intend to use the promoted properties for message routing or tracking purposes.</span></span> <span data-ttu-id="d5d16-115">En caso contrario, si solo va a obtener acceso a las propiedades promocionadas desde las orquestaciones, que debería aprovechar el hecho de que **campos distintivos** son mucho más barato, más ligero y más fácil de usar que  **Campos de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d5d16-115">Otherwise, if you are only going to access the promoted properties from within your orchestrations, you should take advantage of the fact that **Distinguished Fields** are much cheaper, more lightweight, and more easy-to-use than **Property Fields**.</span></span>  
  
  <span data-ttu-id="d5d16-116">Las propiedades promocionadas mediante el **campo distintivo** mecanismo solo son accesible desde las orquestaciones y no es accesible desde las canalizaciones, puertos y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d5d16-116">Properties promoted by using the **Distinguished Field** mechanism are only accessible from within orchestrations and cannot be accessed from pipelines, ports, and so on.</span></span> <span data-ttu-id="d5d16-117">Por otro lado, las propiedades promocionan mediante el **campos de propiedades** y mecanismo de propiedad de esquema son accesibles desde todos estos componentes.</span><span class="sxs-lookup"><span data-stu-id="d5d16-117">On the other hand, properties promoted by using the **Property Fields** and property schema mechanism are accessible from all of these components.</span></span> <span data-ttu-id="d5d16-118">Otra diferencia importante es que los valores de los campos de propiedades tienen una limitación de 255 caracteres y que los de los campos distintivos no tienen dicha limitación.</span><span class="sxs-lookup"><span data-stu-id="d5d16-118">Another important difference is that property field values are limited to 255 characters and distinguished field values have no such limit.</span></span>  
  
  <span data-ttu-id="d5d16-119">En esta sección se proporciona información acerca de estos dos tipos de promoción de propiedades, incluida la información acerca de cómo establecer dichas propiedades promocionadas para un esquema de mensaje mediante el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d5d16-119">This section provides information about these two types of property promotion, including how information about how to establish such promoted properties for a message schema by using BizTalk Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5d16-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5d16-120">In This Section</span></span>  
  
-   [<span data-ttu-id="d5d16-121">Propiedades de contexto de mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d5d16-121">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)  
  
-   [<span data-ttu-id="d5d16-122">Procesamiento de mensajes de instancia con campos distintivos</span><span class="sxs-lookup"><span data-stu-id="d5d16-122">Instance Message Processing Using Distinguished Fields</span></span>](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [<span data-ttu-id="d5d16-123">Procesamiento de mensajes de instancia con promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="d5d16-123">Instance Message Processing Using Property Promotion</span></span>](../core/instance-message-processing-using-property-promotion.md)