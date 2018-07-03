---
title: Cómo agregar Functoids de Scripting a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.script
ms.assetid: eb96814a-b3fb-48f6-a947-ab595a270faa
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e983564b448ef27323879c6db15ccc232d032d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019142"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a><span data-ttu-id="f74cf-102">Cómo agregar functoids de secuencia de comandos a una asignación</span><span class="sxs-lookup"><span data-stu-id="f74cf-102">How to Add Scripting Functoids to a Map</span></span>
<span data-ttu-id="f74cf-103">El **Scripting** functoid le permite usar un script personalizado o código en tiempo de ejecución para realizar funciones de lo contrario, no está disponibles.</span><span class="sxs-lookup"><span data-stu-id="f74cf-103">The **Scripting** functoid enables you to use custom script or code at run time to perform functions otherwise not available.</span></span> <span data-ttu-id="f74cf-104">Por ejemplo, se puede llamar a un objeto COM en tiempo de ejecución mediante la **Scripting** functoid y escribir su propio script personalizado.</span><span class="sxs-lookup"><span data-stu-id="f74cf-104">For example, you can call a COM object at run time by using the **Scripting** functoid and writing your own custom script.</span></span>  
  
 <span data-ttu-id="f74cf-105">Para obtener información conceptual sobre la **Scripting** functoid, consulte [Functoid de Scripting](../core/scripting-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="f74cf-105">For conceptual information about the **Scripting** functoid, see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="f74cf-106">Para agregar el functoid de secuencia de comandos a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="f74cf-106">To add the Scripting functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="f74cf-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="f74cf-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="f74cf-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f74cf-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="f74cf-109">Arrastre el **Scripting** functoid ![ ] (../core/media/bts-tls-scripting.gif "bts_tls_scripting") desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f74cf-109">Drag the **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting") from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="f74cf-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="f74cf-111">Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="f74cf-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-112">Si se construye un mapa con más de un functoid juntas, necesitará tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="f74cf-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="f74cf-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="f74cf-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="f74cf-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="f74cf-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="f74cf-115">Seleccione el **Scripting** functoid que acaba de agregar a la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="f74cf-115">Select the **Scripting** functoid that you just added to the displayed grid page.</span></span>  
  
4. <span data-ttu-id="f74cf-116">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) botón asociado a la **Script** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f74cf-116">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, click the ellipsis (**...**) button associated with the **Script** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-117">Como alternativa, haga clic en el functoid y, a continuación, haga clic en **Configurar secuencia de comandos de Functoid** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="f74cf-117">Alternatively, you can right-click the functoid, and then click **Configure Functoid Script** in the context menu.</span></span> <span data-ttu-id="f74cf-118">El **configurar Functoid de script** aparece el cuadro de diálogo con el **configuración de Functoid de secuencia de comandos** pestaña seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f74cf-118">The **Configure Scripting Functoid** dialog box appears with the **Script Functoid Configuration** tab selected.</span></span>  
  
5. <span data-ttu-id="f74cf-119">En el **configurar Functoid de script** cuadro de diálogo el **Seleccionar tipo de script** lista desplegable, seleccione el tipo de la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="f74cf-119">In the **Configure Scripting Functoid** dialog box, in the **Select script type** drop-down list, select the type of your script.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-120">Según el tipo de secuencia de comandos que elija, se habilitarán y deshabilitará distintos subconjuntos de los demás campos del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f74cf-120">Depending on your selection of script type, different subsets of the remaining dialog box fields will be enabled and disabled.</span></span>  
  
6. <span data-ttu-id="f74cf-121">Si seleccionó **ensamblado externo** como el tipo de secuencia de comandos, use el **ensamblado de Script**, **clase de Script**, y **método de Script** desplegable las listas, en ese orden, para seleccionar el ensamblado, clase y método, respectivamente, para asociarlos con este **Scripting** functoid.</span><span class="sxs-lookup"><span data-stu-id="f74cf-121">If you selected **External Assembly** as the script type, use the **Script assembly**, **Script class**, and **Script method** drop-down lists, in that order, to select the assembly, class, and method, respectively, to associate with this **Scripting** functoid.</span></span>  
  
   > [!WARNING]
   >  <span data-ttu-id="f74cf-122">El código del ensamblado externo debe ser seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f74cf-122">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="f74cf-123">En condiciones de sobrecarga, pueden ejecutarse simultáneamente varias instancias de una asignación.</span><span class="sxs-lookup"><span data-stu-id="f74cf-123">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-124">Después de haber seleccionado un ensamblado, el **clase de Script** se rellenará la lista desplegable con las clases de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f74cf-124">After you have selected an assembly, the **Script class** drop-down list will be populated with the classes in that assembly.</span></span> <span data-ttu-id="f74cf-125">Del mismo modo, después de haber seleccionado una clase, el **método de Script** se rellenará la lista desplegable con los métodos de esa clase.</span><span class="sxs-lookup"><span data-stu-id="f74cf-125">Likewise, after you have selected a class, the **Script method** drop-down list will be populated with the methods in that class.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-126">El **script en línea** cuadro de texto se deshabilita cuando selecciona **ensamblado externo** como el tipo de secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="f74cf-126">The **Inline script** text box is disabled when you select **External Assembly** as the script type.</span></span>  
  
    <span data-ttu-id="f74cf-127">Si seleccionó algo distinto **ensamblado externo** como el tipo de secuencia de comandos (una de las opciones en línea), use el **script en línea** cuadro de texto para escribir el script en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f74cf-127">If you selected something other than **External Assembly** as the script type (one of the inline choices), use the **Inline script** text box to enter your script in the language you selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-128">Las opciones de idioma en línea para la **Scripting** functoid incluyen C#. NET, JScript.NET, Visual Basic. NET, XSLT y plantilla de llamada XSLT.</span><span class="sxs-lookup"><span data-stu-id="f74cf-128">The inline language choices for the **Scripting** functoid include C# .NET, JScript.NET, Visual Basic .NET, XSLT, and XSLT Call Template.</span></span>  
  
    <span data-ttu-id="f74cf-129">Los scripts que usan C# no permiten declaraciones "using".</span><span class="sxs-lookup"><span data-stu-id="f74cf-129">Scripting using C# does not allow "using" statements.</span></span> <span data-ttu-id="f74cf-130">Si el script debe usar alguna clase .Net especial. A continuación, los ensamblados correspondientes y sus ensamblados dependientes debe agregarse a "Referencias" en el proyecto de BizTalk y el código del script debe usar nombres completos.</span><span class="sxs-lookup"><span data-stu-id="f74cf-130">If the script needs to use any special .Net classes, then the corresponding assemblies and their dependent assemblies should be added to "References" in the BizTalk project, and the script code should use fully qualified names.</span></span> <span data-ttu-id="f74cf-131">Si escribe un script para realizar la conversión de minúsculas sensible a cultura, el fragmento de código correspondiente debe escribirse tal como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="f74cf-131">If you write a script to perform culture-sensitive lowercase conversion, the corresponding code fragment should be written as below.</span></span> <span data-ttu-id="f74cf-132">Se aplican limitaciones similares a todos los lenguajes de script admitidos.</span><span class="sxs-lookup"><span data-stu-id="f74cf-132">Similar limitations apply to all supported scripting languages.</span></span>  
  
   ```  
   string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
   ```  
  
    <span data-ttu-id="f74cf-133">En el script, para usar clases de cualquier ensamblado, asegúrese de agregar el ensamblado correspondiente y sus ensamblados dependientes a “Referencias” en el proyecto de BizTalk que contiene la asignación.</span><span class="sxs-lookup"><span data-stu-id="f74cf-133">In the script, to use classes from any assembly, ensure you add the corresponding assembly and its dependent assemblies to “References” in the BizTalk project containing your map.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-134">Puede crear un script personalizado directamente en el **script en línea** cuadro de texto, o se puede crear el script en otra parte y péguelo en el **script en línea** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f74cf-134">You can create your custom script directly in the **Inline script** text box, or you can create your script elsewhere, and paste it into the **Inline script** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f74cf-135">El **ensamblado de Script**, **clase de Script**, y **método de Script** listas desplegables se deshabilitan cuando selecciona una de las opciones en línea (algo que no sea **Ensamblado externo**) como el tipo de secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="f74cf-135">The **Script assembly**, **Script class**, and **Script method** drop-down lists are disabled when you select one of the inline choices (something other than **External Assembly**) as the script type.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="f74cf-136">Si crea una secuencia de comandos que contenga varias funciones, la primera función se considerará como la principal o primaria; las demás solo se llamarán si son necesarias para la ejecución de la función principal.</span><span class="sxs-lookup"><span data-stu-id="f74cf-136">If you create a script containing multiple functions, the first function will be treated as the main or primary function; other functions are only called if they are called in the execution of the primary function.</span></span>  
  
    <span data-ttu-id="f74cf-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f74cf-137">Click **OK**.</span></span>  
  
7. <span data-ttu-id="f74cf-138">Si la secuencia de comandos o el método asociado en un ensamblado externo requieren parámetros de entrada, cree el número y el tipo de vínculos de entrada apropiados de igual modo que para un functoid básico.</span><span class="sxs-lookup"><span data-stu-id="f74cf-138">If your script or the associated method in an external assembly requires input parameters, create the appropriate number and type of input links as you would for a basic functoid.</span></span>  
  
8. <span data-ttu-id="f74cf-139">En la mayoría de los casos, su **Scripting** functoid generará un valor de salida utilizado para rellenar un campo del esquema de destino, o como entrada para otro functoid, prácticamente la misma manera que functoids básicos hacer.</span><span class="sxs-lookup"><span data-stu-id="f74cf-139">In most circumstances, your **Scripting** functoid will produce an output value used to populate a field in the destination schema, or as input to another functoid, in much the same way that basic functoids do.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74cf-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f74cf-140">See Also</span></span>  
 [<span data-ttu-id="f74cf-141">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="f74cf-141">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)