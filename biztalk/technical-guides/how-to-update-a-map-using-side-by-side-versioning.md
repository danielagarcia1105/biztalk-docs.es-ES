---
title: "Cómo actualizar un mapa con control de versiones en paralelo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d463823a7038e1ead7e2de323da97eda372db76
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a><span data-ttu-id="93530-102">Cómo actualizar un mapa con control de versiones en paralelo</span><span class="sxs-lookup"><span data-stu-id="93530-102">How to Update a Map Using Side-by-Side Versioning</span></span>
<span data-ttu-id="93530-103">Algunos artefactos de BizTalk, como las asignaciones, se eligen por nombre seguro completo (FQSN), en cuyo caso los enlaces incluyen la versión utilizada.</span><span class="sxs-lookup"><span data-stu-id="93530-103">Some BizTalk artifacts, such as maps, are chosen by fully-qualified strong name (FQSN), in which case the bindings include the version used.</span></span> <span data-ttu-id="93530-104">Esto permite que dos o más asignaciones pueden coexistir en paralelo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="93530-104">This allows two or more maps to coexist side by side in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="93530-105">Como resultado, puede seleccionar una de las asignaciones de entrada mapas en las propiedades de ubicación de recepción o de salida en las propiedades de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="93530-105">As a result, you can select one of the maps for inbound mapping in the receive location properties or outbound mapping in the send port properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93530-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="93530-106">Prerequisites</span></span>  
 <span data-ttu-id="93530-107">Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="93530-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a><span data-ttu-id="93530-108">Para agregar una segunda asignación en paralelo a una asignación existente</span><span class="sxs-lookup"><span data-stu-id="93530-108">To add a second map side by side to an existing map</span></span>  
  
1.  <span data-ttu-id="93530-109">Abra Visual Studio y, a continuación, abra el proyecto que contiene la asignación.</span><span class="sxs-lookup"><span data-stu-id="93530-109">Open Visual Studio, and then open the project containing the map.</span></span>  
  
2.  <span data-ttu-id="93530-110">Abra la asignación en el ensamblado y hace un cambio en la asignación de código.</span><span class="sxs-lookup"><span data-stu-id="93530-110">Open the map in the assembly, and make a code change to the map.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93530-111">Si se llama a un mapa desde una orquestación y la referencia de asignación no es modificable, debe realizar cambios en el código en la propia orquestación.</span><span class="sxs-lookup"><span data-stu-id="93530-111">If you call a map from an orchestration, and the map reference is hard-coded, you may need to make code changes to the orchestration itself.</span></span>  
  
3.  <span data-ttu-id="93530-112">Cambiar el número de versión del ensamblado:</span><span class="sxs-lookup"><span data-stu-id="93530-112">Change the version number of the assembly:</span></span>  
  
    1.  <span data-ttu-id="93530-113">En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="93530-113">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="93530-114">En el **Diseñador de proyectos**, haga clic en el **aplicación** ficha.</span><span class="sxs-lookup"><span data-stu-id="93530-114">In the **Project Designer**, click the **Application** tab.</span></span>  
  
    3.  <span data-ttu-id="93530-115">En el panel derecho, haga clic en **información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="93530-115">In the right pane, click **Assembly Information**.</span></span>  
  
    4.  <span data-ttu-id="93530-116">En el **información de ensamblado** diálogo cuadro, especifique valores para la **versión del ensamblado** campo para cambiar el número de versión de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="93530-116">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to change the assembly version number.</span></span> <span data-ttu-id="93530-117">Debe cambiar solo el número de versión principal o secundaria.</span><span class="sxs-lookup"><span data-stu-id="93530-117">You should change only the major or minor version number.</span></span> <span data-ttu-id="93530-118">El número de versión principal es el primer dígito en la secuencia (***n***. 0.0.0); el número de versión secundaria es el segundo dígito en la secuencia (0. ***n*** . 0.0).</span><span class="sxs-lookup"><span data-stu-id="93530-118">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span>  
  
    5.  <span data-ttu-id="93530-119">Haga clic en **Aceptar** para cerrar el **información de ensamblado** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="93530-119">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
4.  <span data-ttu-id="93530-120">Compile el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="93530-120">Compile the assembly.</span></span>  
  
5.  <span data-ttu-id="93530-121">Implementar el ensamblado en el grupo (y todos los equipos).</span><span class="sxs-lookup"><span data-stu-id="93530-121">Deploy the assembly to the group (and all computers).</span></span>  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a><span data-ttu-id="93530-122">Modificar una asignación para reflejar los números de versiones actualizados</span><span class="sxs-lookup"><span data-stu-id="93530-122">Modifying a Map to Reflect Updated Version Numbers</span></span>  
 <span data-ttu-id="93530-123">Desde una asignación se pueden invocar los ensamblados .NET mediante el functoid Secuencias de comandos .</span><span class="sxs-lookup"><span data-stu-id="93530-123">.NET assemblies can be invoked from within a map by using the Scripting functoid.</span></span> <span data-ttu-id="93530-124">Esto proporciona una gran flexibilidad y permite al programador resolver problemas de asignación personalizada muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="93530-124">This provides a great deal of flexibility and enables the developer to solve many different custom mapping problems.</span></span> <span data-ttu-id="93530-125">También impone una restricción unique en la asignación: internamente debe hacer referencia no solo el nombre de tipo de ensamblado, sino también el número de versión completo del ensamblado que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="93530-125">It also imposes a unique constraint on the map—it must internally reference not only the assembly type name but also the full assembly version number being invoked.</span></span> <span data-ttu-id="93530-126">Como consecuencia, si cambia el número de versión del ensamblado al que llama la asignación, se interrumpirán todos los enlaces que hacen referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="93530-126">As a consequence, if the version number of the assembly called by the map changes, all of the links that reference the assembly will break.</span></span>  
  
 <span data-ttu-id="93530-127">Para evitar este problema, se recomienda que si se requieren que se llame desde un mapa de ensamblados, se crea un ensamblado específico para que contenga sólo la funcionalidad de mapas y que el número de versión de ensamblado de este ensamblado es fijo.</span><span class="sxs-lookup"><span data-stu-id="93530-127">To avoid this issue we recommend that if assemblies are required to be called from a map, a specific assembly is created to hold only map functionality and that the assembly version number of this assembly is fixed.</span></span> <span data-ttu-id="93530-128">De este modo, otras funciones auxiliares pueden actualizar la versión de ensamblado sin interrumpir las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="93530-128">In this way, other helper functions can have the assembly version updated without breaking the maps.</span></span>  
  
 <span data-ttu-id="93530-129">Si se cambia un ensamblado al que hace referencia una asignación tras el desarrollo de la asignación, debería actualizar el archivo de asignaciones fuera del editor de asignaciones para que refleje los números de versiones actualizados.</span><span class="sxs-lookup"><span data-stu-id="93530-129">If an assembly referenced from a map is changed after map development then consider updating the map file outside of the Map Editor to reflect the updated version numbers.</span></span>  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a><span data-ttu-id="93530-130">Para modificar un archivo de asignación para que refleje los números de versión actualizada</span><span class="sxs-lookup"><span data-stu-id="93530-130">To modify a map file to reflect updated version numbers</span></span>  
  
1.  <span data-ttu-id="93530-131">Mediante el **iniciar** menú Abrir **el Bloc de notas**.</span><span class="sxs-lookup"><span data-stu-id="93530-131">Using the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="93530-132">En **el Bloc de notas**, en la **archivo** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="93530-132">In **Notepad**, on the **File** menu, click **Open**.</span></span> <span data-ttu-id="93530-133">En el **abiertos** cuadro de diálogo, seleccione la asignación de archivos desea modificar y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="93530-133">In the **Open** dialog box, select the map file you want to modify, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="93530-134">En el menú **Edición** , haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="93530-134">On the **Edit** menu, click **Find**.</span></span> <span data-ttu-id="93530-135">En el **buscar** diálogo cuadro, escriba **ensamblado =**y, a continuación, haga clic en **Buscar siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93530-135">In the **Find** dialog box, enter **Assembly=**, and then click **Find Next**.</span></span>  
  
4.  <span data-ttu-id="93530-136">Si hay una referencia de secuencia de comandos a un ensamblado externo, el Bloc de notas debería buscar un elemento XML como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="93530-136">If there is a script reference to an external assembly, Notepad should find an XML element like the following:</span></span>  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  <span data-ttu-id="93530-137">Actualice el número de versión.</span><span class="sxs-lookup"><span data-stu-id="93530-137">Update the version number.</span></span> <span data-ttu-id="93530-138">Si hay varias instancias, use **reemplazar** en el **editar** menú.</span><span class="sxs-lookup"><span data-stu-id="93530-138">If there are multiple instances, use **Replace** on the **Edit** menu.</span></span>  
  
6.  <span data-ttu-id="93530-139">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="93530-139">Save the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93530-140">Podrá abrir la asignación mediante el editor de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="93530-140">You can now open the map using the Map Editor.</span></span>