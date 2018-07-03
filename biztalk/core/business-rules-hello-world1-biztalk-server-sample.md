---
title: Business Rules Hello World1 (ejemplo de BizTalk Server) | Microsoft Docs
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
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf4afafeabeae8fa9dec0683bd344c40ce23da8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990005"
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a><span data-ttu-id="6c05b-102">Business Rules Hello World1 (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="6c05b-102">Business Rules Hello World1 (BizTalk Server Sample)</span></span>
<span data-ttu-id="6c05b-103">El ejemplo Business Rules Hello World1 muestra cómo crear un conjunto de reglas BizTalk, guardarlo en un archivo (SampleRuleSet.xml), cargarlo y ejecutarlo basado en un conjunto de ejemplos de hechos.</span><span class="sxs-lookup"><span data-stu-id="6c05b-103">The Business Rules Hello World1 sample demonstrates how to create a BizTalk rule set, save it to a file (SampleRuleSet.xml), load it, and run it based on a sample set of facts.</span></span> <span data-ttu-id="6c05b-104">El conjunto de reglas de ejemplos consta de una regla sencilla que implica a un elemento XML y objetos basados en .NET (propiedades y miembros) como términos de la definición de reglas.</span><span class="sxs-lookup"><span data-stu-id="6c05b-104">The sample rule set contains a simple rule that involves an XML element, and .NET-based objects (properties and members) as terms in rule definition.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="6c05b-105">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c05b-105">What This Sample Does</span></span>  
 <span data-ttu-id="6c05b-106">En este ejemplo se crea un ejecutable que realiza la secuencia de pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c05b-106">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="6c05b-107">Llama al método **CreateRuleset** para generar el conjunto de reglas descrito en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="6c05b-107">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="6c05b-108">Llama al método **SaveToFile** para mostrar cómo guardar un conjunto de reglas en un archivo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-108">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="6c05b-109">Llama al método **LoadFromFile** para mostrar cómo cargar un conjunto de reglas de un archivo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-109">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="6c05b-110">Construye hechos de prueba en los que se puede ejecutar el conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="6c05b-110">Constructs sample facts against which to run the rule set.</span></span>  
  
5.  <span data-ttu-id="6c05b-111">Ejecuta el conjunto de reglas en los hechos de prueba, que produce una presentación en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="6c05b-111">Runs the rule set against the sample facts, producing screen output.</span></span>  
  
6.  <span data-ttu-id="6c05b-112">Pausa, le permite examinar el archivo de conjunto de reglas SampleRuleStore.xml.</span><span class="sxs-lookup"><span data-stu-id="6c05b-112">Pauses, enabling you to examine the rule set file SampleRuleStore.xml.</span></span>  
  
7.  <span data-ttu-id="6c05b-113">Realiza una limpieza mediante la eliminación del archivo de conjunto de reglas en preparación de las ejecuciones posteriores del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-113">Cleans up by deleting the rule set file in preparation for subsequent runs of the sample.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="6c05b-114">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c05b-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="6c05b-115">\<*Ejemplos de la ruta de acceso*\>\Business Rules\Business reglas World1\ Hello</span><span class="sxs-lookup"><span data-stu-id="6c05b-115">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
 <span data-ttu-id="6c05b-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="6c05b-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="6c05b-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="6c05b-117">File(s)</span></span>|<span data-ttu-id="6c05b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c05b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c05b-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span><span class="sxs-lookup"><span data-stu-id="6c05b-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span></span>|<span data-ttu-id="6c05b-120">Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que crea, guarda, carga y ejecuta un conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="6c05b-120">Project, solution, and related files for the portion of this sample that creates, saves, loads, and runs a rule set.</span></span>|  
|<span data-ttu-id="6c05b-121">HelloWorld1.cs</span><span class="sxs-lookup"><span data-stu-id="6c05b-121">HelloWorld1.cs</span></span>|<span data-ttu-id="6c05b-122">El archivo de Visual C# que contiene métodos para mostrar cómo se crea un conjunto de reglas, se guarda un conjunto de reglas en un archivo y se carga un conjunto de reglas desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-122">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, and loading a rule set from a file.</span></span> <span data-ttu-id="6c05b-123">También contiene código adyacente que llama a estos métodos y, a continuación, ejecuta el conjunto de reglas creado.</span><span class="sxs-lookup"><span data-stu-id="6c05b-123">Also contains surrounding code that calls these methods and then runs the created rule set.</span></span>|  
|<span data-ttu-id="6c05b-124">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="6c05b-124">Cleanup.bat</span></span>|<span data-ttu-id="6c05b-125">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="6c05b-125">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="6c05b-126">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="6c05b-126">Removes send and receive ports.</span></span> <span data-ttu-id="6c05b-127">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6c05b-127">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="6c05b-128">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="6c05b-128">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="6c05b-129">El archivo de entrada de ejemplo que se ajusta al esquema definido en el archivo SampleSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="6c05b-129">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="6c05b-130">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="6c05b-130">SampleSchema.xsd</span></span>|<span data-ttu-id="6c05b-131">El archivo de esquemas que define un esquema simple con un elemento al que hace referencia el conjunto de reglas creado en el archivo HelloWorld1.cs. de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6c05b-131">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file HelloWorld1.cs.</span></span>|  
|<span data-ttu-id="6c05b-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="6c05b-132">Setup.bat</span></span>|<span data-ttu-id="6c05b-133">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="6c05b-134">En la carpeta \MySampleLibrary:</span><span class="sxs-lookup"><span data-stu-id="6c05b-134">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="6c05b-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="6c05b-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span></span>|<span data-ttu-id="6c05b-136">Proyectos, soluciones y archivos relacionados para la parte de este ejemplo que proporciona la clase que define los objetos a los que hace referencia el conjunto de reglas creado.</span><span class="sxs-lookup"><span data-stu-id="6c05b-136">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="6c05b-137">En la carpeta \MySampleLibrary:</span><span class="sxs-lookup"><span data-stu-id="6c05b-137">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="6c05b-138">MySampleLibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="6c05b-138">MySampleLibraryClass.cs</span></span>|<span data-ttu-id="6c05b-139">Archivo de Visual C# que contiene la propiedad que se hace referenciada en el **IF** parte de la regla creada y el método que se puede llamar en el **, a continuación,** parte de la regla creada.</span><span class="sxs-lookup"><span data-stu-id="6c05b-139">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="6c05b-140">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c05b-140">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="6c05b-141">Use el siguiente procedimiento para generar e inicializar el ejemplo Business Rules Hello World1.</span><span class="sxs-lookup"><span data-stu-id="6c05b-141">Use the following procedure to build and initialize the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="6c05b-142">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c05b-142">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="6c05b-143">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="6c05b-143">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="6c05b-144">\<*Ejemplos de la ruta de acceso*\>\Business Rules\Business reglas World1\ Hello</span><span class="sxs-lookup"><span data-stu-id="6c05b-144">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
2. <span data-ttu-id="6c05b-145">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c05b-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="6c05b-146">Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] de Microsoft para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-146">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6c05b-147">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="6c05b-147">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="6c05b-148">Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear primero un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="6c05b-148">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="6c05b-149">Utilice este par de claves para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="6c05b-149">Use this key pair to sign the resulting assemblies.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="6c05b-150">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="6c05b-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="6c05b-151">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="6c05b-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="6c05b-152">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c05b-152">Running This Sample</span></span>  
 <span data-ttu-id="6c05b-153">Use el siguiente procedimiento para ejecutar el ejemplo Business Rules Hello World1.</span><span class="sxs-lookup"><span data-stu-id="6c05b-153">Use the following procedure to run the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="6c05b-154">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c05b-154">To run this sample</span></span>  
  
1. <span data-ttu-id="6c05b-155">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="6c05b-155">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="6c05b-156">\<*Ejemplos de la ruta de acceso*\>\Business Rules\Business reglas World1\bin\Debug\ Hello</span><span class="sxs-lookup"><span data-stu-id="6c05b-156">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="6c05b-157">En la ventana de comandos, escriba el nombre del archivo ejecutable para este ejemplo (BusinessRulesHelloWorld1.exe) y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6c05b-157">In the command window, type the name of the executable file for this sample (BusinessRulesHelloWorld1.exe), and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6c05b-158">Mientras se ejecuta, este ejemplo produce el conjunto de reglas de archivo SampleRuleStore.xml en la **bin\Debug** carpeta.</span><span class="sxs-lookup"><span data-stu-id="6c05b-158">While running, this sample produces the rule set file SampleRuleStore.xml in the **bin\Debug** folder.</span></span> <span data-ttu-id="6c05b-159">Cuando se pausa el ejecutable y se espera a que presione ENTRAR para finalizar, puede examinar los contenidos de este archivo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-159">When the executable pauses, waiting for you to press ENTER to finish, you can examine the contents of this file.</span></span> <span data-ttu-id="6c05b-160">Recuerde cerrarlo antes de presionar cualquier tecla para finalizar.</span><span class="sxs-lookup"><span data-stu-id="6c05b-160">Remember to close it before pressing any key to finish.</span></span> <span data-ttu-id="6c05b-161">En caso contrario, puede que el ejecutable no pueda quitarlo en preparación de las ejecuciones posteriores del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6c05b-161">Otherwise, the executable may not be able to delete it in preparation for subsequent runs of the sample.</span></span>  
  
   <span data-ttu-id="6c05b-162">Según la naturaleza del conjunto de reglas creado, si ejecuta este ejemplo con el archivo de entrada de ejemplo proporcionado SampleDocumentInstance.xml, que tiene un valor de uno (1) definido para su **ID** elemento, verá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6c05b-162">Based on the nature of the created rule set, if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
> [!NOTE]
>  <span data-ttu-id="6c05b-163">La salida mostrada en negrita, en el código anterior y en el código siguiente, se produce el resultado por el objeto de negocio de ejemplo, definido por los archivos en el **MySampleLibrary** carpeta, que hace referencia el conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="6c05b-163">The output shown in bold, both in the preceding code and in the code that follows, is the output produced by the sample business object, defined by the files in the **MySampleLibrary** folder, which is referenced by the rule set.</span></span>  
  
 <span data-ttu-id="6c05b-164">Si cambia el valor asociado con el **ID** elemento en el archivo de entrada de ejemplo **SampleDocumentInstance.xml** de uno (1) a dos (2), la salida cambiaría como sigue:</span><span class="sxs-lookup"><span data-stu-id="6c05b-164">If you change the value associated with the **ID** element in the sample input file **SampleDocumentInstance.xml** from one (1) to two (2), the output would change as follows:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
 <span data-ttu-id="6c05b-165">No obtendrá una línea de salida para los objetos de la **MySampleBusinessObject** clase que tienen sus **MyValue** propiedad establecida en un valor (durante la construcción) que coincide con el valor asociado con el  **Id. de** elemento en el archivo de entrada de ejemplo SampleDocumentInstance.xml.</span><span class="sxs-lookup"><span data-stu-id="6c05b-165">You will not get an output line for any objects of the **MySampleBusinessObject** class that have their **MyValue** property set to a value (during construction) that matches the value associated with the **ID** element in the sample input file SampleDocumentInstance.xml.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="6c05b-166">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c05b-166">Comments</span></span>  
 <span data-ttu-id="6c05b-167">La regla creada mediante programación dentro del **CreateRuleset()** método muestra:</span><span class="sxs-lookup"><span data-stu-id="6c05b-167">The rule created programmatically within the **CreateRuleset()** method shows:</span></span>  
  
 <span data-ttu-id="6c05b-168">**IF**</span><span class="sxs-lookup"><span data-stu-id="6c05b-168">**IF**</span></span>  
  
 <span data-ttu-id="6c05b-169">**MySampleBusinessObject.MyValue** no es igual al valor de la **ID** elemento en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="6c05b-169">**MySampleBusinessObject.MyValue** is not equal to the value of the **ID** element in the XML document.</span></span>  
  
 <span data-ttu-id="6c05b-170">**THEN**</span><span class="sxs-lookup"><span data-stu-id="6c05b-170">**THEN**</span></span>  
  
 <span data-ttu-id="6c05b-171">**Mysamplebusinessobject.mysamplemethod (int)** con un parámetro entero, disco duro codificado en la constante cinco (5) en este caso.</span><span class="sxs-lookup"><span data-stu-id="6c05b-171">**MySampleBusinessObject.MySampleMethod(int)** with an integer parameter, hard coded to the constant five (5) in this case.</span></span> <span data-ttu-id="6c05b-172">Este método produce las líneas de salida que comienzan **MySampleBusinessObject Class –-**.</span><span class="sxs-lookup"><span data-stu-id="6c05b-172">This method produces the output lines that begin **MySampleBusinessObject Class –-**.</span></span>  
  
 <span data-ttu-id="6c05b-173">Esta regla depende de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c05b-173">This rule depends on the following:</span></span>  
  
- <span data-ttu-id="6c05b-174">Un **MySampleBusinessObject** clase con una propiedad pública denominada **MyValue** y un método público denominado **MySampleMethod** (que toma un parámetro entero).</span><span class="sxs-lookup"><span data-stu-id="6c05b-174">A **MySampleBusinessObject** class with a public property called **MyValue** and a public method called **MySampleMethod** (that takes in an integer parameter).</span></span>  
  
- <span data-ttu-id="6c05b-175">Un esquema XML schema definition language (XSD) que define un documento XML que contiene un **ID** elemento.</span><span class="sxs-lookup"><span data-stu-id="6c05b-175">An XML schema definition language (XSD) schema that defines an XML document that contains an **ID** element.</span></span>  
  
  <span data-ttu-id="6c05b-176">Puede definir las reglas en términos de clases y esquemas pero, durante la ejecución, se necesitan las instancias de objetos de las clases relevantes y las instancias de documentos de los esquemas relevantes.</span><span class="sxs-lookup"><span data-stu-id="6c05b-176">You define rules in terms of classes and schemas, but during execution, object instances of the relevant classes and document instances of the relevant schemas are required.</span></span> <span data-ttu-id="6c05b-177">Evalúe las reglas en estas instancias de tiempo de ejecución (conocidas como hechos).</span><span class="sxs-lookup"><span data-stu-id="6c05b-177">You evaluate the rules against these run-time instances (known as facts).</span></span> <span data-ttu-id="6c05b-178">En este ejemplo, los hechos son varias instancias de la **MySampleBusinessObject** objeto, construido con valores diferentes para sus **MyValue** propiedad y una sola instancia XML del esquema definido que contiene un valor para el **ID** elemento.</span><span class="sxs-lookup"><span data-stu-id="6c05b-178">In this sample, the facts are multiple instances of the **MySampleBusinessObject** object, constructed with different values for their **MyValue** property, and a single XML instance of the defined schema that contains a value for the **ID** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c05b-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c05b-179">See Also</span></span>  
 [<span data-ttu-id="6c05b-180">Reglas de negocio (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="6c05b-180">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)