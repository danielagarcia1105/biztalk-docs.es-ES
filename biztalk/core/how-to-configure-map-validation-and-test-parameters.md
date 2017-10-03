---
title: "Cómo configurar la validación de asignaciones y parámetros de prueba | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1768918c-e94f-476f-b288-9e030c691177
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f691a58ece178ee00ce983e400e5420ef54fafdf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a><span data-ttu-id="5ff4e-102">Cómo configurar la validación de asignaciones y parámetros de prueba</span><span class="sxs-lookup"><span data-stu-id="5ff4e-102">How to Configure Map Validation and Test Parameters</span></span>
<span data-ttu-id="5ff4e-103">Antes de validar y comprobar una asignación, debe establecer parámetros de prueba y validación de la asignación el **propiedades** ventana del mapa.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-103">Before validating and testing a map, you need to set the map validation and test parameters in the **Properties** window of the map.</span></span>  
  
## <a name="configure-the-map-validation-and-test-parameters"></a><span data-ttu-id="5ff4e-104">Configurar los parámetros de comprobación y validación de mapa</span><span class="sxs-lookup"><span data-stu-id="5ff4e-104">Configure the map validation and test parameters</span></span>  
  
1.  <span data-ttu-id="5ff4e-105">En el Explorador de soluciones, haga clic en la asignación cuya página de propiedades que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-105">In Solution Explorer, right-click the map whose property pages you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5ff4e-106">En la ventana Propiedades, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-106">In the Properties window, do the following.</span></span>  
  
    |<span data-ttu-id="5ff4e-107">Use</span><span class="sxs-lookup"><span data-stu-id="5ff4e-107">Use this</span></span>|<span data-ttu-id="5ff4e-108">Para</span><span class="sxs-lookup"><span data-stu-id="5ff4e-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5ff4e-109">**Validar entrada de comprobar asignación**</span><span class="sxs-lookup"><span data-stu-id="5ff4e-109">**Validate TestMap Input**</span></span>|<span data-ttu-id="5ff4e-110">Configurar si quiere o no que se valide el mensaje de instancia con respecto al esquema de origen antes de comprobar la asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-110">Configure whether you want to have the instance message validated against the source schema before you test the map.</span></span>|  
    |<span data-ttu-id="5ff4e-111">**Validar salida de comprobar asignación**</span><span class="sxs-lookup"><span data-stu-id="5ff4e-111">**Validate TestMap Output**</span></span>|<span data-ttu-id="5ff4e-112">Configurar si quiere o no que se valide el mensaje de instancia con respecto al esquema de destino después de comprobar la asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-112">Configure whether you want to have the instance message validated against the destination schema after you test the map.</span></span>|  
    |<span data-ttu-id="5ff4e-113">**Instancia de entrada de comprobar asignación**</span><span class="sxs-lookup"><span data-stu-id="5ff4e-113">**TestMap Input Instance**</span></span>|<span data-ttu-id="5ff4e-114">Configurar la ubicación de los datos del mensaje de instancia que se va a utilizar cuando compruebe la asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-114">Configure the location of the instance message data to use when you test the map.</span></span><br /><br /> <span data-ttu-id="5ff4e-115">Si configura esta propiedad, también debe configurar la **entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-115">If you configure this property, you must also configure the **TestMap Input** property.</span></span>|  
    |<span data-ttu-id="5ff4e-116">**Instancia de salida de comprobar asignación**</span><span class="sxs-lookup"><span data-stu-id="5ff4e-116">**TestMap Output Instance**</span></span>|<span data-ttu-id="5ff4e-117">Configure la ubicación del archivo donde desea que se almacene la salida de la operación de comprobar asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-117">Configure the location of the file where you want the output of the test map operation to be stored.</span></span><br /><br /> <span data-ttu-id="5ff4e-118">Si configura esta propiedad, también debe configurar la **salida de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-118">If you configure this property, you must also configure the **TestMap Output** property.</span></span>|  
    |<span data-ttu-id="5ff4e-119">**Entrada de comprobar asignación**</span><span class="sxs-lookup"><span data-stu-id="5ff4e-119">**TestMap Input**</span></span>|<span data-ttu-id="5ff4e-120">Configurar el formato de datos de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-120">Configure the input instance data format.</span></span>|  
    |<span data-ttu-id="5ff4e-121">**Salida de comprobar asignación**</span><span class="sxs-lookup"><span data-stu-id="5ff4e-121">**TestMap Output**</span></span>|<span data-ttu-id="5ff4e-122">Configurar el tipo de datos de salida que se va a utilizar cuando compruebe la asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-122">Configure the output data type to use when you test the map.</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5ff4e-123">Si desea comprobar la asignación, debe configurar en primer lugar las propiedades de la asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-123">If you want to test your map, you must configure the map properties first.</span></span>  

<span data-ttu-id="5ff4e-124">Una vez que haya desarrollado la asignación, uno de los siguientes pasos es validarla.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-124">After you have developed your map, one of the next steps is to validate it.</span></span> <span data-ttu-id="5ff4e-125">En este tema se proporcionan instrucciones detalladas para validar asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-125">This topic provides step-by-step instructions for validating maps.</span></span>  
  
## <a name="validate-a-biztalk-map"></a><span data-ttu-id="5ff4e-126">Validar una asignación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5ff4e-126">Validate a BizTalk map</span></span>  
  
1.  <span data-ttu-id="5ff4e-127">En el Explorador de soluciones, abra la asignación que desee validar.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-127">In Solution Explorer, open the map that you want to validate.</span></span>  
  
2.  <span data-ttu-id="5ff4e-128">En el Explorador de soluciones, haga clic en el mapa y, a continuación, seleccione **validar asignación**.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-128">In Solution Explorer, right-click the map, and then select **Validate Map**.</span></span>  
  
3.  <span data-ttu-id="5ff4e-129">En el **salida** ventana, comprobar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-129">In the **Output** window, verify the results.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ff4e-130">Si en la salida utiliza constantes o datos personalizados, debe comprobar que los tipos de datos de los datos de prueba de origen y los valores constantes de destino sean válidos.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-130">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="5ff4e-131">Cuando se valida una asignación, el Asignador de BizTalk no comprueba si los datos de instancia infringen los tipos de datos definidos en los esquemas.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-131">When you validate a map, BizTalk Mapper does not check if the instance data violates any data types defined in the schemas.</span></span> <span data-ttu-id="5ff4e-132">Esto se hace cuando prueba la asignación o valida los datos de instancia con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-132">This is done when you test the map or validate the instance data with BizTalk Editor.</span></span> 

## <a name="test-a-biztalk-map"></a><span data-ttu-id="5ff4e-133">Probar una asignación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5ff4e-133">Test a BizTalk map</span></span>

<span data-ttu-id="5ff4e-134">Una vez que haya desarrollado la asignación, uno de los siguientes pasos es comprobarla.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-134">After you have developed your map, one of the next steps is to test it.</span></span> <span data-ttu-id="5ff4e-135">Este tema proporciona instrucciones paso a paso para probar asignaciones, incluido los pasos para ver el XSLT generado por el compilador de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-135">This topic provides step-by-step instructions for testing maps including steps to view the XSLT generated by the map compiler.</span></span>  
  
1.  <span data-ttu-id="5ff4e-136">En el Explorador de soluciones, haga clic en la asignación que desea probar y, a continuación, seleccione **comprobar asignación**.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-136">In Solution Explorer, right-click the map you want to test, and then select **Test Map**.</span></span>  
  
2.  <span data-ttu-id="5ff4e-137">Comprobar los resultados en la **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-137">Verify the results in the **Output** window.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5ff4e-138">Es recomendable que configure las propiedades de instancia de entrada y de salida en la ventana Propiedades antes de comprobar una asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-138">It is recommended that you configure the input and output instance properties in the Properties window before you test a map.</span></span>  
  
## <a name="review-the-xslt"></a><span data-ttu-id="5ff4e-139">Revisar el XSLT</span><span class="sxs-lookup"><span data-stu-id="5ff4e-139">Review the XSLT</span></span>  
 <span data-ttu-id="5ff4e-140">A menudo es útil inspeccionar el XSLT generado por el compilador de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-140">It is often useful to inspect the XSLT generated by the map compiler.</span></span> <span data-ttu-id="5ff4e-141">Algunas de las ventajas de inspeccionar un XSLT son:</span><span class="sxs-lookup"><span data-stu-id="5ff4e-141">Some of the benefits of inspecting XSLT include:</span></span>  
  
-   <span data-ttu-id="5ff4e-142">Si está utilizando functoids de bucle o personalizados, sabrá mejor cómo se realiza el bucle y cómo se invoca el functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-142">If you are using looping or custom functoids, you will better understand how the looping is performed and how the custom functoid is invoked.</span></span>  
  
-   <span data-ttu-id="5ff4e-143">Si tiene una asignación complicada, revisar el XSLT le permitirá ver cómo se traduce la asignación a una transformación y puede proporcionarle una visión general acerca de cómo mejor estructura, sustitución o eficacia de una o más partes.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-143">If you have a complicated map, reviewing the XSLT will enable you to see how the map is translated into a transform, and may give you insight on how to better structure, replace, or streamline one or more parts.</span></span>  
  
-   <span data-ttu-id="5ff4e-144">Si está usando secuencias de comandos personalizadas u otros artefactos, revisar el XSLT le permitirá ver cómo interactúan las secuencias de comandos, artefactos y otras partes de la asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-144">If you are using custom scripts or other artifacts, reviewing the XSLT will enable you to see how the scripts, artifacts, and other parts of the map interact.</span></span>  
  
 <span data-ttu-id="5ff4e-145">Es decir, revisar el XSLT es un buena forma de depurar una asignación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-145">In other words, reviewing the XSLT is a great way to debug a map.</span></span>  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a><span data-ttu-id="5ff4e-146">Ver el XSLT generado por el compilador de asignaciones</span><span class="sxs-lookup"><span data-stu-id="5ff4e-146">View the XSLT generated by the map compiler</span></span>  
  
1.  <span data-ttu-id="5ff4e-147">En un proyecto de BizTalk de Visual Studio, seleccione la **el Explorador de soluciones** pestaña, haga clic en un mapa y, a continuación, seleccione **validar asignación**.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-147">From a Visual Studio BizTalk project, select the **Solution Explorer** tab, right-click a map, and then select **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="5ff4e-148">Desplácese a la ventana Resultados para buscar la dirección URL del archivo XSL.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-148">Scroll the Output window to find the URL for the XSL file.</span></span> <span data-ttu-id="5ff4e-149">Presione **CTRL**y seleccione la dirección URL para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-149">Press **CTRL**, and select the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ff4e-150">Los cambios realizados en el archivo XSL no se reflejan en el mapa y se sobrescriben en la siguiente compilación.</span><span class="sxs-lookup"><span data-stu-id="5ff4e-150">Changes made to the XSL file are not reflected in the map and are overwritten on the next build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff4e-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff4e-151">See also</span></span>  

[<span data-ttu-id="5ff4e-152">Cómo depurar mapas</span><span class="sxs-lookup"><span data-stu-id="5ff4e-152">How to Debug Maps</span></span>](../core/how-to-debug-maps.md)  
[<span data-ttu-id="5ff4e-153">Solucionar problemas de asignaciones</span><span class="sxs-lookup"><span data-stu-id="5ff4e-153">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)  