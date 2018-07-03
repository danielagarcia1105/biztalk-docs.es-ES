---
title: Importar esquemas de JD Edwards OneWorld en proyectos de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5954f92e55dac362387d66a8b65375e92fe187fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966149"
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a><span data-ttu-id="c4ff8-102">Importación de esquemas de JD Edwards OneWorld en proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c4ff8-102">Importing JD Edwards OneWorld Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="c4ff8-103">En este tema se trata la búsqueda de un servidor de JD Edwards OneWorld y la importación de los esquemas a un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4ff8-103">This topic discusses browsing a JD Edwards OneWorld server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ff8-104">Debe asegurarse de que establece el arglist.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="c4ff8-105">Debe actualizar jdearglist.txt antes de generar los esquemas en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-105">You must update the jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="c4ff8-106">Para obtener más información, consulte [controlar los valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="c4ff8-106">For more information, see [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ff8-107">Cada vez que cambie el jdearglist, debe regenerar los esquemas para ese objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="c4ff8-108">Después de crear el sistema lógico de JD Edwards OneWorld, puede explorar JD Edwards OneWorld abriendo el Asistente para adaptador de Microsoft desde un proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-108">After creating the JD Edwards OneWorld logical system, you can browse JD Edwards OneWorld by opening the Microsoft Adapter Wizard from a BizTalk Server project.</span></span>  
  
### <a name="to-import-schemas"></a><span data-ttu-id="c4ff8-109">Para importar esquemas</span><span class="sxs-lookup"><span data-stu-id="c4ff8-109">To import schemas</span></span>  
  
1. <span data-ttu-id="c4ff8-110">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4ff8-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="c4ff8-111">Haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] , seleccione **agregar**y seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-111">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3. <span data-ttu-id="c4ff8-112">Haga clic en **agregar adaptador**y seleccione **abierto**.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-112">Click **Add adapter**, and select **Open**.</span></span>  
  
4. <span data-ttu-id="c4ff8-113">Seleccione el adaptador y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-113">Select the adapter, and click **Next**.</span></span>  
  
    <span data-ttu-id="c4ff8-114">El JD.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-114">The JD.</span></span> <span data-ttu-id="c4ff8-115">Sistema de Edwards OneWorld XE aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-115">Edwards OneWorld XE system appears in the browser.</span></span>  
  
    <span data-ttu-id="c4ff8-116">![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")</span><span class="sxs-lookup"><span data-stu-id="c4ff8-116">![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")</span></span>  
  
    <span data-ttu-id="c4ff8-117">El Asistente para adaptadores muestra un árbol con todos los sistemas definidos.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-117">The Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="c4ff8-118">JD Edwards OneWorld tiene demasiados módulos para mostrar en una lista larga.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-118">JD Edwards OneWorld has too many modules to show in one long list.</span></span> <span data-ttu-id="c4ff8-119">Los módulos se agrupan juntos de acuerdo con los tres primeros caracteres de su nombre.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-119">The modules are grouped together according to the first three characters of their name.</span></span>  
  
   - <span data-ttu-id="c4ff8-120">El primer nivel de la jerarquía es la lista de todos los prefijos de tres caracteres para los nombres de los módulos.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-120">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
   - <span data-ttu-id="c4ff8-121">El segundo nivel enumera todos los módulos que comparten el mismo prefijo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-121">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
   - <span data-ttu-id="c4ff8-122">El último nivel enumera las funciones empresariales que pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-122">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="c4ff8-123">Al expandir el icono servicios puede ver sus operaciones.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-123">When you expand the services icon you can view its operations.</span></span>  
  
     <span data-ttu-id="c4ff8-124">Al expandir una operación se muestran los argumentos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-124">Expanding an operation displays the input/output arguments.</span></span>  
  
     <span data-ttu-id="c4ff8-125">Puede expandir los argumentos de entrada y salida para ver los tipos de datos de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-125">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c4ff8-126">Si cambian las definiciones del objeto de servidor, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-126">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c4ff8-127">Si cambia el archivo jdearglist.txt después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-127">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="c4ff8-128">Para obtener información sobre jdearglist.txt, consulte [controlar los valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="c4ff8-128">For information on jdearglist.txt, see to [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="c4ff8-129">Generación de esquemas</span><span class="sxs-lookup"><span data-stu-id="c4ff8-129">Generating Schemas</span></span>  
 <span data-ttu-id="c4ff8-130">Use el siguiente procedimiento para generar esquemas.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-130">Use the following procedure to generate schemas.</span></span>  
  
#### <a name="to-generate-schemas"></a><span data-ttu-id="c4ff8-131">Procedimiento para generar esquemas</span><span class="sxs-lookup"><span data-stu-id="c4ff8-131">To generate schemas</span></span>  
  
1.  <span data-ttu-id="c4ff8-132">Seleccione el elemento para el cual desea importar esquemas.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-132">Select the item for which you want to import schemas.</span></span>  
  
2.  <span data-ttu-id="c4ff8-133">Haga clic en (o arrastre) para agregar el elemento a la **transmisión** panel (para un entrante a J. Edwards OneWorld llamar).</span><span class="sxs-lookup"><span data-stu-id="c4ff8-133">Click (or drag) to add the item to the **Transmit** pane (for an inbound to J. Edwards OneWorld call).</span></span>  
  
3.  <span data-ttu-id="c4ff8-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-134">Click **OK**.</span></span>  
  
     <span data-ttu-id="c4ff8-135">Los esquemas generados para el elemento seleccionado de JD Edwards OneWorld se importan en el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-135">Schemas generated for the selected JD Edwards OneWorld item are imported into the BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ff8-136">Cuando se usa la libreta de direcciones (N0100041) es el nombre del campo **cActionCode**.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="c4ff8-137">La acción forma parte del propio archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c4ff8-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="c4ff8-138">Los códigos son:</span><span class="sxs-lookup"><span data-stu-id="c4ff8-138">The codes are:</span></span>  
>   
>  <span data-ttu-id="c4ff8-139">--A para Agregar</span><span class="sxs-lookup"><span data-stu-id="c4ff8-139">--A for Add</span></span>  
>   
>  <span data-ttu-id="c4ff8-140">--C para Cambiar</span><span class="sxs-lookup"><span data-stu-id="c4ff8-140">--C for Change</span></span>  
>   
>  <span data-ttu-id="c4ff8-141">--D para Eliminar</span><span class="sxs-lookup"><span data-stu-id="c4ff8-141">--D for Delete</span></span>  
>   
>  <span data-ttu-id="c4ff8-142">--I para Consulta</span><span class="sxs-lookup"><span data-stu-id="c4ff8-142">--I for Inquiry</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ff8-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4ff8-143">See Also</span></span>  
 [<span data-ttu-id="c4ff8-144">Agregar los artefactos a Administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c4ff8-144">Add the artifacts to BizTalk Administration</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)