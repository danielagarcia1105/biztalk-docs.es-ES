---
title: Business Rules Hello World2 (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ccc78579c9febfa93b489d72c40ccb603bed92a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972813"
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a><span data-ttu-id="519ce-102">Business Rules Hello World2 (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="519ce-102">Business Rules Hello World2 (BizTalk Server Sample)</span></span>
<span data-ttu-id="519ce-103">El ejemplo Business Rules Hello World2 amplía el ejemplo Business Rules Hello World1 demostrando cómo a la versión, publicar e implementar la regla XML que se establece en el almacén de reglas SQL compartido y cómo ejecutar la directiva con la **directiva** objeto proporciona el marco de trabajo de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="519ce-103">The Business Rules Hello World2 sample extends the Business Rules Hello World1 sample by demonstrating how to version, publish, and deploy the XML rule set to the shared SQL rule store, and how to run the policy using the **Policy** object provided by the Business Rules Framework.</span></span> <span data-ttu-id="519ce-104">El ejemplo también muestra las actualizaciones de directivas dinámicas en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="519ce-104">The sample also demonstrates dynamic policy updates in action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="519ce-105">Este ejemplo da por supuesto que el usuario ha instalado el Servicio de actualización de motor de reglas y los Componentes de reglas de negocios (situados en el nodo "Software adicional") durante la instalación del producto.</span><span class="sxs-lookup"><span data-stu-id="519ce-105">This sample assumes that the user has installed the Rule Engine Update Service and Business Rules Components (located under the "Additional Software" node) during installation of the product.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="519ce-106">Usa **directiva** objetos para integrar el motor de reglas en cualquier aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="519ce-106">You use **Policy** objects to integrate the rule engine into any stand-alone application.</span></span> <span data-ttu-id="519ce-107">El **directiva** objeto es la abstracción administradas a través de la regla a varias instancias del motor, los conjuntos se recuperan y se crean instancias desde el almacén de SQL compartido, y se recuperan y publican al equipo que hospeda las actualizaciones de las directivas de reglas aplicación.</span><span class="sxs-lookup"><span data-stu-id="519ce-107">The **Policy** object is the abstraction through which multiple rule engine instances are managed, rule sets are retrieved and instantiated from the shared SQL store, and updates to the policies are retrieved and published to the hosting application.</span></span>  
  
 <span data-ttu-id="519ce-108">Para obtener información básica acerca de la regla establecer definido y ver hechos de prueba construidos por este ejemplo, vea [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="519ce-108">For basic information about the rule set defined, and sample facts constructed by this sample, see [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="519ce-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="519ce-109">What This Sample Does</span></span>  
 <span data-ttu-id="519ce-110">En este ejemplo se crea un ejecutable que realiza la secuencia de pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="519ce-110">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="519ce-111">Llama al método **CreateRuleset** para generar el conjunto de reglas descrito en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="519ce-111">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="519ce-112">Llama al método **SaveToFile** para mostrar cómo guardar un conjunto de reglas en un archivo.</span><span class="sxs-lookup"><span data-stu-id="519ce-112">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="519ce-113">Llama al método **LoadFromFile** para mostrar cómo cargar un conjunto de reglas de un archivo.</span><span class="sxs-lookup"><span data-stu-id="519ce-113">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="519ce-114">Implementa el conjunto de reglas en un almacén de reglas SQL compartido.</span><span class="sxs-lookup"><span data-stu-id="519ce-114">Deploys the rule set to a shared SQL rule store.</span></span>  
  
5.  <span data-ttu-id="519ce-115">Se ejecuta la regla establecer mediante un **directiva** objeto y usando el mismo conjunto de hechos de ejemplo utilizados en la Business Rules Hello World1 de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="519ce-115">Runs the rule set by using a **Policy** object, and by using the same set of sample facts used in the Business Rules Hello World1 sample.</span></span>  
  
6.  <span data-ttu-id="519ce-116">Hace una pausa, lo que le permite modificar la regla establece archivo **SampleRuleStore.xml** de forma específica.</span><span class="sxs-lookup"><span data-stu-id="519ce-116">Pauses, enabling you to modify the rule set file **SampleRuleStore.xml** in a specific way.</span></span>  
  
7.  <span data-ttu-id="519ce-117">Se ejecuta el conjunto de reglas nuevo mediante un **directiva** de objeto, establecer la regla modificada ahora y nuevo de ejemplo con el mismo conjunto de hechos de ejemplo utilizados en la Business Rules Hello World1.</span><span class="sxs-lookup"><span data-stu-id="519ce-117">Runs the rule set again using a **Policy** object, the now modified rule set, and again with the same set of sample facts used in the Business Rules Hello World1 sample.</span></span>  
  
8.  <span data-ttu-id="519ce-118">Realiza una limpieza mediante la eliminación del archivo de conjunto de reglas y de los registros del conjunto de reglas implementados en preparación de la ejecución posterior del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="519ce-118">Cleans up by deleting the rule set file and the deployed rule set records in preparation for subsequent running of the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="519ce-119">Para obtener información importante acerca de todos los ejemplos de este SDK, consulte [ejemplos](../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="519ce-119">For important information about all samples in this SDK, see [Samples](../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="519ce-120">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="519ce-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="519ce-121">*\<Ejemplos de la ruta de acceso\>* \Business Rules\Business reglas World2\ Hello</span><span class="sxs-lookup"><span data-stu-id="519ce-121">*\<Samples Path\>* \Business Rules\Business Rules Hello World2\\</span></span>  
  
 <span data-ttu-id="519ce-122">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="519ce-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="519ce-123">Archivos</span><span class="sxs-lookup"><span data-stu-id="519ce-123">File(s)</span></span>|<span data-ttu-id="519ce-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="519ce-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="519ce-125">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld2.csproj, BusinessRulesHelloWorld2.sln</span><span class="sxs-lookup"><span data-stu-id="519ce-125">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld2.csproj, BusinessRulesHelloWorld2.sln</span></span>|<span data-ttu-id="519ce-126">Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que crea, guarda, carga, implementa y ejecuta un conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="519ce-126">Project, solution, and related files for the portion of this sample that creates, saves, loads, deploys, and executes a rule set.</span></span>|  
|<span data-ttu-id="519ce-127">HelloWorld2.cs</span><span class="sxs-lookup"><span data-stu-id="519ce-127">HelloWorld2.cs</span></span>|<span data-ttu-id="519ce-128">Archivo de Visual C# que contiene métodos para mostrar cómo crear una regla de conjunto, guardar un conjunto de reglas en un archivo, cómo cargar un conjunto de reglas de un archivo, la regla de implementación de conjunto en un almacén de reglas compartido de Microsoft SQL Server y, a continuación, ejecutar el conjunto de reglas mediante un **directiva**objeto.</span><span class="sxs-lookup"><span data-stu-id="519ce-128">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, loading a rule set from a file, deploying the rule set to a shared Microsoft SQL Server rule store, and then running the rule set by using a **Policy** object.</span></span>|  
|<span data-ttu-id="519ce-129">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="519ce-129">Cleanup.bat</span></span>|<span data-ttu-id="519ce-130">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="519ce-130">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="519ce-131">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="519ce-131">Removes send and receive ports.</span></span> <span data-ttu-id="519ce-132">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="519ce-132">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="519ce-133">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="519ce-133">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="519ce-134">El archivo de entrada de ejemplo que se ajusta al esquema definido en el archivo SampleSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="519ce-134">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="519ce-135">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="519ce-135">SampleSchema.xsd</span></span>|<span data-ttu-id="519ce-136">El archivo de esquema que define un esquema simple con un elemento al que hace referencia el conjunto de reglas creado en el archivo de Visual C# Class1.cs.</span><span class="sxs-lookup"><span data-stu-id="519ce-136">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file Class1.cs.</span></span>|  
|<span data-ttu-id="519ce-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="519ce-137">Setup.bat</span></span>|<span data-ttu-id="519ce-138">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="519ce-138">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="519ce-139">En la carpeta \HelloWorld2Library:</span><span class="sxs-lookup"><span data-stu-id="519ce-139">In the \HelloWorld2Library folder:</span></span><br /><br /> <span data-ttu-id="519ce-140">AssemblyInfo.cs, HelloWorld2Library.csproj, HelloWorld2Library.sln</span><span class="sxs-lookup"><span data-stu-id="519ce-140">AssemblyInfo.cs, HelloWorld2Library.csproj, HelloWorld2Library.sln</span></span>|<span data-ttu-id="519ce-141">Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que proporciona la clase que define los objetos a los que hace referencia el conjunto de reglas creado.</span><span class="sxs-lookup"><span data-stu-id="519ce-141">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="519ce-142">En la carpeta \HelloWorld2Library:</span><span class="sxs-lookup"><span data-stu-id="519ce-142">In the \HelloWorld2Library folder:</span></span><br /><br /> <span data-ttu-id="519ce-143">HelloWorld2LibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="519ce-143">HelloWorld2LibraryClass.cs</span></span>|<span data-ttu-id="519ce-144">Archivo de Visual C# que contiene la propiedad que se hace referenciada en el **IF** parte de la regla creada y el método que se puede llamar en el **, a continuación,** parte de la regla creada.</span><span class="sxs-lookup"><span data-stu-id="519ce-144">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a><span data-ttu-id="519ce-145">Para crear e inicializar el ejemplo Business Rules Hello World2</span><span class="sxs-lookup"><span data-stu-id="519ce-145">To build and initialize the Business Rules Hello World2 sample</span></span>  
  
1. <span data-ttu-id="519ce-146">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="519ce-146">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="519ce-147">*\<Ejemplos de la ruta de acceso\>* \Business Rules\Business reglas World2\ Hello</span><span class="sxs-lookup"><span data-stu-id="519ce-147">*\<Samples Path\>* \Business Rules\Business Rules Hello World2\\</span></span>  
  
2. <span data-ttu-id="519ce-148">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="519ce-148">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="519ce-149">Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="519ce-149">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="519ce-150">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="519ce-150">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="519ce-151">Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear primero un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="519ce-151">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="519ce-152">Utilice este par de claves para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="519ce-152">Use this key pair to sign the resulting assemblies.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="519ce-153">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="519ce-153">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="519ce-154">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="519ce-154">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a><span data-ttu-id="519ce-155">Para ejecutar el ejemplo Business Rules Hello World2</span><span class="sxs-lookup"><span data-stu-id="519ce-155">To run the Business Rules Hello World2 sample</span></span>  
  
1.  <span data-ttu-id="519ce-156">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="519ce-156">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="519ce-157">*\<Ejemplos de la ruta de acceso\>* \Business Rules\Business reglas World2\bin\Debug\ Hello</span><span class="sxs-lookup"><span data-stu-id="519ce-157">*\<Samples Path\>* \Business Rules\Business Rules Hello World2\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="519ce-158">En la ventana de comandos, escriba el nombre del archivo para este ejemplo (**BusinessRulesHelloWorld2.exe**), y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="519ce-158">In the command window, type the name of the file for this sample (**BusinessRulesHelloWorld2.exe**), and then press ENTER.</span></span>  
  
## <a name="hello-world2-output"></a><span data-ttu-id="519ce-159">Resultado de Hello World2</span><span class="sxs-lookup"><span data-stu-id="519ce-159">Hello World2 Output</span></span>  
 <span data-ttu-id="519ce-160">Según la naturaleza del conjunto de reglas creado, se describe en la sección de comentarios de [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md), si ejecuta este ejemplo con el archivo de entrada de ejemplo proporcionado SampleDocumentInstance.xml, que se ha definido un valor de uno (1) para su **ID** elemento, verá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="519ce-160">Based on the nature of the created rule set, described in the Comments section of [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md), if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Deploying the ruleset ...  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...  
Grabbing the policy ...  
Executing the policy...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
The major version of the policy was: 1  
The minor version of the policy was: 0  
Press the ENTER to continue after updating the policy...  
```  
  
> [!NOTE]
>  <span data-ttu-id="519ce-161">El resultado se muestra en negrita es el resultado producido por el objeto empresarial de ejemplo, definido por los archivos en el **HelloWorld2Library** carpeta que la regla establece referencias.</span><span class="sxs-lookup"><span data-stu-id="519ce-161">The output shown in bold is the output produced by the sample business object, defined by the files in the **HelloWorld2Library** folder that the rule set references.</span></span> <span data-ttu-id="519ce-162">En este punto, la aplicación se queda esperando en este estado.</span><span class="sxs-lookup"><span data-stu-id="519ce-162">At this point, the application is left waiting in this state.</span></span>  
  
 <span data-ttu-id="519ce-163">La siguiente parte de la ejecución de este ejemplo conlleva el uso del Compositor de reglas de negocios para cambiar las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="519ce-163">The next part of running the sample involves using the Business Rules Composer to change the business rules.</span></span>  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a><span data-ttu-id="519ce-164">Para usar el Compositor de reglas de negocios para cambiar las reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="519ce-164">To use the Business Rules Composer to change the business rules</span></span>  
  
1. <span data-ttu-id="519ce-165">Para abrir el Compositor de reglas de negocio, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocio**.</span><span class="sxs-lookup"><span data-stu-id="519ce-165">To open the Business Rules Composer, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Composer**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="519ce-166">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="519ce-166">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="519ce-167">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="519ce-167">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="519ce-168">Si aparece un cuadro de diálogo de SQL Server en el equipo que ejecuta SQL Server, haga clic en **Aceptar** para conectarse al almacén de reglas.</span><span class="sxs-lookup"><span data-stu-id="519ce-168">If a SQL Server dialog box appears on the computer running SQL Server, click **OK** to connect to the rule store.</span></span>  
  
3. <span data-ttu-id="519ce-169">En **Explorador de directivas**, a continuación el **SampleRuleSet** nodo, haga clic en el nodo **versión 1.0 – implementada**y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="519ce-169">In **Policy Explorer**, below the **SampleRuleSet** node, right-click the node **Version 1.0 – Deployed**, and then click **Copy**.</span></span>  
  
4. <span data-ttu-id="519ce-170">Haga clic en **SampleRuleSet**y, a continuación, haga clic en **pegar (versión de directiva)**.</span><span class="sxs-lookup"><span data-stu-id="519ce-170">Right-click **SampleRuleSet**, and then click **Paste (Policy Version)**.</span></span>  
  
5. <span data-ttu-id="519ce-171">Puede cambiar la condición de regla y la acción en función de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="519ce-171">You can change the rule condition and action to meet your needs.</span></span> <span data-ttu-id="519ce-172">Para este procedimiento, haga clic en **rule1** en **versión 1.1 (sin guardar)**.</span><span class="sxs-lookup"><span data-stu-id="519ce-172">For this procedure, click **rule1** in **Version 1.1 (not saved)**.</span></span> <span data-ttu-id="519ce-173">En el panel derecho, haga clic en **condiciones**y, a continuación, haga clic en **Agregar operador lógico NOT**.</span><span class="sxs-lookup"><span data-stu-id="519ce-173">In the right pane, right-click **Conditions**, and then click **Add Logical NOT**.</span></span> <span data-ttu-id="519ce-174">Agregar un **NOT lógico** operación **no igual** en el predicado es equivalente a usar un **igual** predicado.</span><span class="sxs-lookup"><span data-stu-id="519ce-174">Adding a **Logical NOT** operation to **Not Equal** to predicate is equivalent to using an **Equal** predicate.</span></span>  
  
6. <span data-ttu-id="519ce-175">Haga clic en el nodo **versión 1.1 (sin guardar)** y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="519ce-175">Right-click the node **Version 1.1(not saved)**, and then click **Save**.</span></span> <span data-ttu-id="519ce-176">Haga clic en nuevo y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="519ce-176">Right-click again, and then click **Publish**.</span></span> <span data-ttu-id="519ce-177">Haga clic en una tercera vez y haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="519ce-177">Right-click a third time and click **Deploy**.</span></span>  
  
7. <span data-ttu-id="519ce-178">En la ventana de comandos pausada que le pide que presione cualquier tecla para continuar tras la actualización de la directiva, presione cualquier tecla.</span><span class="sxs-lookup"><span data-stu-id="519ce-178">In the paused command window asking you to press any key to continue after updating the policy, press any key.</span></span>  
  
   <span data-ttu-id="519ce-179">El resultado (dando por supuesto que ha cambiado la regla mediante la agregación de un operador lógico NOT) del archivo ejecutable BusinessRulesHelloWorld2.exe continúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="519ce-179">Output (assuming you changed the rule by adding a logical Not) from the executable file BusinessRulesHelloWorld2.exe continues as follows:</span></span>  
  
```  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...         
Grabbing the policy ...         
Executing the policy...         
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5         
The major version of the policy was: 1         
The minor version of the policy was: 1         
Press ENTER to continue after updating the policy...         
```  
  
 <span data-ttu-id="519ce-180">Observe cómo ha cambiado el resultado:</span><span class="sxs-lookup"><span data-stu-id="519ce-180">Notice how the output has changed:</span></span>  
  
-   <span data-ttu-id="519ce-181">La línea de salida en el método **MySampleMethod** sólo imprime una vez ahora, para la instancia de la **MySampleBusinessObject** clase para la que el **MyValue** propiedad es igual a 1 , en lugar de la regla anterior de impresión cuando la **MyValue** propiedad no es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="519ce-181">The output line in the method **MySampleMethod** only prints once now, for the instance of the **MySampleBusinessObject** class for which the **MyValue** property is equal to 1, rather than the previous rule of printing when the **MyValue** property is not equal to 1.</span></span>  
  
-   <span data-ttu-id="519ce-182">El número de la versión secundaria de la directiva es ahora 1.</span><span class="sxs-lookup"><span data-stu-id="519ce-182">The minor version number of the policy is now 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519ce-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="519ce-183">See Also</span></span>  
 [<span data-ttu-id="519ce-184">Reglas de negocio (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="519ce-184">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)