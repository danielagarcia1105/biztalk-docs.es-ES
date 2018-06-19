---
title: Cómo agregar Functoids básicos a una asignación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a81fb73-cccf-4f74-af92-39e4af13e255
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23a6748a5ce128ef13ce012412e36570e4e01eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248988"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a><span data-ttu-id="4eb13-102">Cómo agregar functoids básicos a una asignación</span><span class="sxs-lookup"><span data-stu-id="4eb13-102">How to Add Basic Functoids to a Map</span></span>
<span data-ttu-id="4eb13-103">Muchos functoids son muy sencillos de utilizar.</span><span class="sxs-lookup"><span data-stu-id="4eb13-103">Many functoids are very simple to use.</span></span> <span data-ttu-id="4eb13-104">Estos se denominan aquí functoids básicos para distinguirlos de los functoids de la **avanzadas** categoría.</span><span class="sxs-lookup"><span data-stu-id="4eb13-104">These are referred to here as basic functoids to distinguish them from the functoids in the **Advanced** category.</span></span> <span data-ttu-id="4eb13-105">Los functoids básicos comprenden las siguientes categorías: de conversión, acumulativos, de bases de datos, de fecha y hora, lógicos, matemáticos, científicos y de cadena.</span><span class="sxs-lookup"><span data-stu-id="4eb13-105">Basic functoids comprise the remaining categories of functoids such as Conversion, Cumulative, Database, Date and Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
 <span data-ttu-id="4eb13-106">Por regla general, los functoids básicos tienen tipos simples (por ejemplo, números y cadenas) como vínculos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="4eb13-106">Basic functoids, in general, have simple types, such as numbers and strings, as their input and output links.</span></span>  
  
 <span data-ttu-id="4eb13-107">La utilización de un functoid básico supone agregarlo una página de cuadrícula, crear vínculos de entrada al functoid, que provienen de la izquierda, y crear un vínculo de salida del functoid, que sale hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="4eb13-107">Using a basic functoid involves adding it to a grid page, creating input links to the functoid, coming from the left, and creating output link from the functoid, leaving to the right.</span></span> <span data-ttu-id="4eb13-108">En este tema se proporcionan instrucciones detalladas para estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="4eb13-108">This topic provides step-by-step instructions for these operations.</span></span>  
  
## <a name="add-a-basic-functoid-to-a-map"></a><span data-ttu-id="4eb13-109">Agregar un functoid básico a un mapa</span><span class="sxs-lookup"><span data-stu-id="4eb13-109">Add a basic functoid to a map</span></span>  
  
1.  <span data-ttu-id="4eb13-110">Con el cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] activo, haga clic en la pestaña apropiada para seleccionar la categoría del functoid que desea ver.</span><span class="sxs-lookup"><span data-stu-id="4eb13-110">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the appropriate tab to select the category of the functoid you want to use.</span></span>  
  
     <span data-ttu-id="4eb13-111">Aparece la lista de functoids disponibles de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4eb13-111">The list of available functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="4eb13-112">Arrastre el functoid que desea utilizar desde el cuadro de herramientas hasta la ubicación apropiada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4eb13-112">Drag the functoid you want to use from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-113">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="4eb13-113">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="4eb13-114">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="4eb13-114">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-115">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="4eb13-115">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="4eb13-116">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="4eb13-116">Functoids are executed from left to right.</span></span> <span data-ttu-id="4eb13-117">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="4eb13-117">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
## <a name="create-input-links-to-a-basic-functoid"></a><span data-ttu-id="4eb13-118">Crear vínculos de entrada a un functoid básico</span><span class="sxs-lookup"><span data-stu-id="4eb13-118">Create input links to a basic functoid</span></span>  
  
1.  <span data-ttu-id="4eb13-119">Arrastre un nodo Registro o Campo desde el esquema de origen hasta el functoid básico en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="4eb13-119">Drag a record or field node from the source schema to the basic functoid in the displayed grid page.</span></span>  
  
     <span data-ttu-id="4eb13-120">**- O bien-**</span><span class="sxs-lookup"><span data-stu-id="4eb13-120">**- Or -**</span></span>  
  
     <span data-ttu-id="4eb13-121">En la página de cuadrícula mostrada, arrastre otro functoid, que esté ubicado más a la izquierda, hasta el functoid básico en el que desea crear un vínculo de entrada.</span><span class="sxs-lookup"><span data-stu-id="4eb13-121">In the displayed grid page, drag another functoid, which is located farther to the left, to the basic functoid to which you want to create an input link.</span></span>  
  
     <span data-ttu-id="4eb13-122">**- O bien-**</span><span class="sxs-lookup"><span data-stu-id="4eb13-122">**- Or -**</span></span>  
  
     <span data-ttu-id="4eb13-123">Arrastre el functoid básico de la página de cuadrícula mostrada hasta un nodo Registro o Campo del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="4eb13-123">Drag the basic functoid in the displayed grid page to a record or field node in the source schema.</span></span>  
  
     <span data-ttu-id="4eb13-124">**- O bien-**</span><span class="sxs-lookup"><span data-stu-id="4eb13-124">**- Or -**</span></span>  
  
     <span data-ttu-id="4eb13-125">En la página de cuadrícula mostrada, arrastre el functoid básico en el que desea crear un vínculo de entrada hasta otro functoid, que esté ubicado más a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="4eb13-125">In the displayed grid page, drag the basic functoid to which you want to create an input link to another functoid that is located farther to the left.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-126">Mientras se arrastra, el extremo que se mueve del vínculo, en lugar del extremo anclado el vínculo, se convierte en un icono de cruz para permitir más precisa del segundo extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="4eb13-126">While dragging, the moving endpoint of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="4eb13-127">Si desplaza el extremo que se mueve del vínculo sobre un objeto que no es un segundo extremo apropiado para ese vínculo, como podría ocurrir si hay una falta de coincidencia en el tipo de datos, el icono de cruz se transforma en un icono que muestra un círculo con una barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="4eb13-127">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
2.  <span data-ttu-id="4eb13-128">Repita el paso 1 tantas veces como sea necesario para establecer el conjunto completo de vínculos de entrada (auque quizás no todo el conjunto de parámetros de entrada) para el functoid básico.</span><span class="sxs-lookup"><span data-stu-id="4eb13-128">Repeat step 1 as necessary to establish the complete set of input links (though perhaps not the entire set of input parameters) to the basic functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-129">Existen algunos functoids que no requieren vínculos de entrada.</span><span class="sxs-lookup"><span data-stu-id="4eb13-129">There are a few functoids that do not require any input links.</span></span> <span data-ttu-id="4eb13-130">Por ejemplo, el **fecha**, **tiempo**, y **fecha y hora** functoids en el **fecha y hora** categoría de functoid proporciona la fecha actual, tiempo, o fecha y hora, respectivamente, en el que se está procesando un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="4eb13-130">For example, the **Date**, **Time**, and **Date and Time** functoids in the **Date and Time** functoid category provide the current date, time, or date and time, respectively, at which an instance message is being processed.</span></span> <span data-ttu-id="4eb13-131">Por lo tanto, no requieren parámetros de entrada del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="4eb13-131">Thus, they do not require any input parameters from the source schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-132">El orden de los parámetros de entrada para muchos functoids es relevante, como se indica en el tema de referencia de functoids correspondiente (consulte **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]).</span><span class="sxs-lookup"><span data-stu-id="4eb13-132">The order of input parameters to many functoids is significant, as indicated in the corresponding functoid reference topic (see **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]).</span></span> <span data-ttu-id="4eb13-133">El orden en que se crean los vínculos establece el orden de los parámetros de entrada al functoid.</span><span class="sxs-lookup"><span data-stu-id="4eb13-133">The order in which you create links sets the order of input parameters to the functoid.</span></span> <span data-ttu-id="4eb13-134">Para obtener más información sobre propiedades de functoid y especificar el orden de los parámetros de entrada de functoid, consulte [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4eb13-134">For more information about functoid properties and specifying the order of functoid input parameters, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="4eb13-135">Para obtener información sobre cómo configurar los parámetros de entrada de un functoid, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4eb13-135">For information about how to configure the input parameters of a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-136">Asegúrese de que los functoids o el nodo de esquema de origen que desea vincular estén visibles en la página de cuadrícula mostrada o en la ventana de esquema de origen antes de comenzar a vincular.</span><span class="sxs-lookup"><span data-stu-id="4eb13-136">Ensure the functoids or source schema node you want to link are visible in the displayed grid page or source schema window before you begin linking.</span></span>  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a><span data-ttu-id="4eb13-137">Crear el vínculo de salida de un functoid básico</span><span class="sxs-lookup"><span data-stu-id="4eb13-137">Create the output link from a basic functoid</span></span>  
  
1.  <span data-ttu-id="4eb13-138">Arrastre un nodo Registro o Campo desde el esquema de destino hasta el functoid básico en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="4eb13-138">Drag a record or field node from the destination schema to the basic functoid in the displayed grid page.</span></span>  
  
     <span data-ttu-id="4eb13-139">**- O bien-**</span><span class="sxs-lookup"><span data-stu-id="4eb13-139">**- Or -**</span></span>  
  
     <span data-ttu-id="4eb13-140">En la página de cuadrícula mostrada, arrastre otro functoid, que esté ubicado más a la derecha, hasta el functoid básico en el que desea crear un vínculo de salida.</span><span class="sxs-lookup"><span data-stu-id="4eb13-140">In the displayed grid page, drag another functoid, which is located farther to the right, to the basic functoid to which you want to create the output link.</span></span>  
  
     <span data-ttu-id="4eb13-141">**- O bien-**</span><span class="sxs-lookup"><span data-stu-id="4eb13-141">**- Or -**</span></span>  
  
     <span data-ttu-id="4eb13-142">Arrastre el functoid básico que está en la página de cuadrícula mostrada hasta un nodo Registro o Campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="4eb13-142">Drag the basic functoid in the displayed grid page to a record or field node in the destination schema.</span></span>  
  
     <span data-ttu-id="4eb13-143">**- O bien-**</span><span class="sxs-lookup"><span data-stu-id="4eb13-143">**- Or -**</span></span>  
  
2.  <span data-ttu-id="4eb13-144">En la página de cuadrícula mostrada, arrastre el functoid básico en el que desea crear el vínculo de salida hasta otro functoid que esté ubicado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="4eb13-144">In the displayed grid page, drag the basic functoid to which you want to create the output link to another functoid that is located farther to the right.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-145">Asegúrese de que los functoids y el nodo de esquema de origen que desea vincular ya estén visibles en la página de cuadrícula mostrada y en la ventana de esquema de origen respectivamente antes de comenzar a vincular.</span><span class="sxs-lookup"><span data-stu-id="4eb13-145">Ensure the functoids and source schema node that you want to link are already visible in the displayed grid page and source schema window, respectively, before you begin the linking operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-146">La vinculación de functoids siempre intenta evitar vinculaciones inapropiadas, como vínculos en los que los tipos de datos de origen y de destino no coinciden.</span><span class="sxs-lookup"><span data-stu-id="4eb13-146">Functoid linking always attempts to disallow inappropriate linking, such as links where source and target data types do not match.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4eb13-147">Mientras se arrastra, el extremo que se mueve del vínculo (a diferencia del extremo anclado) se transforma en un icono de cruz para permitir alcanzar el objetivo del segundo extremo de forma más precisa.</span><span class="sxs-lookup"><span data-stu-id="4eb13-147">While dragging, the moving end point of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="4eb13-148">Si desplaza el extremo que se mueve del vínculo sobre un objeto que no es un segundo extremo apropiado para ese vínculo, como podría ocurrir si hay una falta de coincidencia en el tipo de datos, el icono de cruz se transforma en un icono que muestra un círculo con una barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="4eb13-148">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb13-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eb13-149">See Also</span></span>  
<span data-ttu-id="4eb13-150">**Referencia de functoid**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4eb13-150">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>