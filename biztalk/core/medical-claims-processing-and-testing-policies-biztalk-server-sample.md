---
title: Medical Claims Processing and Testing Policies (ejemplo de BizTalk Server) | Documentos de Microsoft
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
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70cba6055c51371ddaaf99775bd5e7a60e7f3929
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007989"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a><span data-ttu-id="39991-102">Medical Claims directivas de procesamiento y pruebas (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="39991-102">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>
<span data-ttu-id="39991-103">El ejemplo Medical Claims Processing and Testing Policies muestra cómo crear un conjunto de reglas compuesto por varias reglas que examinen hechos derivados de una tabla de la base de datos y del documento entrante, y que usan objetos basados en .NET para registrar los resultados del procesamiento de reclamaciones.</span><span class="sxs-lookup"><span data-stu-id="39991-103">The Medical Claims Processing and Testing Policies sample demonstrates how to create a rule set containing multiple rules that examine facts derived from a database table and the inbound document, and which use .NET-based objects to record the results of the claims processing.</span></span>  
  
 <span data-ttu-id="39991-104">Este ejemplo muestra la ejecución integral del escenario de procesamiento de reclamaciones mediante una aplicación sencilla basada en .NET que usa el Motor de reglas de negocios para ejecutar un conjunto de reglas de reclamaciones médicas en las reclamaciones entrantes y determinar el estado (STATUS) de la reclamación y la razón (REASON) de dicho estado.</span><span class="sxs-lookup"><span data-stu-id="39991-104">This sample demonstrates end-end execution of the claim processing scenario using a simple .NET-based application that uses the Business Rule Engine to run a medical claims rule set against incoming claims to determine the STATUS of the claim and the REASON for the status.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39991-105">Este ejemplo también muestra como realizar el seguimiento de la ejecución del Motor de reglas de negocios mediante un archivo de seguimiento de depuraciones.</span><span class="sxs-lookup"><span data-stu-id="39991-105">This sample also demonstrates how to trace Business Rule Engine execution using a debug trace file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="39991-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="39991-106">What This Sample Does</span></span>  
 <span data-ttu-id="39991-107">Este ejemplo aplica la secuencia de reglas siguiente a las reclamaciones enviadas:</span><span class="sxs-lookup"><span data-stu-id="39991-107">This sample applies the following sequence of rules to submitted claims:</span></span>  
  
1.  <span data-ttu-id="39991-108">Rechaza la reclamación si el importe total reclamado supera el máximo permitido por la póliza.</span><span class="sxs-lookup"><span data-stu-id="39991-108">Rejects the claim if the total amount claimed exceeds the maximum permitted by the policy.</span></span>  
  
2.  <span data-ttu-id="39991-109">Rechaza la reclamación si el cliente ha estado en el hospital más noches que el máximo permitido por la póliza.</span><span class="sxs-lookup"><span data-stu-id="39991-109">Rejects the claim if the client has stayed in hospitals more nights than the maximum permitted by the policy.</span></span>  
  
3.  <span data-ttu-id="39991-110">Rechaza la reclamación si la fecha que figura en ella está en el futuro.</span><span class="sxs-lookup"><span data-stu-id="39991-110">Rejects the claim if the date on the claim is in the future.</span></span>  
  
4.  <span data-ttu-id="39991-111">Rechaza la reclamación si la póliza no es válida.</span><span class="sxs-lookup"><span data-stu-id="39991-111">Rejects the claim if the policy is not valid.</span></span>  
  
5.  <span data-ttu-id="39991-112">Si la póliza ha vencido, envía una indicación al departamento de ventas con el Id. de la póliza y el nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="39991-112">Sends a lead to the sales department with the policy ID and customer name if the policy has expired.</span></span>  
  
6.  <span data-ttu-id="39991-113">En caso contrario, aprueba la reclamación.</span><span class="sxs-lookup"><span data-stu-id="39991-113">Otherwise, approves the claim.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="39991-114">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="39991-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="39991-115">\<*Ejemplos de ruta de acceso*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span><span class="sxs-lookup"><span data-stu-id="39991-115">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
 <span data-ttu-id="39991-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="39991-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="39991-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="39991-117">File(s)</span></span>|<span data-ttu-id="39991-118">Description</span><span class="sxs-lookup"><span data-stu-id="39991-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39991-119">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="39991-119">Cleanup.bat</span></span>|<span data-ttu-id="39991-120">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="39991-120">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="39991-121">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="39991-121">Removes send and receive ports.</span></span> <span data-ttu-id="39991-122">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="39991-122">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="39991-123">Create_PolicyValidity_Table.sql</span><span class="sxs-lookup"><span data-stu-id="39991-123">Create_PolicyValidity_Table.sql</span></span>|<span data-ttu-id="39991-124">Secuencia de comandos SQL que agrega una tabla nueva con el nombre PolicyValidity a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="39991-124">SQL script that adds a new table named PolicyValidity to the Northwind sample database.</span></span>|  
|<span data-ttu-id="39991-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="39991-125">Setup.bat</span></span>|<span data-ttu-id="39991-126">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="39991-126">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="39991-127">En la carpeta \Claims:</span><span class="sxs-lookup"><span data-stu-id="39991-127">In the \Claims folder:</span></span><br /><br /> <span data-ttu-id="39991-128">AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs</span><span class="sxs-lookup"><span data-stu-id="39991-128">AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs</span></span>|<span data-ttu-id="39991-129">Proyectos, soluciones, origen y archivos relacionados para la parte de este ejemplo que registra el resultado de las notificaciones de procesamiento, denominan el **, a continuación,** parte de una regla.</span><span class="sxs-lookup"><span data-stu-id="39991-129">Project, solution, source, and related files for the portion of this sample that records the result of the claims processing, called the **THEN** portion of a rule.</span></span>|  
|<span data-ttu-id="39991-130">En la carpeta \FactRetrieverForClaimsProcessing:</span><span class="sxs-lookup"><span data-stu-id="39991-130">In the \FactRetrieverForClaimsProcessing folder:</span></span><br /><br /> <span data-ttu-id="39991-131">AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="39991-131">AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln</span></span>|<span data-ttu-id="39991-132">Archivos del proyecto, la solución, de origen y relacionados correspondientes a la parte de este ejemplo que proporciona el administrador de almacenes de datos a largo plazo que recupera información de la tabla PolicyValidity creada por este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="39991-132">Project, solution, source, and related files for the portion of this sample that provides the long-term fact retriever that retrieves information from the PolicyValidity table created by this sample.</span></span>|  
|<span data-ttu-id="39991-133">En la carpeta \RulesForMedicalClaims:</span><span class="sxs-lookup"><span data-stu-id="39991-133">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="39991-134">App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln</span><span class="sxs-lookup"><span data-stu-id="39991-134">App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln</span></span>|<span data-ttu-id="39991-135">Proyectos, soluciones, origen y archivos relacionados para la parte de este ejemplo que constituye el ejecutable principal para este ejemplo (RulesForMedicalClaims.exe) y que mediante programación define y almacena el conjunto de reglas, construye datos de ejemplo y, a continuación, se ejecuta el conjunto de reglas mediante un **PolicyTester** objeto.</span><span class="sxs-lookup"><span data-stu-id="39991-135">Project, solution, source, and related files for the portion of this sample that constitutes the main executable for this sample (RulesForMedicalClaims.exe), and which programmatically defines and stores the rule set, constructs sample facts, and then runs the rule set using a **PolicyTester** object.</span></span>|  
|<span data-ttu-id="39991-136">En la carpeta \RulesForMedicalClaims:</span><span class="sxs-lookup"><span data-stu-id="39991-136">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="39991-137">MedicalClaims.xsd</span><span class="sxs-lookup"><span data-stu-id="39991-137">MedicalClaims.xsd</span></span>|<span data-ttu-id="39991-138">Archivo de esquema que define la estructura de las reclamaciones médicas de ejemplo enviadas a este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="39991-138">Schema file that defines the structure of the sample medical claims submitted to this sample.</span></span>|  
|<span data-ttu-id="39991-139">En la carpeta \RulesForMedicalClaims:</span><span class="sxs-lookup"><span data-stu-id="39991-139">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="39991-140">sampleClaim.xml</span><span class="sxs-lookup"><span data-stu-id="39991-140">sampleClaim.xml</span></span>|<span data-ttu-id="39991-141">Archivo de entrada de ejemplo que se ajusta al esquema definido en el archivo MedicalClaims.xsd.</span><span class="sxs-lookup"><span data-stu-id="39991-141">Sample input file that conforms to the schema defined in the file MedicalClaims.xsd.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="39991-142">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="39991-142">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="39991-143">Para crear e inicializar el ejemplo Medical Claims Processing and Testing Policies</span><span class="sxs-lookup"><span data-stu-id="39991-143">To build and initialize the Medical Claims Processing and Testing Policies sample</span></span>  
  
1.  <span data-ttu-id="39991-144">Asegúrese de que la base de datos Northwind esté instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="39991-144">Make sure that you have the Northwind database on your machine.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="39991-145">Para ejecutar este ejemplo, debe tener la base de datos de ejemplo Northwind de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="39991-145">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="39991-146">[Descargar](https://www.microsoft.com/download/details.aspx?id=23654)e instalar.</span><span class="sxs-lookup"><span data-stu-id="39991-146">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 
  
2.  <span data-ttu-id="39991-147">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="39991-147">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="39991-148">\<*Ejemplos de ruta de acceso*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span><span class="sxs-lookup"><span data-stu-id="39991-148">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
3.  <span data-ttu-id="39991-149">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="39991-149">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="39991-150">Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] correspondientes a este ejemplo, incluidos Claims.dll, FactRetrieverForClaimsProcessing.dll y RulesForMedicalClaims.dll.</span><span class="sxs-lookup"><span data-stu-id="39991-150">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including Claims.dll, FactRetrieverForClaimsProcessing.dll, and RulesForMedicalClaims.dll.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39991-151">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="39991-151">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39991-152">Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="39991-152">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="39991-153">Utilice este par de claves para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="39991-153">Use this key pair to sign the resulting assemblies.</span></span>  
  
    -   <span data-ttu-id="39991-154">Ejecuta la secuencia de comandos SQL suministrada Create_PolicyValidity_Table.sql mediante el Analizador de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="39991-154">Runs the provided SQL script Create_PolicyValidity_Table.sql using SQL Query Analyzer.</span></span> <span data-ttu-id="39991-155">La secuencia de comandos crea la tabla, PolicyValidity, con dos filas de ejemplo en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="39991-155">The script creates the table, PolicyValidity, with two sample rows in the Northwind sample database.</span></span> <span data-ttu-id="39991-156">Esta tabla tiene dos columnas: ID y PolicyStatus.</span><span class="sxs-lookup"><span data-stu-id="39991-156">This table has two columns: ID and PolicyStatus.</span></span>  
  
    -   <span data-ttu-id="39991-157">Crea y enlaza los puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39991-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
    -   <span data-ttu-id="39991-158">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="39991-158">Enables the receive location, and starts the send port.</span></span>  
  
    -   <span data-ttu-id="39991-159">Se da de alta e inicia la orquestación.</span><span class="sxs-lookup"><span data-stu-id="39991-159">Enlists and starts orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39991-160">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="39991-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="39991-161">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="39991-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="39991-162">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="39991-162">Running This Sample</span></span>  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="39991-163">Para ejecutar el ejemplo Medical Claims Processing and Testing Policies</span><span class="sxs-lookup"><span data-stu-id="39991-163">To run the Medical Claims Processing and Testing Policies sample</span></span>  
  
1.  <span data-ttu-id="39991-164">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="39991-164">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="39991-165">\<*Ejemplos de ruta de acceso*\>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="39991-165">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="39991-166">Ejecute el archivo RulesForMedicalClaims.exe en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="39991-166">Run the file RulesForMedicalClaims.exe on the command line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39991-167">Puede cambiar los valores de los elementos individuales en el archivo de reclamaciones de ejemplo (sampleClaim.xml) y ejecutar el ejemplo varias veces.</span><span class="sxs-lookup"><span data-stu-id="39991-167">You can change the values of individual elements in the sample claim file sampleClaim.xml and run the sample repeatedly.</span></span> <span data-ttu-id="39991-168">La lista que figura a continuación muestra los resultados previstos para los distintos valores de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="39991-168">The expected outputs for different values in these elements are shown in the list that follows.</span></span>  
  
 <span data-ttu-id="39991-169">Los escenarios de resultados basados en las diversas combinaciones de valores en el archivo de reclamaciones de ejemplo enviado son:</span><span class="sxs-lookup"><span data-stu-id="39991-169">Output scenarios based on various combinations of values in the submitted sample claims file are:</span></span>  
  
-   <span data-ttu-id="39991-170">En el caso de una reclamación cuyo importe supere los 1000 dólares, se obtiene el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="39991-170">For a claim whose amount exceeds $1000, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="39991-171">En el caso de una reclamación cuyo número de noches sea superior a 10, se obtiene el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="39991-171">For a claim whose number of nights exceeds 10, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="39991-172">En el caso de una reclamación cuya fecha no sea válida (fecha > fecha actual), se obtiene el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="39991-172">For a claim whose date is not valid (date > current date), the following output in obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   <span data-ttu-id="39991-173">Para una notificación con un Id. de directiva que no es válida (por ejemplo, si se cambia el **identificador** elemento tenga un valor de 2) debido a la expiración de la directiva, se obtiene el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="39991-173">For a claim with a policy ID that is not valid (for example, by changing the **ID** element to have a value of 2) because of policy expiration, the following output is obtained:</span></span>  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   <span data-ttu-id="39991-174">En el caso de una reclamación válida, se obtiene el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="39991-174">For a claim that is valid, the following output is obtained:</span></span>  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="39991-175">Cada vez que ejecute este ejemplo, se creará un archivo de texto (outputtrace.txt) en la carpeta ...\RulesForMedicalClaims\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="39991-175">A text file, outputtrace.txt, is created in the folder ...\RulesForMedicalClaims\bin\Debug folder every time you run this sample.</span></span> <span data-ttu-id="39991-176">Contiene un seguimiento de depuración de la ejecución de la regla y se crea tras cada ciclo de ejecución en la carpeta \RulesForMedicalClaims\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="39991-176">It contains a debug trace of rule execution, and it is created after every execution cycle under the folder \RulesForMedicalClaims\bin\Debug.</span></span> <span data-ttu-id="39991-177">Puede examinar este archivo para ver el seguimiento de resultados de la ejecución de la regla.</span><span class="sxs-lookup"><span data-stu-id="39991-177">You can examine this file to see the output trace of rule execution.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="39991-178">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39991-178">Comments</span></span>  
 <span data-ttu-id="39991-179">Los orígenes de los datos empleados en la evaluación del conjunto de reglas son:</span><span class="sxs-lookup"><span data-stu-id="39991-179">The fact sources used in the rule set evaluation are:</span></span>  
  
-   <span data-ttu-id="39991-180">Un administrador de almacenes a largo plazo, una. Aplicación basada en red que implementa el **IFactReriever** la interfaz, se crea en la carpeta FactRetrieverForClaimsProcessing.</span><span class="sxs-lookup"><span data-stu-id="39991-180">A long-term fact retriever, a .NET-based application that implements the **IFactReriever** interface, is built in the folder FactRetrieverForClaimsProcessing.</span></span> <span data-ttu-id="39991-181">La directiva de procesamiento de reclamaciones médicas lo emplea para recuperar datos (con forma de conjunto de datos) de la base de datos PolicyValidity y para la evaluación de las condiciones de las reglas.</span><span class="sxs-lookup"><span data-stu-id="39991-181">It is used by the medical claims processing policy to retrieve data (in the form of a dataset) from the PolicyValidity database and to use in rule condition evaluation.</span></span>  
  
-   <span data-ttu-id="39991-182">La notificación está en forma de un documento XML que contiene la siguiente información almacenada en elementos hermanos: nombre, identificador, cantidad, noches y fecha.</span><span class="sxs-lookup"><span data-stu-id="39991-182">The claim is in the form of an XML document that contains the following information, stored in sibling elements: Name, ID, Amount, Nights, and Date.</span></span>  
  
-   <span data-ttu-id="39991-183">UN ARCHIVO. Biblioteca de clases basado en la red (notificaciones), con un **ClaimResults** clase se utiliza para registrar el estado y el motivo de la reclamación mediante propiedades y para enviar una indicación (si la directiva no es válida) mediante la invocación de la **SendLeads** método con el identificador y el nombre como parámetros.</span><span class="sxs-lookup"><span data-stu-id="39991-183">A .NET-based class library (Claims), with a **ClaimResults** class is used to record the STATUS and REASON of the claim using properties, and to send a lead (if the policy is not valid) by invoking the **SendLeads** method with ID and name as parameters.</span></span>  
  
 <span data-ttu-id="39991-184">Según estos orígenes de los datos, se pueden describir de manera informal las reglas definidas para este escenario del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="39991-184">Based on these fact sources, you can informally describe the rules defined for this scenario as follows:</span></span>  
  
1.  <span data-ttu-id="39991-185">Comprobar si la reclamación entrante es válida.</span><span class="sxs-lookup"><span data-stu-id="39991-185">Check to see if the incoming claim is valid.</span></span> <span data-ttu-id="39991-186">La reclamación no es válida si el importe supera el límite permitido para una reclamación, si la póliza ha vencido (verificado mediante la comprobación de la tabla de la base de datos), si el número de noches supera el límite máximo permitido y si se ha realizado la reclamación para una fecha en el futuro.</span><span class="sxs-lookup"><span data-stu-id="39991-186">The claim is not valid if the amount is over the allowable limit for a claim, if the policy has expired (verified by checking the database table), if the number of nights has exceeded the maximum allowable limit, and if the claim is made for a future date.</span></span> <span data-ttu-id="39991-187">Si se ha determinado que la reclamación no es válida, establecer los valores de STATUS y REASON de la reclamación de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="39991-187">If the claim has been determined to be not valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
2.  <span data-ttu-id="39991-188">Si el Id. de la póliza de la reclamación entrante ha vencido, enviar una indicación (con el Id. de la póliza y el nombre del cliente) al departamento de renovación de pólizas.</span><span class="sxs-lookup"><span data-stu-id="39991-188">If the policy ID of the incoming claim has expired, send a lead (with policy ID and customer name) to the policy renewal department.</span></span>  
  
3.  <span data-ttu-id="39991-189">Si la reclamación es válida, establecer los valores de STATUS y REASON de la reclamación de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="39991-189">If the claim is valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
 <span data-ttu-id="39991-190">Una representación más formal de las reglas y sus enlaces de términos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="39991-190">A more formal representation of the rules and their term bindings is as follows:</span></span>  
  
-   <span data-ttu-id="39991-191">**Regla 1. Comprobación de cantidad**</span><span class="sxs-lookup"><span data-stu-id="39991-191">**Rule 1. Amount check**</span></span>  
  
    ```  
    IF Amount in the XML document is > 1000  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"\  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="39991-192">**Regla 2. Noches pasadas en el hospital**</span><span class="sxs-lookup"><span data-stu-id="39991-192">**Rule 2. Nights spent in the hospital**</span></span>  
  
    ```  
    IF number of nights in the XML document is > 10  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="39991-193">**Regla 3. Fecha de validez**</span><span class="sxs-lookup"><span data-stu-id="39991-193">**Rule 3. Date validity**</span></span>  
  
    ```  
    IF date on the incoming XML claim is > Today  
      AND   
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Cannot submit claims in the future!"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="39991-194">**Regla 4. Validez de la póliza**</span><span class="sxs-lookup"><span data-stu-id="39991-194">**Rule 4. Policy validity**</span></span>  
  
    ```  
    IF Policy is invalid for the ID in the XML claim (check database)  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Policy Invalid"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="39991-195">**Regla 5. Responsable de ventas**</span><span class="sxs-lookup"><span data-stu-id="39991-195">**Rule 5. Sales lead**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   <span data-ttu-id="39991-196">**Regla 6. Reclamación aceptada**</span><span class="sxs-lookup"><span data-stu-id="39991-196">**Rule 6. Claim accepted**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="39991-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="39991-197">See Also</span></span>  
 [<span data-ttu-id="39991-198">Reglas de negocio (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="39991-198">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)