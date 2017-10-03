---
title: "Importación de esquemas en BizTalk Server Projects2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing schemas
- schemas, importing into BizTalk Server projects
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ebb0a39850029adec06986da5ddad1fc44c33ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="f89b6-102">Importación de esquemas en proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f89b6-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="f89b6-103">En este tema se trata la búsqueda de un servidor de JD Edwards EnterpriseOne y la importación de los esquemas a un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f89b6-103">This section discusses browsing a JD Edwards EnterpriseOne server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89b6-104">Debe asegurarse de que establece el arglist.</span><span class="sxs-lookup"><span data-stu-id="f89b6-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="f89b6-105">Debe actualizar jdearglist.txt antes de generar los esquemas en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f89b6-105">You must update jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="f89b6-106">Para obtener más información, consulte [control de valores de cadena](../core/handling-string-values2.md).</span><span class="sxs-lookup"><span data-stu-id="f89b6-106">For more information, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89b6-107">Cada vez que cambie el jdearglist, debe regenerar los esquemas para ese objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="f89b6-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="f89b6-108">Después de crear el puerto de JD Edwards EnterpriseOne, puede explorar JD Edwards EnterpriseOne abriendo el Asistente para adaptador de Microsoft desde un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f89b6-108">After creating the JD Edwards EnterpriseOne port, you can browse JD Edwards EnterpriseOne by launching the Microsoft Adapter Wizard from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
### <a name="to-import-schemas-into-a-biztalk-server-project"></a><span data-ttu-id="f89b6-109">Procedimiento para importar esquemas en un proyecto de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f89b6-109">To import schemas into a BizTalk Server project</span></span>  
  
1.  <span data-ttu-id="f89b6-110">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f89b6-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="f89b6-111">Haga clic en el nombre de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] , seleccione **agregar**y seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="f89b6-111">Right-click the name of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="f89b6-112">Haga clic en **agregar** para abrir el **Asistente para agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="f89b6-112">Click **Add** to open the **Add Adapter Wizard**.</span></span>  
  
4.  <span data-ttu-id="f89b6-113">En el **Seleccionar adaptador** , seleccione el nombre del adaptador para el que desea importar esquemas (por ejemplo, **JDEEnterpriseOne**).</span><span class="sxs-lookup"><span data-stu-id="f89b6-113">On the **Select Adapter** page, select the name of the adapter for which you want to import schemas (for example, **JDEEnterpriseOne**).</span></span>  
  
5.  <span data-ttu-id="f89b6-114">En el **SQL Server** , seleccione un servidor SQL server.</span><span class="sxs-lookup"><span data-stu-id="f89b6-114">In the **SQL Server** box, select a SQL server.</span></span>  
  
6.  <span data-ttu-id="f89b6-115">En el **base de datos** , seleccione una base de datos.</span><span class="sxs-lookup"><span data-stu-id="f89b6-115">In the **Database** box, select a database.</span></span>  
  
     <span data-ttu-id="f89b6-116">La base de datos predeterminada es la misma que el servidor SQL.</span><span class="sxs-lookup"><span data-stu-id="f89b6-116">The default database is the same one as your SQL server.</span></span>  
  
7.  <span data-ttu-id="f89b6-117">En el **puerto** cuadro, seleccione un servidor SQL server y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f89b6-117">In the **Port** box, select a SQL server, and then click **Next**.</span></span>  
  
     <span data-ttu-id="f89b6-118">El sistema JD Edwards EnterpriseOne se muestra en el explorador.</span><span class="sxs-lookup"><span data-stu-id="f89b6-118">The JD Edwards EnterpriseOne system displays in the browser.</span></span>  
  
8.  <span data-ttu-id="f89b6-119">Continúe con el siguiente procedimiento a continuación.</span><span class="sxs-lookup"><span data-stu-id="f89b6-119">Continue with the next procedure below.</span></span>  
  
 <span data-ttu-id="f89b6-120">El Asistente para agregar adaptador muestra un árbol con todos los sistemas definidos.</span><span class="sxs-lookup"><span data-stu-id="f89b6-120">The Add Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="f89b6-121">JD Edwards EnterpriseOne tiene muchos módulos.</span><span class="sxs-lookup"><span data-stu-id="f89b6-121">JD Edwards EnterpriseOne has many modules.</span></span> <span data-ttu-id="f89b6-122">Los módulos se agrupan juntos de acuerdo con los tres primeros caracteres de su nombre.</span><span class="sxs-lookup"><span data-stu-id="f89b6-122">The modules are grouped together according to the first three characters of their name.</span></span>  
  
-   <span data-ttu-id="f89b6-123">El primer nivel de la jerarquía es la lista de todos los prefijos de tres caracteres para los nombres de los módulos.</span><span class="sxs-lookup"><span data-stu-id="f89b6-123">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
-   <span data-ttu-id="f89b6-124">El segundo nivel enumera todos los módulos que comparten el mismo prefijo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="f89b6-124">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
-   <span data-ttu-id="f89b6-125">El último nivel enumera las funciones empresariales que pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="f89b6-125">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="f89b6-126">Cuando amplíe el icono de servicios, puede ver sus operaciones.</span><span class="sxs-lookup"><span data-stu-id="f89b6-126">When you expand the services icon, you can view its operations.</span></span>  
  
 <span data-ttu-id="f89b6-127">Al expandir una operación se muestran los argumentos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="f89b6-127">Expanding an operation displays the input/output arguments.</span></span> <span data-ttu-id="f89b6-128">Puede expandir los argumentos de entrada y salida para ver los tipos de datos de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="f89b6-128">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89b6-129">Si cambian las definiciones del objeto de servidor, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="f89b6-129">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89b6-130">Si cambia el archivo jdearglist.txt después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="f89b6-130">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="f89b6-131">Para obtener más información sobre jdearglist.txt, consulte [control de valores de cadena](../core/handling-string-values2.md).</span><span class="sxs-lookup"><span data-stu-id="f89b6-131">For more information on jdearglist.txt, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
### <a name="to-select-the-schemas"></a><span data-ttu-id="f89b6-132">Procedimiento para seleccionar los esquemas</span><span class="sxs-lookup"><span data-stu-id="f89b6-132">To select the schemas</span></span>  
  
1.  <span data-ttu-id="f89b6-133">En el **seleccionar servicios para importar** página, expanda el nodo de nivel superior de la **objetos comerciales** nodo o la **servicios empresariales** nodo.</span><span class="sxs-lookup"><span data-stu-id="f89b6-133">In the **Select Services to Import** page, expand the top level node of the **Business Objects** node or the **Business Services** node.</span></span>  
  
2.  <span data-ttu-id="f89b6-134">Active la casilla situada junto a los elementos que desea importar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f89b6-134">Select the check box next to the items that you want to import, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="f89b6-135">Los esquemas generados para los elementos seleccionados de JD Edwards EnterpriseOne se importan en su proyecto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f89b6-135">Schemas generated for the selected JD Edwards EnterpriseOne items are imported into your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89b6-136">Cuando se utiliza la libreta de direcciones (N0100041) es el nombre del campo **cActionCode**.</span><span class="sxs-lookup"><span data-stu-id="f89b6-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="f89b6-137">La acción forma parte del propio archivo XML.</span><span class="sxs-lookup"><span data-stu-id="f89b6-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="f89b6-138">Los códigos son:</span><span class="sxs-lookup"><span data-stu-id="f89b6-138">The codes are:</span></span>  
  
-   <span data-ttu-id="f89b6-139">A para Agregar</span><span class="sxs-lookup"><span data-stu-id="f89b6-139">A for Add</span></span>  
  
-   <span data-ttu-id="f89b6-140">C para Cambiar</span><span class="sxs-lookup"><span data-stu-id="f89b6-140">C for Change</span></span>  
  
-   <span data-ttu-id="f89b6-141">D para Eliminar</span><span class="sxs-lookup"><span data-stu-id="f89b6-141">D for Delete</span></span>  
  
-   <span data-ttu-id="f89b6-142">I para Consulta</span><span class="sxs-lookup"><span data-stu-id="f89b6-142">I for Inquiry</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89b6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="f89b6-143">See Also</span></span>  
 [<span data-ttu-id="f89b6-144">Crear controladores de JD Edwards EnterpriseOne envío</span><span class="sxs-lookup"><span data-stu-id="f89b6-144">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)