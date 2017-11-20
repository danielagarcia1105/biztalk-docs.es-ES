---
title: "Cómo trabajar con tipos de puertos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, port types
- port types, deleting
- port types, Web
- port types, request-response
- orchestrations, ports
- port types, modifier
- port types
- ports, port types
- port types, one-way
ms.assetid: 78ac731e-c330-4888-a9ee-10523fef8ed0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e3b4307cb9d48679ae1b90f7e02dd0288ec2957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-work-with-port-types"></a><span data-ttu-id="eb3cc-102">Cómo trabajar con tipos de puerto</span><span class="sxs-lookup"><span data-stu-id="eb3cc-102">How to Work with Port Types</span></span>
<span data-ttu-id="eb3cc-103">Un tipo de puerto consta de un patrón de comunicación, un conjunto de operaciones (solicitudes o respuestas) y los tipos de mensaje con los que pueden trabajar esas operaciones.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-103">A port type consists of a communication pattern, a set of operations (requests or responses), and the message types that those operations can work on.</span></span> <span data-ttu-id="eb3cc-104">El patrón puede ser unidireccional o de solicitud-respuesta (bidireccional), y todas las operaciones definidas en ese tipo de puerto deben utilizar el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-104">The pattern can be either one-way or request-response (two-way), and all operations defined on that port type must use the same pattern.</span></span> <span data-ttu-id="eb3cc-105">Tenga en cuenta que los tipos de puerto son independientes de la dirección: la dirección se especifica en cada puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-105">Note that port types are direction-agnostic: direction is specified on individual ports.</span></span>  
  
 <span data-ttu-id="eb3cc-106">El ámbito de un tipo de puerto se define mediante la **modificador de tipo** propiedad.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-106">The scope of a port type is defined by the **Type Modifier** property.</span></span> <span data-ttu-id="eb3cc-107">Un tipo de puerto puede ser público, privado o interno.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-107">A port type can be public, private, or internal.</span></span> <span data-ttu-id="eb3cc-108">Si es público, estará visible para cualquiera que interactúe con la orquestación.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-108">If it is public, it is visible to anyone interacting with the orchestration.</span></span> <span data-ttu-id="eb3cc-109">Si es privado, estará visible para otras orquestaciones dentro del mismo proyecto y el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-109">If it is private, it is visible to other orchestrations within the same project and namespace.</span></span> <span data-ttu-id="eb3cc-110">Si es interno, el tipo de puerto estará visible solo dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-110">If it is internal, the port type is visible only within the project.</span></span> <span data-ttu-id="eb3cc-111">Puesto que una definición de tipo de puerto incluye tipos de mensaje, el ámbito del tipo de mensaje deberá incluir el de cualquier tipo de puerto que lo utilice.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-111">Since a port type definition includes message types, the scope of the message type must encompass that of any port type that uses it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb3cc-112">Un tipo de puerto se puede aplicar a cualquier número de puertos.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-112">A port type can be applied to any number of ports.</span></span> <span data-ttu-id="eb3cc-113">Un puerto puede considerarse como una instancia de un tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-113">You can think of a port as an instance of a port type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb3cc-114">Un tipo de puerto no tiene una dirección de comunicación de forma inherente; la dirección se establece en cada puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-114">A port type does not inherently have a communication direction; you set direction on individual ports.</span></span>  
  
### <a name="to-add-a-request-response-port-type"></a><span data-ttu-id="eb3cc-115">Para agregar un tipo de puerto de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="eb3cc-115">To add a request-response port type</span></span>  
  
1.  <span data-ttu-id="eb3cc-116">En la ventana Vista orquestación, haga clic en **tipos de puerto** y, a continuación, haga clic en **tipo de puerto de solicitud-respuesta nuevo**.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-116">In the Orchestration View window, right-click **Port Types** and then click **New Request-response Port Type**.</span></span>  
  
     <span data-ttu-id="eb3cc-117">El **tipos de puerto** expande el nodo, si se contrae, y se agrega un nuevo tipo de puerto de solicitud-respuesta con una operación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-117">The **Port Types** node expands, if collapsed, and a new request-response port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="eb3cc-118">Especifique un nombre para el tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-118">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="eb3cc-119">Defina una o más operaciones de puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-119">Define one or more port operations.</span></span>  
  
     <span data-ttu-id="eb3cc-120">Puede asignar un nombre a las operaciones de puerto, pero cuando las seleccione desde otro proyecto, aparecerán únicamente como "Solicitud" y "Respuesta"</span><span class="sxs-lookup"><span data-stu-id="eb3cc-120">You can name your port operations, but when you are selecting them from another project, you will see them only as "Request" and "Response."</span></span> <span data-ttu-id="eb3cc-121">Si selecciona una operación de puerto desde otro proyecto, compruebe que tiene el tipo de mensaje correcto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-121">If you select a port operation from another project, verify that it has the correct message type.</span></span>  
  
### <a name="to-add-a-one-way-port-type"></a><span data-ttu-id="eb3cc-122">Para agregar un tipo de puerto unidireccional</span><span class="sxs-lookup"><span data-stu-id="eb3cc-122">To add a one-way port type</span></span>  
  
1.  <span data-ttu-id="eb3cc-123">En la ventana Vista orquestación, haga clic en **tipos de puerto** y, a continuación, haga clic en **nuevo tipo de puerto unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-123">In the Orchestration View window, right-click **Port Types** and then click **New One-way Port Type**.</span></span>  
  
     <span data-ttu-id="eb3cc-124">El **tipos de puerto** expande el nodo, si se contrae y se agrega un nuevo tipo de puerto unidireccional con una operación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-124">The **Port Types** node expands, if collapsed, and a new one-way port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="eb3cc-125">Especifique un nombre para el tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-125">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="eb3cc-126">Defina una o más operaciones de puerto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-126">Define one or more port operations.</span></span>  
  
### <a name="to-add-a-web-port-type"></a><span data-ttu-id="eb3cc-127">Para agregar un tipo de puerto Web</span><span class="sxs-lookup"><span data-stu-id="eb3cc-127">To add a Web port type</span></span>  
  
-   <span data-ttu-id="eb3cc-128">Agregue una referencia de proyecto a un ensamblado que contenga una clase de proxy para un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-128">Add a project reference to an assembly containing a proxy class for a Web service.</span></span> <span data-ttu-id="eb3cc-129">Para obtener más información, consulte [crear puertos Web](../core/creating-web-ports.md).</span><span class="sxs-lookup"><span data-stu-id="eb3cc-129">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
### <a name="to-remove-a-port-type"></a><span data-ttu-id="eb3cc-130">Para quitar un tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="eb3cc-130">To remove a port type</span></span>  
  
-   <span data-ttu-id="eb3cc-131">En la ventana Vista orquestación, haga clic en eliminar y, a continuación, haga clic en el tipo de puerto **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-131">In the Orchestration View window, right-click the port type to delete, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb3cc-132">Si el tipo de puerto está en uso, su eliminación afectará a la configuración de los puertos que estén configurados para utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-132">If the port type is in use, deleting it will impact the configuration of any ports that are configured to use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb3cc-133">Los elementos que aparecen como de solo de lectura se definen en otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-133">Items that appear as read-only are defined in another orchestration.</span></span>  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a><span data-ttu-id="eb3cc-134">Para establecer el modificador de tipo para un tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="eb3cc-134">To set the type modifier for a port type</span></span>  
  
-   <span data-ttu-id="eb3cc-135">En la ventana Propiedades, establezca la siguiente propiedad:</span><span class="sxs-lookup"><span data-stu-id="eb3cc-135">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="eb3cc-136">Propiedad</span><span class="sxs-lookup"><span data-stu-id="eb3cc-136">Property</span></span>|<span data-ttu-id="eb3cc-137">Description</span><span class="sxs-lookup"><span data-stu-id="eb3cc-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="eb3cc-138">Modificador de tipo</span><span class="sxs-lookup"><span data-stu-id="eb3cc-138">Type Modifier</span></span>|<span data-ttu-id="eb3cc-139">Determina el ámbito del tipo de puerto:</span><span class="sxs-lookup"><span data-stu-id="eb3cc-139">Determines the scope of the port type:</span></span><br /><br /> <span data-ttu-id="eb3cc-140">Privado: acceso a este tipo de puerto está limitado al módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-140">Private—Access to this port type is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="eb3cc-141">Público: acceso a este tipo de puerto no está limitado.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-141">Public—Access to this port type is not limited.</span></span><br /><br /> <span data-ttu-id="eb3cc-142">Interno: el acceso a este tipo de puerto está limitado a los módulos dentro del mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="eb3cc-142">Internal—Access to this port type is limited to modules within the same project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb3cc-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb3cc-143">See Also</span></span>  
 <span data-ttu-id="eb3cc-144">[Patrón de comunicación](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="eb3cc-144">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="eb3cc-145">[Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="eb3cc-145">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="eb3cc-146">Uso de puertos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="eb3cc-146">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)