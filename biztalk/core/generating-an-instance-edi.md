---
title: Generar una instancia (EDI) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362b9803-4d4a-4d17-9ad6-439ec4c7d8aa
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82674b175ad1c408b6ddb9f7823427a550288e96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999301"
---
# <a name="generating-an-instance-edi"></a><span data-ttu-id="22e52-102">Generar una instancia (EDI)</span><span class="sxs-lookup"><span data-stu-id="22e52-102">Generating an Instance (EDI)</span></span>
<span data-ttu-id="22e52-103">Puede generar una instancia de mensaje desde un esquema EDI en el tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="22e52-103">You can generate a message instance from an EDI schema at design time.</span></span> <span data-ttu-id="22e52-104">Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22e52-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span>  
  
 <span data-ttu-id="22e52-105">Puede generar un intercambio procesado por lotes completo (con intercambio y encabezados de grupo) o un conjunto de transacciones (sin intercambio ni encabezados de grupo).</span><span class="sxs-lookup"><span data-stu-id="22e52-105">You can generate either a complete batched interchange (with interchange and group headers) or a transaction set (without interchange and group headers).</span></span> <span data-ttu-id="22e52-106">Si ejecuta la operación para generar un intercambio completo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un archivo con un encabezado de intercambio, un grupo para cada esquema y tres conjuntos de transacciones idénticos por grupo para cada esquema.</span><span class="sxs-lookup"><span data-stu-id="22e52-106">If you execute the operation to generate a complete interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with one interchange header, a group for each schema, and three identical transaction sets per group for each schema.</span></span> <span data-ttu-id="22e52-107">Si ejecuta la operación para generar un conjunto de transacciones, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un archivo con un único conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="22e52-107">If you execute the operation to generate a transaction set, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with a single transaction set.</span></span>  
  
 <span data-ttu-id="22e52-108">Para generar un intercambio procesado por lotes completo, ejecute el comando Generar instancia en el esquema por lotes.</span><span class="sxs-lookup"><span data-stu-id="22e52-108">To generate a complete batched interchange, you execute the generate-instance command on the batch schema.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="22e52-109"> detectará los esquemas de mensaje en el proyecto e incluirá automáticamente los conjuntos de transacciones para esos esquemas.</span><span class="sxs-lookup"><span data-stu-id="22e52-109"> will detect the message schemas in the project, and will automatically include transaction sets for those schemas.</span></span>  
  
 <span data-ttu-id="22e52-110">Para generar un único conjunto de transacciones, ejecute el comando Generar instancia en un esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="22e52-110">To generate a single transaction set, you execute the generate-instance command on a message schema.</span></span> <span data-ttu-id="22e52-111">En este caso, el esquema por lotes no necesita agregarse al proyecto.</span><span class="sxs-lookup"><span data-stu-id="22e52-111">In this case, the batch schema does not need to be added to the project.</span></span> <span data-ttu-id="22e52-112">La instancia generada no incluirá un intercambio ni un encabezado de grupo, por lo que tendrá que agregarlos manualmente para tener un intercambio EDI funcional.</span><span class="sxs-lookup"><span data-stu-id="22e52-112">The generated instance will not include an interchange or group header, however, so you will have to add those manually to have a functional EDI interchange.</span></span>  
  
 <span data-ttu-id="22e52-113">Cuando genere una instancia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará un cuadro de diálogo en el que se especifica la configuración usada en esa instancia, incluidos los separadores y el identificador de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="22e52-113">When you generate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration used in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="22e52-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="22e52-114">Prerequisites</span></span>  
 <span data-ttu-id="22e52-115">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22e52-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a><span data-ttu-id="22e52-116">Para generar una instancia de un intercambio procesado por lotes</span><span class="sxs-lookup"><span data-stu-id="22e52-116">To generate an instance of a batched interchange</span></span>  
  
1. <span data-ttu-id="22e52-117">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto.</span><span class="sxs-lookup"><span data-stu-id="22e52-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="22e52-118">En el Explorador de soluciones, agregue un esquema de mensaje al proyecto para cada tipo de conjunto de transacciones que desee en la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="22e52-118">Add a message schema to the project in Solution Explorer for each type of transaction set that you want in the message instance.</span></span> <span data-ttu-id="22e52-119">Agregue el esquema por lotes para el tipo de codificación al proyecto: Edifact_BatchSchema.xsd o X12_BatchSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="22e52-119">Add the batch schema for the type of encoding to the project: either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22e52-120">Los esquemas de lotes se encuentran en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span><span class="sxs-lookup"><span data-stu-id="22e52-120">The batch schemas are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="22e52-121">No tiene que generar el proyecto para generar una instancia.</span><span class="sxs-lookup"><span data-stu-id="22e52-121">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="22e52-122">Haga clic en el esquema por lotes en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="22e52-122">Right-click the batch schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="22e52-123">En el **propiedades** ventana, establezca **genere el tipo de salida de instancia** a **nativo** o **XML**.</span><span class="sxs-lookup"><span data-stu-id="22e52-123">In the **Properties** window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="22e52-124">Seleccionar **nativo** le solicitará la generación de un archivo sin formato con una extensión. txt.</span><span class="sxs-lookup"><span data-stu-id="22e52-124">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="22e52-125">Seleccionar **XML** le solicitará la generación de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="22e52-125">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="22e52-126">Para **nombre de archivo de instancia de salida**, escriba un nombre o busque un archivo y seleccione el archivo.</span><span class="sxs-lookup"><span data-stu-id="22e52-126">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22e52-127">Si no especifica un valor para el nombre de archivo de la instancia de salida, se elegirá uno de forma automática.</span><span class="sxs-lookup"><span data-stu-id="22e52-127">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="22e52-128">El nombre de archivo aparecerá en la ventana Salida de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22e52-128">The filename will be displayed in the Output window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="22e52-129">Si selecciona un archivo existente, el contenido de éste se reemplazará por el contenido que genera esta operación.</span><span class="sxs-lookup"><span data-stu-id="22e52-129">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="22e52-130">Haga clic en el esquema por lotes y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="22e52-130">Right-click the batch schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="22e52-131">En el **propiedades de instancia EDI** cuadro de diálogo, seleccione los separadores, identificadores y otra configuración de opciones para usarse en esa instancia y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22e52-131">In the **EDI Instance Properties** dialog box, select the separators, identifiers, and other configuration options to be used in that instance, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="22e52-132">Compruebe que la operación ha funcionado en el **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="22e52-132">Verify that the operation worked in the **Output** window.</span></span>  
  
8. <span data-ttu-id="22e52-133">Para ver el archivo, presione **Control** y haga clic en el vínculo en el **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="22e52-133">To view the file, press **Control** and click the link in the **Output** window.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="22e52-134"> se mostrará el contenido del archivo en la ventana del Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="22e52-134"> will display the contents of the file in the BizTalk Editor window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22e52-135">Cuando se genera una instancia que contiene un 837I, 837d o 837p, el valor de GS08 se establecerá forma incorrecta como 00401.</span><span class="sxs-lookup"><span data-stu-id="22e52-135">When generating an instance that contains an 837I, 837D, or 837P, the value of GS08 will be incorrectly set to 00401.</span></span> <span data-ttu-id="22e52-136">Para obtener más información, consulte [problemas conocidos relacionados con las herramientas de XML utilizadas con soluciones EDI](../core/known-issues-with-xml-tools-used-with-edi-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="22e52-136">For more information, see [Known Issues with XML Tools Used with EDI Solutions](../core/known-issues-with-xml-tools-used-with-edi-solutions.md).</span></span>  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a><span data-ttu-id="22e52-137">Para generar una instancia de conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="22e52-137">To generate an instance of a transaction set</span></span>  
  
1. <span data-ttu-id="22e52-138">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto.</span><span class="sxs-lookup"><span data-stu-id="22e52-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="22e52-139">Agregue el esquema del tipo de conjunto de transacciones para el que desea generar una instancia.</span><span class="sxs-lookup"><span data-stu-id="22e52-139">Add the schema for the type of transaction set that you want to generate an instance for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22e52-140">Para generar una instancia de conjunto de transacciones, no necesita agregar el esquema por lotes al proyecto.</span><span class="sxs-lookup"><span data-stu-id="22e52-140">You do not have to add the batch schema to the project to generate an instance of a transaction set.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22e52-141">No tiene que generar el proyecto para generar una instancia.</span><span class="sxs-lookup"><span data-stu-id="22e52-141">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="22e52-142">Haga clic en el esquema de mensaje en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="22e52-142">Right-click the message schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="22e52-143">En la ventana Propiedades, establezca **genere el tipo de salida de instancia** a **nativo** o **XML**.</span><span class="sxs-lookup"><span data-stu-id="22e52-143">In the Properties window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="22e52-144">Seleccionar **nativo** le solicitará la generación de un archivo sin formato con una extensión. txt.</span><span class="sxs-lookup"><span data-stu-id="22e52-144">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="22e52-145">Seleccionar **XML** le solicitará la generación de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="22e52-145">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="22e52-146">Para **nombre de archivo de instancia de salida**, escriba un nombre o busque un archivo y seleccione el archivo.</span><span class="sxs-lookup"><span data-stu-id="22e52-146">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22e52-147">Si no especifica un valor para el nombre de archivo de la instancia de salida, se elegirá uno de forma automática.</span><span class="sxs-lookup"><span data-stu-id="22e52-147">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="22e52-148">El nombre de archivo se mostrará en el **salida** ventana de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22e52-148">The filename will be displayed in the **Output** window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="22e52-149">Si selecciona un archivo existente, el contenido de éste se reemplazará por el contenido que genera esta operación.</span><span class="sxs-lookup"><span data-stu-id="22e52-149">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="22e52-150">Haga clic en el esquema de mensaje y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="22e52-150">Right-click the message schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="22e52-151">En el **propiedades de instancia EDI** cuadro de diálogo, seleccione las opciones de configuración que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22e52-151">In the **EDI Instance Properties** dialog box, select the configuration options that you want, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="22e52-152">Compruebe que hay un mensaje en el **salida** ventana que indica que la operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="22e52-152">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
8. <span data-ttu-id="22e52-153">Para ver el archivo, presione **Control** y haga clic en el vínculo en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="22e52-153">To view the file, press **Control** and click the link in the Output window.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="22e52-154"> se mostrará el contenido del archivo en la ventana del Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="22e52-154"> will display the contents of the file in the BizTalk Editor window.</span></span>  
  
9. <span data-ttu-id="22e52-155">Para crear un mensaje EDI funcional, agregue el intercambio y los encabezados de grupo al mensaje en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="22e52-155">To make a functional EDI message, add the interchange and group headers to the message in a text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e52-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e52-156">See Also</span></span>  
 <span data-ttu-id="22e52-157">[Uso de herramientas de XML en tiempo de diseño](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="22e52-157">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="22e52-158">Validación de una instancia (EDI)</span><span class="sxs-lookup"><span data-stu-id="22e52-158">Validating an Instance (EDI)</span></span>](../core/validating-an-instance-edi.md)