---
title: Los pasos del desarrollo de una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- designing, orchestrations
- orchestrations, designing
- orchestrations, creating
- creating, orchestrations
- Copy Local property
ms.assetid: 556b1e6c-63a6-4805-a0a5-e555f198fe4e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd0a19754871a6e736365e622513b193dcbf06a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277396"
---
# <a name="steps-in-orchestration-development"></a><span data-ttu-id="627c6-102">Pasos del desarrollo de una orquestación</span><span class="sxs-lookup"><span data-stu-id="627c6-102">Steps in Orchestration Development</span></span>
<span data-ttu-id="627c6-103">Para desarrollar una orquestación, normalmente se realizan las acciones básicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="627c6-103">To develop an orchestration, you typically perform the following basic actions:</span></span>  
  
-   <span data-ttu-id="627c6-104">Agregar formas para representar los procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="627c6-104">Add shapes to represent your business processes.</span></span>  
  
     <span data-ttu-id="627c6-105">El Diseñador de orquestaciones proporciona un cuadro de herramientas de formas que se puede utilizar para representar diferentes acciones u otras abstracciones.</span><span class="sxs-lookup"><span data-stu-id="627c6-105">Orchestration Designer provides you with a toolbox of shapes that can be used to represent different actions or other abstractions.</span></span> <span data-ttu-id="627c6-106">Para obtener más información, consulte [formas de orquestación](../core/orchestration-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-106">For more information, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
-   <span data-ttu-id="627c6-107">Definir esquemas para describir el formato de los mensajes</span><span class="sxs-lookup"><span data-stu-id="627c6-107">Define schemas to describe the format of your messages.</span></span>  
  
     <span data-ttu-id="627c6-108">Puede definir esquemas con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="627c6-108">You can define schemas with BizTalk Editor.</span></span> <span data-ttu-id="627c6-109">Para obtener más información, consulte [cómo crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-109">For more information, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span>  
  
-   <span data-ttu-id="627c6-110">Definir los puertos a través de los que se envían y se reciben los mensajes</span><span class="sxs-lookup"><span data-stu-id="627c6-110">Define ports through which messages are sent and received.</span></span>  
  
     <span data-ttu-id="627c6-111">Puede definir puertos para especificar cómo y dónde se envían y reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="627c6-111">You can define ports to specify how and where messages are sent and received.</span></span> <span data-ttu-id="627c6-112">Para obtener más información, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
-   <span data-ttu-id="627c6-113">Enlazar **enviar** y **recepción** formas a puertos.</span><span class="sxs-lookup"><span data-stu-id="627c6-113">Bind **Send** and **Receive** shapes to ports.</span></span>  
  
     <span data-ttu-id="627c6-114">Puede conectar su **enviar** y **recepción** formas a puertos y especificar las operaciones de puerto que utilizan.</span><span class="sxs-lookup"><span data-stu-id="627c6-114">You can connect your **Send** and **Receive** shapes to ports and specify the port operations that they use.</span></span> <span data-ttu-id="627c6-115">Para obtener más información, consulte [cómo configurar la forma envío](../core/how-to-configure-the-send-shape.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-115">For more information, see [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span> <span data-ttu-id="627c6-116">Consulte también [cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-116">Also see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
-   <span data-ttu-id="627c6-117">Asignar o transformar datos entre mensajes</span><span class="sxs-lookup"><span data-stu-id="627c6-117">Assign or transform data between messages.</span></span>  
  
     <span data-ttu-id="627c6-118">Puede usar el **construir mensaje** forma para asignar valores de mensaje o realizar transformaciones de mensajes.</span><span class="sxs-lookup"><span data-stu-id="627c6-118">You can use the **Construct Message** shape to assign message values or do message transformations.</span></span> <span data-ttu-id="627c6-119">Para obtener más información, consulte [construir mensajes](../core/constructing-messages.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-119">For more information, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
-   <span data-ttu-id="627c6-120">Identificar cualquier componente personalizado que quizás desee escribir o agregar como referencia para trabajar en su orquestación</span><span class="sxs-lookup"><span data-stu-id="627c6-120">Identify any custom components that you might want to write or add as reference to work within your orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="627c6-121">Si el **Copy Local** propiedad del ensamblado que se hace referencia está establecida en **True**, orquestación no será posible recoger los cambios realizados en el ensamblado externo después de la referencia del complemento inicial realiza Proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="627c6-121">If the **Copy Local** property of the referenced assembly is set to **True**, Orchestration will not be able to pick up any changes made to the external assembly after the initial add reference takes place in BizTalk project.</span></span>  
  
-   <span data-ttu-id="627c6-122">Definir y asignar variables de orquestación para administrar datos en la orquestación que se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="627c6-122">Define and assign orchestration variables to manage data in your running orchestration.</span></span>  
  
     <span data-ttu-id="627c6-123">Puede utilizar la carpeta Variables de la ventana Vista orquestación para declarar las variables de orquestación, y el Editor de expresiones de BizTalk para editar expresiones que asignan y utilizan las variables en varias formas.</span><span class="sxs-lookup"><span data-stu-id="627c6-123">You can use the Variables folder in the Orchestration View window to declare your orchestration variables, and BizTalk Expression Editor to edit expressions that assign and use the variables in various shapes.</span></span> <span data-ttu-id="627c6-124">Para obtener más información, consulte [tipos de datos de XLANG-s](../core/xlang-s-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-124">For more information, see [XLANG-s Data Types](../core/xlang-s-data-types.md).</span></span>  
  
-   <span data-ttu-id="627c6-125">Generar la orquestación para comprobar su integridad</span><span class="sxs-lookup"><span data-stu-id="627c6-125">Build your orchestration to test it for completeness.</span></span>  
  
     <span data-ttu-id="627c6-126">La orquestación se genera al compilar el proyecto o la solución que la contiene.</span><span class="sxs-lookup"><span data-stu-id="627c6-126">You build your orchestration when you compile the project or solution that contains it.</span></span> <span data-ttu-id="627c6-127">Para obtener más información, consulte [cómo generar orquestaciones](../core/how-to-build-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="627c6-127">For more information, see [How to Build Orchestrations](../core/how-to-build-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627c6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="627c6-128">See Also</span></span>  
 <span data-ttu-id="627c6-129">[Generar y ejecutar orquestaciones](../core/building-and-running-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="627c6-129">[Building and Running Orchestrations](../core/building-and-running-orchestrations.md) </span></span>  
 <span data-ttu-id="627c6-130">[Administrar orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="627c6-130">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="627c6-131">Crear orquestaciones mediante el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="627c6-131">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)