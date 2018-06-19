---
title: Importar esquemas de JD Edwards OneWorld en proyectos de BizTalk Server | Documentos de Microsoft
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
ms.openlocfilehash: cd8e20660a58b647388e7db2324abc5f9a7028e5
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013827"
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a><span data-ttu-id="49a0d-102">Importación de esquemas de JD Edwards OneWorld en proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="49a0d-102">Importing JD Edwards OneWorld Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="49a0d-103">En este tema se trata la búsqueda de un servidor de JD Edwards OneWorld y la importación de los esquemas a un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49a0d-103">This topic discusses browsing a JD Edwards OneWorld server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49a0d-104">Debe asegurarse de que establece el arglist.</span><span class="sxs-lookup"><span data-stu-id="49a0d-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="49a0d-105">Debe actualizar jdearglist.txt antes de generar los esquemas en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="49a0d-105">You must update the jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="49a0d-106">Para obtener más información, consulte [control de valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="49a0d-106">For more information, see [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49a0d-107">Cada vez que cambie el jdearglist, debe regenerar los esquemas para ese objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="49a0d-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="49a0d-108">Después de crear el sistema lógico de JD Edwards OneWorld, puede explorar JD Edwards OneWorld abriendo el Asistente para adaptador de Microsoft desde un proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="49a0d-108">After creating the JD Edwards OneWorld logical system, you can browse JD Edwards OneWorld by opening the Microsoft Adapter Wizard from a BizTalk Server project.</span></span>  
  
### <a name="to-import-schemas"></a><span data-ttu-id="49a0d-109">Para importar esquemas</span><span class="sxs-lookup"><span data-stu-id="49a0d-109">To import schemas</span></span>  
  
1.  <span data-ttu-id="49a0d-110">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49a0d-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="49a0d-111">Haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] , seleccione **agregar**y seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="49a0d-111">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="49a0d-112">Haga clic en **agregar adaptador**y seleccione **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="49a0d-112">Click **Add adapter**, and select **Open**.</span></span>  
  
4.  <span data-ttu-id="49a0d-113">Seleccione el adaptador y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="49a0d-113">Select the adapter, and click **Next**.</span></span>  
  
     <span data-ttu-id="49a0d-114">JD.</span><span class="sxs-lookup"><span data-stu-id="49a0d-114">The JD.</span></span> <span data-ttu-id="49a0d-115">Sistema de Edwards OneWorld XE aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="49a0d-115">Edwards OneWorld XE system appears in the browser.</span></span>  
  
     ![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")  
  
     <span data-ttu-id="49a0d-116">El Asistente para adaptadores muestra un árbol con todos los sistemas definidos.</span><span class="sxs-lookup"><span data-stu-id="49a0d-116">The Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="49a0d-117">JD Edwards OneWorld tiene demasiados módulos para mostrar en una lista larga.</span><span class="sxs-lookup"><span data-stu-id="49a0d-117">JD Edwards OneWorld has too many modules to show in one long list.</span></span> <span data-ttu-id="49a0d-118">Los módulos se agrupan juntos de acuerdo con los tres primeros caracteres de su nombre.</span><span class="sxs-lookup"><span data-stu-id="49a0d-118">The modules are grouped together according to the first three characters of their name.</span></span>  
  
    -   <span data-ttu-id="49a0d-119">El primer nivel de la jerarquía es la lista de todos los prefijos de tres caracteres para los nombres de los módulos.</span><span class="sxs-lookup"><span data-stu-id="49a0d-119">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
    -   <span data-ttu-id="49a0d-120">El segundo nivel enumera todos los módulos que comparten el mismo prefijo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="49a0d-120">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
    -   <span data-ttu-id="49a0d-121">El último nivel enumera las funciones empresariales que pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="49a0d-121">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="49a0d-122">Cuando se expande el icono servicios puede ver sus operaciones.</span><span class="sxs-lookup"><span data-stu-id="49a0d-122">When you expand the services icon you can view its operations.</span></span>  
  
     <span data-ttu-id="49a0d-123">Al expandir una operación se muestran los argumentos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="49a0d-123">Expanding an operation displays the input/output arguments.</span></span>  
  
     <span data-ttu-id="49a0d-124">Puede expandir los argumentos de entrada y salida para ver los tipos de datos de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="49a0d-124">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49a0d-125">Si cambian las definiciones del objeto de servidor, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="49a0d-125">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49a0d-126">Si cambia el archivo jdearglist.txt después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="49a0d-126">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="49a0d-127">Para obtener información sobre jdearglist.txt, consulte [control de valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="49a0d-127">For information on jdearglist.txt, see to [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="49a0d-128">Generación de esquemas</span><span class="sxs-lookup"><span data-stu-id="49a0d-128">Generating Schemas</span></span>  
 <span data-ttu-id="49a0d-129">Use el siguiente procedimiento para generar esquemas.</span><span class="sxs-lookup"><span data-stu-id="49a0d-129">Use the following procedure to generate schemas.</span></span>  
  
#### <a name="to-generate-schemas"></a><span data-ttu-id="49a0d-130">Procedimiento para generar esquemas</span><span class="sxs-lookup"><span data-stu-id="49a0d-130">To generate schemas</span></span>  
  
1.  <span data-ttu-id="49a0d-131">Seleccione el elemento para el cual desea importar esquemas.</span><span class="sxs-lookup"><span data-stu-id="49a0d-131">Select the item for which you want to import schemas.</span></span>  
  
2.  <span data-ttu-id="49a0d-132">Haga clic en (o arrastrar) para agregar el elemento a la **transmisión** panel (para un entrante a J. Edwards OneWorld llamadas).</span><span class="sxs-lookup"><span data-stu-id="49a0d-132">Click (or drag) to add the item to the **Transmit** pane (for an inbound to J. Edwards OneWorld call).</span></span>  
  
3.  <span data-ttu-id="49a0d-133">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49a0d-133">Click **OK**.</span></span>  
  
     <span data-ttu-id="49a0d-134">Los esquemas generados para el elemento seleccionado de JD Edwards OneWorld se importan en el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="49a0d-134">Schemas generated for the selected JD Edwards OneWorld item are imported into the BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49a0d-135">Cuando se utiliza la libreta de direcciones (N0100041) es el nombre del campo **cActionCode**.</span><span class="sxs-lookup"><span data-stu-id="49a0d-135">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="49a0d-136">La acción forma parte del propio archivo XML.</span><span class="sxs-lookup"><span data-stu-id="49a0d-136">The action is part of the XML file itself.</span></span> <span data-ttu-id="49a0d-137">Los códigos son:</span><span class="sxs-lookup"><span data-stu-id="49a0d-137">The codes are:</span></span>  
>   
>  <span data-ttu-id="49a0d-138">--A para Agregar</span><span class="sxs-lookup"><span data-stu-id="49a0d-138">--A for Add</span></span>  
>   
>  <span data-ttu-id="49a0d-139">--C para Cambiar</span><span class="sxs-lookup"><span data-stu-id="49a0d-139">--C for Change</span></span>  
>   
>  <span data-ttu-id="49a0d-140">--D para Eliminar</span><span class="sxs-lookup"><span data-stu-id="49a0d-140">--D for Delete</span></span>  
>   
>  <span data-ttu-id="49a0d-141">--I para Consulta</span><span class="sxs-lookup"><span data-stu-id="49a0d-141">--I for Inquiry</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a0d-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="49a0d-142">See Also</span></span>  
 [<span data-ttu-id="49a0d-143">Agregar los artefactos a la administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="49a0d-143">Add the artifacts to BizTalk Administration</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)