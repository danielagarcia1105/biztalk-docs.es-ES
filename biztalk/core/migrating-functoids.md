---
title: Migrar Functoids | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, migrating
- migrating, maps
- Migrating functoids, about Migrating functoids
- Migrating functoids
- Scripting functoids
- migrating, functoids
- migrating, Scripting functoids
ms.assetid: fc5b3ac9-28c6-41df-b779-15a8c3188528
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b01f37551b9d4c1aef13786be7094504f8cee08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020506"
---
# <a name="migrating-functoids"></a><span data-ttu-id="cb9fb-102">Migrar functoids</span><span class="sxs-lookup"><span data-stu-id="cb9fb-102">Migrating Functoids</span></span>
<span data-ttu-id="cb9fb-103">Cuando se migra una asignación de versiones anteriores de BizTalk Server a BizTalk Server, también se migran todos los functoids incluidos en el mapa.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-103">When you migrate a map from previous versions of BizTalk Server to BizTalk Server, any functoids included in the map are also migrated.</span></span> <span data-ttu-id="cb9fb-104">Si los functoids que migra no incluyen **Scripting** ninguna tarea adicional de functoids, es necesaria.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-104">If the functoids you migrate do not include **Scripting** functoids, no additional migration tasks are required.</span></span> <span data-ttu-id="cb9fb-105">Sin embargo si la asignación incluye **Scripting** functoids personalizados o, es posible que tenga que realice más pasos.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-105">However if your map includes **Scripting** functoids or custom functoids, you may have additional steps to perform.</span></span>  
  
 <span data-ttu-id="cb9fb-106">En versiones anteriores de BizTalk Server, se incluyen todas las secuencias de comandos personalizadas con un **Scripting** functoid se escribía en línea.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-106">In previous versions of BizTalk Server, all custom script included with a **Scripting** functoid was written inline.</span></span> <span data-ttu-id="cb9fb-107">Es decir, que cuando creó el functoid, todas las secuencias de comandos a las que llamó durante el tiempo de ejecución se almacenaron con el functoid.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-107">That is, when you created the functoid, all the script the functoid called during run time was stored with the functoid.</span></span> <span data-ttu-id="cb9fb-108">Si desea utilizar la misma secuencia de comandos con un functoid diferente, debe copiarlo y pegarlo de un **Scripting** reescribe el functoid a otro, o la secuencia de comandos desde el principio.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-108">If you wanted to use the same script with a different functoid, you either copied and pasted it from one **Scripting** functoid to another, or you rewrote the script from scratch.</span></span>  
  
 <span data-ttu-id="cb9fb-109">Al migrar una asignación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia los scripts en línea existentes con los functoids.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copies existing inline scripts with the functoids when you migrate a map.</span></span> <span data-ttu-id="cb9fb-110">Sin embargo, no todos los scripts funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-110">However, not all of the scripts may function correctly.</span></span> <span data-ttu-id="cb9fb-111">BizTalk Server utiliza Visual Basic .NET y JScript. NET, en lugar de VBScript y JScript utilizada en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-111">BizTalk Server uses Visual Basic .NET and JScript .NET rather than the VBScript and JScript used in previous versions.</span></span> <span data-ttu-id="cb9fb-112">Las versiones .NET de los lenguajes incluyen algunos cambios en la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-112">The .NET versions of the languages include some changes in syntax.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb9fb-113">No olvide probar su **Scripting** functoids después de la migración.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-113">Be sure to test your **Scripting** functoids after migration.</span></span>  
  
 <span data-ttu-id="cb9fb-114">Deberá volver a escribir los functoids personalizados.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-114">You will need to rewrite custom functoids.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cb9fb-115"> espera functoids personalizados usen .NET framework.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-115"> expects custom functoids to use the .NET framework.</span></span> <span data-ttu-id="cb9fb-116">No puede utilizar los antiguos functoids personalizados basados en COM.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-116">It cannot use the older, COM-based custom functoids.</span></span> <span data-ttu-id="cb9fb-117">Los functoids personalizados se pueden escribir para que utilicen .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-117">Custom functoids can be rewritten to use the .NET framework.</span></span> <span data-ttu-id="cb9fb-118">Para el código de ejemplo de un functoid personalizado, consulte [Functoid personalizado (ejemplo de BizTalk Server)](../core/custom-functoid-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="cb9fb-118">For sample code of a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
 <span data-ttu-id="cb9fb-119">Una alternativa consiste en ajustar la funcionalidad del functoid personalizado en un ensamblado externo y llamar a este ensamblado mediante un **Scripting** functoid.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-119">An alternative is to wrap the functionality of the custom functoid in an external assembly and call this assembly through a **Scripting** functoid.</span></span> <span data-ttu-id="cb9fb-120">La siguiente sección describe este proceso:</span><span class="sxs-lookup"><span data-stu-id="cb9fb-120">The following section describes this process.</span></span>  
  
### <a name="to-migrate-your-custom-functoids"></a><span data-ttu-id="cb9fb-121">Para migrar los functoids personalizados</span><span class="sxs-lookup"><span data-stu-id="cb9fb-121">To migrate your custom functoids</span></span>  
  
1. <span data-ttu-id="cb9fb-122">Vuelva a crear la funcionalidad de un functoid en un lenguaje .NET, por ejemplo, Microsoft Visual Basic .NET, JScript .NET o Microsoft Visual C# .NET.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-122">Re-create the functionality of the functoid in a .NET language, such as Microsoft Visual Basic .NET, JScript .NET, or Microsoft Visual C# .NET.</span></span>  
  
2. <span data-ttu-id="cb9fb-123">Cree un ensamblado que contenga la nueva funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-123">Create an assembly to contain the new functionality.</span></span>  
  
3. <span data-ttu-id="cb9fb-124">Registre el ensamblado en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="cb9fb-124">Register the assembly in the global assembly cache (GAC).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cb9fb-125">Para registrar los ensamblados en la caché de ensamblados global, deben tener nombres seguros y estar firmados.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-125">To register assemblies in the global assembly cache, they must be strong named and signed.</span></span> <span data-ttu-id="cb9fb-126">Para obtener más información sobre el registro de ensamblados, vea "Caché global de ensamblados" en la colección combinada de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb9fb-126">For more information about registering assemblies, see "Global Assembly Cache" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
4. <span data-ttu-id="cb9fb-127">Crear una referencia entre el mapa que contiene el **Scripting** functoid y el ensamblado que contiene la funcionalidad que se ha vuelto a escribir.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-127">Create a reference between the map that contains the **Scripting** functoid and the assembly that contains the rewritten functionality.</span></span>  
  
5. <span data-ttu-id="cb9fb-128">Configurar la **Script** propiedad para el **Scripting** functoid.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-128">Configure the **Script** property for the **Scripting** functoid.</span></span> <span data-ttu-id="cb9fb-129">Esta propiedad determina qué script el **Scripting** functoid llamadas durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-129">This property determines what script the **Scripting** functoid calls during run time.</span></span> <span data-ttu-id="cb9fb-130">Debe hacer coincidir el valor de esta propiedad con el lenguaje al que convirtió la secuencia de comandos personalizada.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-130">You must match the value of this property to the language into which you converted your custom script.</span></span> <span data-ttu-id="cb9fb-131">Para obtener más información sobre cómo configurar la propiedad de secuencia de comandos, consulte [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="cb9fb-131">For more information about how to configure the Script property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="cb9fb-132">Consulte también [Functoid de Scripting](../core/scripting-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="cb9fb-132">Also see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
6. <span data-ttu-id="cb9fb-133">Compile el proyecto de BizTalk que contiene el mapa con el **Scripting** functoid.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-133">Build the BizTalk project that contains the map with the **Scripting** functoid.</span></span>  
  
7. <span data-ttu-id="cb9fb-134">Valide y pruebe la asignación.</span><span class="sxs-lookup"><span data-stu-id="cb9fb-134">Validate and test the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9fb-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb9fb-135">See Also</span></span>  
 <span data-ttu-id="cb9fb-136">[Editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="cb9fb-136">[Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) </span></span>  
 [<span data-ttu-id="cb9fb-137">Functoid de scripting</span><span class="sxs-lookup"><span data-stu-id="cb9fb-137">Scripting Functoid</span></span>](../core/scripting-functoid.md)