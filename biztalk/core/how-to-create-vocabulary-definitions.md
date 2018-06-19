---
title: Cómo crear definiciones de vocabulario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, definitions
ms.assetid: 6f8fc4c2-2c46-4a7d-a02f-89de0396e3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff9fdfc7cd444a97d1a24353c13d93460c00d4ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250564"
---
# <a name="how-to-create-vocabulary-definitions"></a><span data-ttu-id="bb94e-102">Cómo crear definiciones de vocabulario</span><span class="sxs-lookup"><span data-stu-id="bb94e-102">How to Create Vocabulary Definitions</span></span>
<span data-ttu-id="bb94e-103">Puede utilizar el Asistente para definición de vocabulario para crear definiciones de vocabulario.</span><span class="sxs-lookup"><span data-stu-id="bb94e-103">You can use the Vocabulary Definition Wizard to create vocabulary definitions.</span></span> <span data-ttu-id="bb94e-104">Es posible definir una definición de vocabulario como un valor, un rango de valores, un conjunto de valores constantes o elementos de un ensamblado .NET, un documento XML o una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bb94e-104">You can define a vocabulary definition as a constant value, a range of values, a set of values, or elements of a .NET assembly, XML document, or database table.</span></span> <span data-ttu-id="bb94e-105">Si selecciona una variable pública, habrá **obtener** y **establecer** opciones al igual que en el Asistente para definición de base de datos y XML.</span><span class="sxs-lookup"><span data-stu-id="bb94e-105">If you select a public variable, there will be **Get** and **Set** options just like in Database and XML definition wizard.</span></span>  
  
 <span data-ttu-id="bb94e-106">Como alternativa, puede crear una nueva definición de vocabulario seleccionando un hecho de una de las tres pestañas: por ejemplo, una columna de base de datos, un nodo XML o un miembro de una clase .NET: arrastrar el hecho de sobre para el **vocabularios** ficha, y colocándolo en una versión no publicada de un vocabulario.</span><span class="sxs-lookup"><span data-stu-id="bb94e-106">Alternatively, you can create a new vocabulary definition by selecting a fact from one of the three tabs—for example, a database column, an XML node, or a member of a .NET class—dragging the fact over to the **Vocabularies** tab, and dropping it to an unpublished version of a vocabulary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb94e-107">No es posible agregar una definición de vocabulario a una versión de vocabulario ya publicada.</span><span class="sxs-lookup"><span data-stu-id="bb94e-107">You cannot add a vocabulary definition to a vocabulary version that has been published.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-constant-value"></a><span data-ttu-id="bb94e-108">Para definir una definición de vocabulario como un valor constate</span><span class="sxs-lookup"><span data-stu-id="bb94e-108">To define a vocabulary definition as a constant value</span></span>  
  
1.  <span data-ttu-id="bb94e-109">Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-109">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-110">También puede arrastrar y colocar elementos desde otras pestañas del explorador de hechos: esquemas XML, bases de datos y las clases de .NET</span><span class="sxs-lookup"><span data-stu-id="bb94e-110">You can also drag and drop items from other tabs of Fact Explorer: XML Schemas, Databases and .NET Classes</span></span>  
  
2.  <span data-ttu-id="bb94e-111">En el Asistente para definición de vocabulario, seleccione **valor constante, rango de valores o conjunto de valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-111">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb94e-112">Edite el nombre de definición y la descripción de definición.</span><span class="sxs-lookup"><span data-stu-id="bb94e-112">Edit the definition name and definition description.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-113">La longitud máxima que se mostrará de un nombre de definición es de 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb94e-113">The maximum length for a definition display name is 512 characters.</span></span>  
  
4.  <span data-ttu-id="bb94e-114">Seleccione **valor constante**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-114">Select **Constant Value**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb94e-115">Seleccione un tipo de definición de la lista desplegable de tipos de sistema disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb94e-115">Select a definition type from the drop-down list of available system types.</span></span>  
  
6.  <span data-ttu-id="bb94e-116">Editar el nombre para mostrar y el valor y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-116">Edit the display name and value, and then click **Finish**.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-range-of-values"></a><span data-ttu-id="bb94e-117">Para definir una definición de vocabulario como rango de valores</span><span class="sxs-lookup"><span data-stu-id="bb94e-117">To define a vocabulary definition as a range of values</span></span>  
  
1.  <span data-ttu-id="bb94e-118">Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-118">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="bb94e-119">En el Asistente para definición de vocabulario, seleccione **valor constante, rango de valores o conjunto de valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-119">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb94e-120">Edite el nombre de definición y la descripción de definición.</span><span class="sxs-lookup"><span data-stu-id="bb94e-120">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="bb94e-121">Seleccione **rango de valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-121">Select **Range of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb94e-122">Seleccione un tipo de definición en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bb94e-122">Select a definition type from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="bb94e-123">Haga clic en **rango bajo**y, a continuación, haga clic en **editar** para especificar los valores del rango bajo.</span><span class="sxs-lookup"><span data-stu-id="bb94e-123">Click **Range Low**, and then click **Edit** to specify the values for the lower range.</span></span> <span data-ttu-id="bb94e-124">Se abrirá el cuadro de diálogo de definición de parámetros.</span><span class="sxs-lookup"><span data-stu-id="bb94e-124">The parameter definition dialog will be opened.</span></span>  
  
7.  <span data-ttu-id="bb94e-125">Seleccione **usar valor constante** y escriba un valor constante o seleccione **usar definición de vocabulario publicado** y vaya a una definición de vocabulario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-125">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="bb94e-126">Repita los pasos 6 y 7 para **rango alto**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-126">Repeat steps 6 and 7 for **Range High**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-127">El **rango alto** valor puede superar el **rango bajo** valor.</span><span class="sxs-lookup"><span data-stu-id="bb94e-127">The **Range High** value must exceed the **Range Low** value.</span></span>  
  
9. <span data-ttu-id="bb94e-128">Escriba la cadena de formato de presentación o haga clic en **predeterminado** para volver a la cadena de formato de presentación predeterminado y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-128">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-129">La cadena de formato debe incluir índices de parámetro entre llaves, por ejemplo, "{0}" y "{1}"—to actúan como marcadores de posición para los parámetros de rango alto y bajo.</span><span class="sxs-lookup"><span data-stu-id="bb94e-129">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the high and low range parameters.</span></span>  
  
     <span data-ttu-id="bb94e-130">![Las definiciones de vocabulario](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span><span class="sxs-lookup"><span data-stu-id="bb94e-130">![Vocabulary Definitions](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span></span>  
<span data-ttu-id="bb94e-131">Rango de valores con cadenas de formato</span><span class="sxs-lookup"><span data-stu-id="bb94e-131">Range of values with formatted string</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-set-of-values"></a><span data-ttu-id="bb94e-132">Para definir una definición de vocabulario como conjunto de valores</span><span class="sxs-lookup"><span data-stu-id="bb94e-132">To define a vocabulary definition as a set of values</span></span>  
  
1.  <span data-ttu-id="bb94e-133">Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-133">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="bb94e-134">En el Asistente para definición de vocabulario, seleccione **valor constante, rango de valores o conjunto de valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-134">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb94e-135">Edite el nombre de definición y la descripción de definición.</span><span class="sxs-lookup"><span data-stu-id="bb94e-135">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="bb94e-136">Seleccione **conjunto de valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-136">Select **Set of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb94e-137">Seleccione el tipo de definición y escriba el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="bb94e-137">Enter the definition type and display name.</span></span>  
  
6.  <span data-ttu-id="bb94e-138">Para agregar un miembro al conjunto, seleccione **usar valor constante** y escriba un valor constante o seleccione **usar definición de vocabulario publicado** y vaya a una definición de vocabulario y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-138">To add a member to the set, select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="bb94e-139">Repita el paso 6 con cualquier combinación de definiciones de vocabulario o constantes en tantos elementos como desee incluir en el conjunto.</span><span class="sxs-lookup"><span data-stu-id="bb94e-139">Repeat step 6, with any combination of constants or vocabulary definitions, for as many items as you want to include in your set.</span></span>  
  
8.  <span data-ttu-id="bb94e-140">Para mover un elemento en el orden relativo del conjunto, selecciónelo y, a continuación, haga clic en **una** o **hacia abajo**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-140">To move a member within the relative order of the set, select it and then click **Up** or **Down**.</span></span>  
  
9. <span data-ttu-id="bb94e-141">Para quitar un miembro del conjunto, selecciónelo y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-141">To remove a member from the set, select it and then click **Remove**.</span></span>  
  
10. <span data-ttu-id="bb94e-142">Cuando se haya completado el conjunto, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-142">When you have completed your set, click **Finish**.</span></span>  
  
     <span data-ttu-id="bb94e-143">![Las definiciones de vocabulario](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span><span class="sxs-lookup"><span data-stu-id="bb94e-143">![Vocabulary Definitions](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span></span>  
<span data-ttu-id="bb94e-144">Conjunto de valores</span><span class="sxs-lookup"><span data-stu-id="bb94e-144">Set of values</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-net-class-or-class-member"></a><span data-ttu-id="bb94e-145">Para definir una definición de vocabulario como miembro de clase y clase .NET</span><span class="sxs-lookup"><span data-stu-id="bb94e-145">To define a vocabulary definition as a .NET class or class member</span></span>  
  
1.  <span data-ttu-id="bb94e-146">Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-146">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="bb94e-147">En el Asistente para definición de vocabulario, seleccione **clase .NET o miembro de clase**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-147">In the Vocabulary Definition Wizard, select **.NET Class or Class Member**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb94e-148">Editar la **nombre de definición de** y **descripción** campos.</span><span class="sxs-lookup"><span data-stu-id="bb94e-148">Edit the **Definition Name** and **Description** fields.</span></span>  
  
4.  <span data-ttu-id="bb94e-149">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-149">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="bb94e-150">En el **ensamblados .NET** cuadro de diálogo, seleccione un ensamblado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-150">In the **.NET Assemblies** dialog box, select an assembly, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-151">Los ensamblados tienen que estar en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="bb94e-151">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="bb94e-152">El Compositor de reglas de negocio carga un ensamblado .NET al buscar el ensamblado de .NET en el **Explorador de hechos** ventana o en la **clase .NET o una definición de miembro de clase** página de la **vocabulario Definición de** ventana.</span><span class="sxs-lookup"><span data-stu-id="bb94e-152">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="bb94e-153">Si actualiza el ensamblado en la GAC, cierre el Compositor de reglas de negocios y reinícielo para cargar el ensamblado .NET actualizado.</span><span class="sxs-lookup"><span data-stu-id="bb94e-153">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="bb94e-154">El Compositor de reglas de negocio no actualiza el ensamblado de forma automática.</span><span class="sxs-lookup"><span data-stu-id="bb94e-154">The business rule composer does not refresh the assembly automatically.</span></span>  
  
6.  <span data-ttu-id="bb94e-155">Expanda el nodo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb94e-155">Expand the assembly node.</span></span>  
  
7.  <span data-ttu-id="bb94e-156">Seleccione una clase, o expanda una clase y seleccione un miembro de clase y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-156">Select a class, or expand a class and select a class member, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="bb94e-157">Haga clic en **siguiente**y especifique el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="bb94e-157">Click **Next**, and specify the display name.</span></span>  
  
     <span data-ttu-id="bb94e-158">Para obtener más información, consulte más adelante en este tema "Para especificar el formato de presentación de una definición de vocabulario mediante parámetros".</span><span class="sxs-lookup"><span data-stu-id="bb94e-158">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="bb94e-159">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-159">Click **Finish**.</span></span>  
  
     <span data-ttu-id="bb94e-160">![Las definiciones de vocabulario](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span><span class="sxs-lookup"><span data-stu-id="bb94e-160">![Vocabulary Definitions](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span></span>  
<span data-ttu-id="bb94e-161">Definición de vocabulario de objeto Net</span><span class="sxs-lookup"><span data-stu-id="bb94e-161">Net object vocabulary definition</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-an-xml-document-element-or-attribute"></a><span data-ttu-id="bb94e-162">Para definir una definición de vocabulario como un atributo o elemento de documento XML</span><span class="sxs-lookup"><span data-stu-id="bb94e-162">To define a vocabulary definition as an XML document element or attribute</span></span>  
  
1.  <span data-ttu-id="bb94e-163">Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-163">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="bb94e-164">En el Asistente para definición de vocabulario, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-164">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb94e-165">Escriba un nombre de definición y una descripción de la definición.</span><span class="sxs-lookup"><span data-stu-id="bb94e-165">Type a definition name and a definition description.</span></span>  
  
4.  <span data-ttu-id="bb94e-166">Haga clic en **examinar** para buscar un archivo de esquema y especificar un atributo o elemento de documento.</span><span class="sxs-lookup"><span data-stu-id="bb94e-166">Click **Browse** to locate a schema file and specify a document element or attribute.</span></span>  
  
5.  <span data-ttu-id="bb94e-167">Seleccione en la lista desplegable un tipo compatible con el tipo de atributo o elemento del esquema.</span><span class="sxs-lookup"><span data-stu-id="bb94e-167">From the drop-down list, select a type that is compatible with the type of the element or attribute in the schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-168">Si no puede llevarse a cabo una conversión válida (en cualquiera de los dos sentidos) entre el tipo especificado y el tipo de atributo o elemento de documento, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bb94e-168">If a valid cast cannot be done to or from the specified type to the type of the document element or attribute, you will get an error at run time.</span></span>  
  
6.  <span data-ttu-id="bb94e-169">Seleccione un tipo de operación para indicar si pretende obtener el valor del atributo o elemento (Get) o bien establecer su valor (Set).</span><span class="sxs-lookup"><span data-stu-id="bb94e-169">Select an operation type to indicate whether you plan to get the value of the element or attribute, or to set its value.</span></span>  
  
7.  <span data-ttu-id="bb94e-170">Si decide establecer el valor, haga clic en **siguiente**y, a continuación, especifique el formato de presentación.</span><span class="sxs-lookup"><span data-stu-id="bb94e-170">If you chose to set the value, click **Next**, and then specify the display format.</span></span>  
  
8.  <span data-ttu-id="bb94e-171">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-171">Click **Finish**.</span></span>  
  
     <span data-ttu-id="bb94e-172">![Las definiciones de vocabulario](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span><span class="sxs-lookup"><span data-stu-id="bb94e-172">![Vocabulary Definitions](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span></span>  
<span data-ttu-id="bb94e-173">Definición de vocabulario XML</span><span class="sxs-lookup"><span data-stu-id="bb94e-173">XML vocabulary definition</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb94e-174">La existencia del elemento definido y del tipo de documento no se valida nunca.</span><span class="sxs-lookup"><span data-stu-id="bb94e-174">The existence of the defined element and the document type is never validated.</span></span> <span data-ttu-id="bb94e-175">Si el documento impuesto no contiene el elemento, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bb94e-175">If the asserted document does not have the element, you will get a runtime error.</span></span> <span data-ttu-id="bb94e-176">Si impone un documento con un tipo de documento desconocido, se omitirá.</span><span class="sxs-lookup"><span data-stu-id="bb94e-176">If you assert a document with unknown document type, it will simply be ignored.</span></span>  
  
#### <a name="to-define-a-vocabulary-definition-as-a-database-table-or-database-table-column"></a><span data-ttu-id="bb94e-177">Para definir una definición de vocabulario como tabla o columna de base de datos</span><span class="sxs-lookup"><span data-stu-id="bb94e-177">To define a vocabulary definition as a database table or database table column</span></span>  
  
1.  <span data-ttu-id="bb94e-178">Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-178">Right-click the vocabulary version and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="bb94e-179">En el Asistente para definición de vocabulario, seleccione **tabla de base de datos o la definición de columna de tabla de base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-179">In the Vocabulary Definition Wizard, select **Database Table or Database Table Column Definition**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb94e-180">Escriba un nombre de definición y una descripción de definición.</span><span class="sxs-lookup"><span data-stu-id="bb94e-180">Type a definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="bb94e-181">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-181">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="bb94e-182">Seleccione un equipo de servidor SQL Server al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="bb94e-182">Select a SQL Server computer to connect with.</span></span> <span data-ttu-id="bb94e-183">Si el equipo de SQL Server no está iniciado, seleccione el **iniciar SQL Server si está detenido** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="bb94e-183">If the SQL Server computer is not currently started, select the **Start SQL Server if it is stopped** check box.</span></span>  
  
6.  <span data-ttu-id="bb94e-184">Seleccione un tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="bb94e-184">Select an authentication type.</span></span> <span data-ttu-id="bb94e-185">Si selecciona autenticación de SQL Server, escriba el nombre de inicio de sesión y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-185">If you select SQL Server authentication, type your logon name and password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="bb94e-186">Seleccione la tabla o columna de tabla que desea enlazar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-186">Select the table or table column that you want to bind to, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="bb94e-187">Si ha seleccionado una columna de tabla, seleccione si desea obtener su valor (Get) o establecerlo (Set).</span><span class="sxs-lookup"><span data-stu-id="bb94e-187">If you selected a table column, select whether you want to get its value or set its value.</span></span> <span data-ttu-id="bb94e-188">Si escoge obtener su valor, escriba el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="bb94e-188">If you choose to get its value, type the display name.</span></span> <span data-ttu-id="bb94e-189">Si decide establecer su valor, haga clic en **siguiente** para especificar el formato de presentación.</span><span class="sxs-lookup"><span data-stu-id="bb94e-189">If you choose to set its value, click **Next** to specify the display format.</span></span>  
  
     <span data-ttu-id="bb94e-190">Para obtener más información, consulte más adelante en este tema "Para especificar el formato de presentación de una definición de vocabulario mediante parámetros".</span><span class="sxs-lookup"><span data-stu-id="bb94e-190">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="bb94e-191">Si ha seleccionado una tabla, escriba un nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="bb94e-191">If you selected a table, type a display name.</span></span>  
  
10. <span data-ttu-id="bb94e-192">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-192">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-193">De forma predeterminada, **DataConnection** se usa el enlace</span><span class="sxs-lookup"><span data-stu-id="bb94e-193">By default, **DataConnection** binding is used</span></span>  
  
     <span data-ttu-id="bb94e-194">![Las definiciones de vocabulario](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span><span class="sxs-lookup"><span data-stu-id="bb94e-194">![Vocabulary Definitions](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span></span>  
<span data-ttu-id="bb94e-195">Definición de vocabulario de base de datos</span><span class="sxs-lookup"><span data-stu-id="bb94e-195">Database vocabulary definition</span></span>  
  
#### <a name="to-specify-the-display-format-of-a-vocabulary-definition-by-using-parameters"></a><span data-ttu-id="bb94e-196">Para especificar el formato de presentación de una definición de vocabulario mediante parámetros</span><span class="sxs-lookup"><span data-stu-id="bb94e-196">To specify the display format of a vocabulary definition by using parameters</span></span>  
  
1.  <span data-ttu-id="bb94e-197">Seleccione un parámetro de la lista de **parámetros** en el Asistente para definición de vocabulario y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-197">Select a parameter from the list of **Parameters** in Vocabulary Definition Wizard, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="bb94e-198">Seleccione **usar valor constante** y escriba un valor constante o seleccione **usar definición de vocabulario publicado** y vaya a una definición de vocabulario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-198">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="bb94e-199">Escriba la cadena de formato de presentación o haga clic en **predeterminado** para volver a la cadena de formato de presentación predeterminado y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-199">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb94e-200">La cadena de formato debe incluir índices de parámetro entre llaves, por ejemplo, "{0}" y "{1}"—to actúan como marcadores de posición para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="bb94e-200">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the parameters.</span></span>  
  
     <span data-ttu-id="bb94e-201">![Las definiciones de vocabulario](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span><span class="sxs-lookup"><span data-stu-id="bb94e-201">![Vocabulary Definitions](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span></span>  
<span data-ttu-id="bb94e-202">Definición de vocabulario mediante parámetros</span><span class="sxs-lookup"><span data-stu-id="bb94e-202">Vocabulary definition with parameters</span></span>