---
title: "Cómo usar los tipos de mensaje de varias partes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multi-part message types, parts
- multi-part message types, creating
- multi-part message types, type modifiers
- messages
- multi-part message types, deleting
- orchestrations, messages
- deleting, multi-part messages
- multi-part message types, about multi-part message types
- orchestrations, type modifier
- messages, multi-parts
- creating, multi-part messages
- messages, about messages
ms.assetid: 009a39bd-cfc4-42d9-918c-88ac24bfc370
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87f210c4b0d2969edc9ddfa27b1d8494310eb6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-multi-part-message-types"></a><span data-ttu-id="a1679-102">Cómo usar los tipos de mensaje de varias partes</span><span class="sxs-lookup"><span data-stu-id="a1679-102">How to Use Multi-part Message Types</span></span>
<span data-ttu-id="a1679-103">Cada mensaje tiene un tipo de mensaje de varias partes, una descripción de la estructura del mensaje que se compone de cero o más partes de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1679-103">Each message has a multi-part message type, a description of the message structure that consists of zero or more message parts.</span></span> <span data-ttu-id="a1679-104">Las partes se definen en el lenguaje de definición de esquemas XML (XSD) mediante esquemas o clases .NET.</span><span class="sxs-lookup"><span data-stu-id="a1679-104">The parts are defined by XML Schema Definition (XSD) language schemas or .NET classes.</span></span> <span data-ttu-id="a1679-105">Puede definir sus propios tipos de mensaje de varias partes o usar los esquemas y las clases .NET existentes.</span><span class="sxs-lookup"><span data-stu-id="a1679-105">You can define your own multi-part message types, or you can use existing .NET classes and schemas.</span></span>  
  
 <span data-ttu-id="a1679-106">Puede obtener acceso a las partes de mensaje o asignarlas directamente dentro de la orquestación, o bien usar elementos individuales de partes de mensaje que se exponen como campos distintivos o campos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a1679-106">You can access or assign message parts directly within your orchestration, or you can use individual elements of message parts that are exposed as distinguished fields or property fields.</span></span> <span data-ttu-id="a1679-107">Para obtener más información, consulte [usar campos distintivos y las propiedades de mensaje](../core/using-distinguished-fields-and-property-fields.md).</span><span class="sxs-lookup"><span data-stu-id="a1679-107">For more information, see [Using Distinguished Fields and Message Properties](../core/using-distinguished-fields-and-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1679-108">Un tipo de mensaje de varias partes no tiene que contener necesariamente varias partes.</span><span class="sxs-lookup"><span data-stu-id="a1679-108">A multi-part message type does not necessarily contain multiple parts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1679-109">Una parte de mensaje puede definirse mediante el tipo .NET **XmlDocument**, que puede utilizarse para contener un documento XML arbitrario, por cualquier tipo .NET que es serializable con XML, o por cualquier .NET escriba auxiliar serialización personalizada.</span><span class="sxs-lookup"><span data-stu-id="a1679-109">A message part can be defined by the .NET type **XmlDocument**, which can be used to contain an arbitrary XML document, by any .NET type that is XML-serializable, or by any .NET type supporting custom serialization.</span></span>  
  
## <a name="add-a-multi-part-message-type"></a><span data-ttu-id="a1679-110">Agregar un tipo de mensaje de varias partes</span><span class="sxs-lookup"><span data-stu-id="a1679-110">Add a multi-part message type</span></span>  
  
1.  <span data-ttu-id="a1679-111">En el **Vista orquestación** ventana, expanda la **tipos** nodo.</span><span class="sxs-lookup"><span data-stu-id="a1679-111">In the **Orchestration View** window, expand the **Types** node.</span></span>  
  
2.  <span data-ttu-id="a1679-112">Haga clic en **tipos de mensaje de varias partes** y, a continuación, haga clic en **nuevo tipo de mensaje de varias partes**.</span><span class="sxs-lookup"><span data-stu-id="a1679-112">Right-click **Multi-part Message Types** and then click **New Multi-part Message Type**.</span></span>  
  
     <span data-ttu-id="a1679-113">El **tipos de mensaje de varias partes** carpeta se expande, si se contrae, y se agrega un nuevo tipo de mensaje de varias partes con parte del mensaje de un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a1679-113">The **Multi-part Message Types** folder expands, if collapsed, and a new multi-part message type is added with one default message part.</span></span>  
  
3.  <span data-ttu-id="a1679-114">Asigne un nombre al tipo de mensaje de varias partes y a la parte de mensaje proporcionada.</span><span class="sxs-lookup"><span data-stu-id="a1679-114">Name the multi-part message type and the provided message part.</span></span>  
  
     <span data-ttu-id="a1679-115">Si el tipo de mensaje de varias partes requiere más de una parte de mensaje, puede agregar partes adicionales asignando un nombre a la \<nuevo > parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1679-115">If your multi-part message type requires more than one message part, you can add additional parts by assigning a name to the \<New> message part.</span></span>  
  
4.  <span data-ttu-id="a1679-116">Asocie cada parte de mensaje a un tipo; por ejemplo, esquema o clase .NET.</span><span class="sxs-lookup"><span data-stu-id="a1679-116">Associate each message part with a type, such as a .NET class or schema.</span></span>  
  
## <a name="remove-a-multi-part-message-type"></a><span data-ttu-id="a1679-117">Quitar un tipo de mensaje de varias partes</span><span class="sxs-lookup"><span data-stu-id="a1679-117">Remove a multi-part message type</span></span>  
  
-   <span data-ttu-id="a1679-118">En el **Vista orquestación** ventana, menú contextual que desea quitar y, a continuación, haga clic en el tipo de mensaje de varias partes **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a1679-118">In the **Orchestration View** window, right-click the multi-part message type you want to remove and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1679-119">Al quitar un tipo de mensaje de varias partes de la orquestación también se quitará la información de tipo de los mensajes que lo utilicen.</span><span class="sxs-lookup"><span data-stu-id="a1679-119">Removing a multi-part message type from your orchestration will also remove the type information from messages that use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1679-120">Los elementos que aparecen como de solo de lectura se definen en otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="a1679-120">Items that appear as read-only are defined in another orchestration.</span></span>  
  
## <a name="remove-a-part-from-a-multi-part-message-type"></a><span data-ttu-id="a1679-121">Quitar un elemento de un tipo de mensaje de varias partes</span><span class="sxs-lookup"><span data-stu-id="a1679-121">Remove a part from a multi-part message type</span></span>  
  
-   <span data-ttu-id="a1679-122">En el **Vista orquestación** ventana, haga clic en el elemento que desea quitar y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a1679-122">In the **Orchestration View** window, right-click the part you want to remove and click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1679-123">No se puede eliminar parte del mensaje de un tipo de mensaje si la **parte del cuerpo del mensaje** propiedad está establecida en true.</span><span class="sxs-lookup"><span data-stu-id="a1679-123">You cannot delete a message type's message part if the **Message Body Part** property is set to true.</span></span> <span data-ttu-id="a1679-124">Debe configurar primero la **parte del cuerpo del mensaje** propiedad en True para otra cosa de partes de ese tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1679-124">You must first set the **Message Body Part** property to True for another of the message type's parts.</span></span>  
  
## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a><span data-ttu-id="a1679-125">Establecer el modificador de tipo para un tipo de mensaje de varias partes</span><span class="sxs-lookup"><span data-stu-id="a1679-125">Set the type modifier for a multi-part message type</span></span>  
  
-   <span data-ttu-id="a1679-126">En el **propiedades** ventana, establezca la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1679-126">In the **Properties** window, set the following property:</span></span>  
  
    |<span data-ttu-id="a1679-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a1679-127">Property</span></span>|<span data-ttu-id="a1679-128">Description</span><span class="sxs-lookup"><span data-stu-id="a1679-128">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="a1679-129">**Modificador de tipo**</span><span class="sxs-lookup"><span data-stu-id="a1679-129">**Type Modifier**</span></span>|<span data-ttu-id="a1679-130">Determina el ámbito del tipo de mensaje de varias partes:</span><span class="sxs-lookup"><span data-stu-id="a1679-130">Determines the scope of the multi-part message type:</span></span><br /><br /> <span data-ttu-id="a1679-131">-   **Privado:**acceso a este tipo de mensaje de varias partes está limitado al módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="a1679-131">-   **Private—**Access to this multi-part message type is limited to the containing module.</span></span><br /><span data-ttu-id="a1679-132">-   **Público:**no se limita el acceso a este tipo de mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="a1679-132">-   **Public—**Access to this multi-part message type is not limited.</span></span><br /><span data-ttu-id="a1679-133">-   **Interno:**acceso a este tipo de mensaje de varias partes está limitado a los módulos dentro del mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="a1679-133">-   **Internal—**Access to this multi-part message type is limited to modules within the same project.</span></span>|  
  
## <a name="add-parts-to-an-existing-multi-part-message"></a><span data-ttu-id="a1679-134">Agregar elementos a un mensaje de varias partes existente</span><span class="sxs-lookup"><span data-stu-id="a1679-134">Add parts to an existing multi-part message</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a1679-135"> permite agregar partes a un mensaje de varias partes XLANG y también hacer referencia a una parte de mensaje mediante un índice mayor que el número de partes declarado originalmente si la parte existe.</span><span class="sxs-lookup"><span data-stu-id="a1679-135"> provides the ability to add parts to a multi part XLANG message and also to refer to a message part by an index greater than the originally declared number of parts if the part exists.</span></span> <span data-ttu-id="a1679-136">Esta funcionalidad puede ser útil para enviar o recibir mensajes SMTP con un número variable de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a1679-136">This functionality may be useful for sending or receiving SMTP messages with a variable number of attachments.</span></span> <span data-ttu-id="a1679-137">Esta funcionalidad se implementa del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1679-137">This functionality is implemented as follows:</span></span>  
  
-   <span data-ttu-id="a1679-138">Desde el proyecto, agregue una referencia a **Microsoft.XLANGs.BaseTypes**.</span><span class="sxs-lookup"><span data-stu-id="a1679-138">From your project, add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="a1679-139">Cree una variable (por ejemplo *xlangPart*) de tipo **Microsoft.XLANGs.BaseTypes.XLANGMessage**.</span><span class="sxs-lookup"><span data-stu-id="a1679-139">Create a variable (for example *xlangPart*) of type **Microsoft.XLANGs.BaseTypes.XLANGMessage**.</span></span>  
  
-   <span data-ttu-id="a1679-140">Llame a *xlangPart***. AddPart(...)**  usando los argumentos apropiados de una forma expresión.</span><span class="sxs-lookup"><span data-stu-id="a1679-140">Call *xlangPart***.AddPart(…)** using the appropriate arguments from an Expression shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1679-141">Las partes agregadas son del tipo **XmlDocument** por lo que no puede agregar una parte de mensaje formateada personalizada usando el **AddPart()** método.</span><span class="sxs-lookup"><span data-stu-id="a1679-141">The added parts are of type **XmlDocument** so you cannot add a custom formatted message part using the **AddPart()** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1679-142">Si se recibe un mensaje de varias partes que contiene mayor que el número de partes declarados, las lecturas de motor de orquestación están cuántos elementos hay en el mensaje, a continuación, crea los tipos de partes apropiados para los elementos que coinciden con el número de partes del mensaje declarado tipo y, a continuación, las construcciones **XmlDocument** partes de las partes restantes.</span><span class="sxs-lookup"><span data-stu-id="a1679-142">If a multi part message that contains greater than the number of declared parts is received, the orchestration engine reads how many parts there are in the message, then constructs the proper part types for the parts that match the number of parts in the declared message type and then constructs **XmlDocument** parts for the remaining parts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1679-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1679-143">See Also</span></span>  
 <span data-ttu-id="a1679-144">**IBaseMessage.AddPart (método) (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a1679-144">**IBaseMessage.AddPart Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
 <span data-ttu-id="a1679-145">[Recursos XSD en Internet](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="a1679-145">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 <span data-ttu-id="a1679-146">[Usar campos distintivos y campos de propiedades](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="a1679-146">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="a1679-147">Usar mensajes en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="a1679-147">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)