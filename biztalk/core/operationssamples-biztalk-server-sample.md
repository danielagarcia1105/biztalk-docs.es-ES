---
title: OperationsSamples (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e42b17f19791eef9bd3f1b5d7d4554f61f08356
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010253"
---
# <a name="operationssamples-biztalk-server-sample"></a><span data-ttu-id="28a81-102">OperationsSamples (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="28a81-102">OperationsSamples (BizTalk Server Sample)</span></span>
<span data-ttu-id="28a81-103">El ejemplo OperationsSamples muestra cómo se realizan actividades operativas mediante el modelo de objetos Operaciones.</span><span class="sxs-lookup"><span data-stu-id="28a81-103">The OperationsSamples sample demonstrates how to perform operational activities using the Operations object model.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="28a81-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-104">What This Sample Does</span></span>  
 <span data-ttu-id="28a81-105">Este ejemplo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28a81-105">This sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="28a81-106">Uso de un perfil de seguimiento para comentar una orquestación con actividades.</span><span class="sxs-lookup"><span data-stu-id="28a81-106">How to use a tracking profile to comment an orchestration with activities.</span></span>  
  
-   <span data-ttu-id="28a81-107">Uso de la base de datos de seguimiento de BAM para buscar un identificador de actividad y usarlo para encontrar una instancia de orquestación relacionada.</span><span class="sxs-lookup"><span data-stu-id="28a81-107">How to use the BAM tracking database to find an activity ID and then use the ID to find a related orchestration instance.</span></span>  
  
-   <span data-ttu-id="28a81-108">Cómo buscar y trabajar con flujos de mensajes mediante la **MessageFlow** clase y otras clases de modelo de objetos de las operaciones y las API.</span><span class="sxs-lookup"><span data-stu-id="28a81-108">How to find and work with message flows by using the **MessageFlow** class and other Operations object model classes and APIs.</span></span>  
  
-   <span data-ttu-id="28a81-109">Cómo obtener acceso a puertos, mensajes y otras instancias mediante las clases derivadas de la **instancia** clase.</span><span class="sxs-lookup"><span data-stu-id="28a81-109">How to access ports, messages, and other instances by using classes derived from the **Instance** class.</span></span>  
  
 <span data-ttu-id="28a81-110">El ejemplo contiene muchas clases y métodos auxiliares que resultan útiles para las operaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="28a81-110">The sample contains many useful helper classes and methods to support the operations above.</span></span> <span data-ttu-id="28a81-111">Estos aspectos destacados y otros sobre el código se explican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="28a81-111">These and other code highlights are discussed in the next section.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="28a81-112">Diseño del ejemplo y justificación</span><span class="sxs-lookup"><span data-stu-id="28a81-112">How This Sample Is Designed and Why</span></span>  
 <span data-ttu-id="28a81-113">Este ejemplo está diseñado para mostrar varios métodos y clases clave del modelo de objetos Operaciones, así como la forma de consultar la base de datos de seguimiento de BAM que está disponible públicamente.</span><span class="sxs-lookup"><span data-stu-id="28a81-113">This sample is designed to demonstrate several of the key classes and methods in the Operations object model and to show how to query the publicly available BAM tracking database.</span></span>  
  
 <span data-ttu-id="28a81-114">El modelo de objetos Operaciones contiene clases que permiten manipular mensajes y otras instancias en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="28a81-114">The Operations object model contains classes that provide the ability to manipulate messages and other instances within BizTalk Server.</span></span>  
  
### <a name="using-a-bam-activity-id"></a><span data-ttu-id="28a81-115">Uso de un identificador de actividad de BAM</span><span class="sxs-lookup"><span data-stu-id="28a81-115">Using a BAM Activity ID</span></span>  
 <span data-ttu-id="28a81-116">Este ejemplo muestra la interacción con BAM y el uso de las vistas disponibles públicamente en la base de datos de seguimiento para localizar un mensaje activo en el cuadro de mensajes a partir de datos económicos.</span><span class="sxs-lookup"><span data-stu-id="28a81-116">This sample shows how to interact with BAM and how to use the publicly available views in the tracking database to locate a live message in the message box by using business data.</span></span> <span data-ttu-id="28a81-117">Para ello, el ejemplo recupera un identificador de orquestación correspondiente a un número de pedido.</span><span class="sxs-lookup"><span data-stu-id="28a81-117">The sample does this by retrieving an orchestration ID corresponding to a purchase order number.</span></span> <span data-ttu-id="28a81-118">Para que esta tarea funcione correctamente, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28a81-118">For this task to succeed, it must do the following:</span></span>  
  
1.  <span data-ttu-id="28a81-119">Utilizar datos económicos (un número de pedido) para encontrar un Id. de actividad.</span><span class="sxs-lookup"><span data-stu-id="28a81-119">Use business data (a purchase order number) to find an activity ID.</span></span> <span data-ttu-id="28a81-120">En este paso se asignan los datos económicos a un Id. interno que se puede utilizar para encontrar información adicional.</span><span class="sxs-lookup"><span data-stu-id="28a81-120">This step maps business data to an internal ID that can be used to find additional information.</span></span>  
  
2.  <span data-ttu-id="28a81-121">Recuperar las referencias de BAM relacionadas con el identificador de actividad.</span><span class="sxs-lookup"><span data-stu-id="28a81-121">Retrieve the BAM references related to the activity ID.</span></span>  
  
3.  <span data-ttu-id="28a81-122">Encontrar una referencia que tenga un tipo de "BizTalkService" y haga referencia a una orquestación.</span><span class="sxs-lookup"><span data-stu-id="28a81-122">Find a reference that has a type of "BizTalkService" and refers to an orchestration.</span></span> <span data-ttu-id="28a81-123">Si se encuentra una, devolver su identificador de instancia.</span><span class="sxs-lookup"><span data-stu-id="28a81-123">If one is found, return its instance ID.</span></span>  
  
 <span data-ttu-id="28a81-124">Esta funcionalidad se proporciona mediante la **BAMWebService.GetOrchestrationID** método estático y los métodos auxiliares asociados incluidas las clases y métodos en el archivo de origen BamManagementService.cs.</span><span class="sxs-lookup"><span data-stu-id="28a81-124">This functionality is provided by the **BAMWebService.GetOrchestrationID** static method and associated helper methods including classes and methods in the BamManagementService.cs source file.</span></span>  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a><span data-ttu-id="28a81-125">Suspensión, finalización y reanudación de instancias</span><span class="sxs-lookup"><span data-stu-id="28a81-125">Suspending, Terminating, and Resuming an Instance</span></span>  
 <span data-ttu-id="28a81-126">El programa de ejemplo incluye una **Samples.OperateOnInstance** método que toma un identificador de operación y la instancia y realiza la operación especificada en la instancia.</span><span class="sxs-lookup"><span data-stu-id="28a81-126">The sample program includes a **Samples.OperateOnInstance** method that takes an operation and instance ID and performs the specified operation on the instance.</span></span> <span data-ttu-id="28a81-127">Las operaciones válidas se definen mediante la **InstanceOperation** enumeración e incluyen suspender, finalizar y reanudar.</span><span class="sxs-lookup"><span data-stu-id="28a81-127">Valid operations are defined by the **InstanceOperation** enumeration and include Suspend, Terminate, and Resume.</span></span> <span data-ttu-id="28a81-128">Estas operaciones se asignan directamente a los métodos de la clase BizTalkOperations:**SuspendInstance**, **TerminateInstance**, y **ResumeInstance**.</span><span class="sxs-lookup"><span data-stu-id="28a81-128">These operations map directly to methods of the BizTalkOperations class—**SuspendInstance**, **TerminateInstance**, and **ResumeInstance**.</span></span>  
  
 <span data-ttu-id="28a81-129">Tenga en cuenta que el método controla las excepciones ArgumentException y SqlException.</span><span class="sxs-lookup"><span data-stu-id="28a81-129">Notice that the method handles both ArgumentException and SqlException exceptions.</span></span> <span data-ttu-id="28a81-130">Debe tener cuidado en la anticipación de excepciones, incluida SqlException, al trabajar con las clases y los métodos del modelo de objetos Operaciones.</span><span class="sxs-lookup"><span data-stu-id="28a81-130">You must be careful to anticipate exceptions—including SqlException—when working with the classes and methods in the Operations object model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28a81-131">Muchos métodos de Operaciones requieren acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28a81-131">Many of the Operations methods require access to the database.</span></span> <span data-ttu-id="28a81-132">Debería anticipar las excepciones que estos métodos inician y controlarlas de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="28a81-132">You should anticipate the exceptions thrown by these methods and handle them appropriately.</span></span>  
  
### <a name="retrieving-all-live-messages"></a><span data-ttu-id="28a81-133">Recuperación de todos los mensajes activos</span><span class="sxs-lookup"><span data-stu-id="28a81-133">Retrieving All Live Messages</span></span>  
 <span data-ttu-id="28a81-134">El modelo de objetos Operaciones facilita la repetición sobre todos los mensajes activos disponibles, tal y como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="28a81-134">The Operations object model makes it straightforward to iterate over all of the available live messages, as shown in the following code fragment:</span></span>  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 <span data-ttu-id="28a81-135">El programa OperationsSamples lleva más lejos este paso al demostrar cómo se obtiene acceso a la información acerca de cada mensaje, incluido el identificador y el tipo de mensaje junto con el número y los tipos de partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="28a81-135">The OperationsSamples program takes this a step further by demonstrating how to access information about each message, including message ID and message type along with the number and types of message parts.</span></span> <span data-ttu-id="28a81-136">Puede modificar este código y usarlo en escenarios donde tenga que repetir en muchos o todos los mensajes activos disponibles en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="28a81-136">You can modify this code and use it in scenarios where you have to iterate through many or all of the available live messages in BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28a81-137">Puede haber cientos o miles de mensajes disponibles.</span><span class="sxs-lookup"><span data-stu-id="28a81-137">There may be hundreds or thousands of messages available.</span></span> <span data-ttu-id="28a81-138">La exploración de toda la lista puede afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="28a81-138">Scanning the entire list may adversely affect performance.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="28a81-139">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-139">Where to Find This Sample</span></span>  
 <span data-ttu-id="28a81-140">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="28a81-140">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="28a81-141">\<*Ejemplos de ruta de acceso*\>\Admin\OperationsOM\OperationsSamples\\</span><span class="sxs-lookup"><span data-stu-id="28a81-141">\<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\\</span></span>  
  
 <span data-ttu-id="28a81-142">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="28a81-142">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="28a81-143">Archivos</span><span class="sxs-lookup"><span data-stu-id="28a81-143">File(s)</span></span>|<span data-ttu-id="28a81-144">Description</span><span class="sxs-lookup"><span data-stu-id="28a81-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28a81-145">BamManagementService.cs</span><span class="sxs-lookup"><span data-stu-id="28a81-145">BamManagementService.cs</span></span>|<span data-ttu-id="28a81-146">Clase de proxy web para el servicio web de BAM.</span><span class="sxs-lookup"><span data-stu-id="28a81-146">Web proxy class for the BAM Web service.</span></span>|  
|<span data-ttu-id="28a81-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="28a81-147">Cleanup.bat</span></span>|<span data-ttu-id="28a81-148">Quita la orquestación de ejemplo y restaura el estado original del ejemplo HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="28a81-148">Removes the sample orchestration and restores the HelloWorld sample to its original state.</span></span>|  
|<span data-ttu-id="28a81-149">HelloOrchestration.btt</span><span class="sxs-lookup"><span data-stu-id="28a81-149">HelloOrchestration.btt</span></span>|<span data-ttu-id="28a81-150">Perfil de seguimiento usado para asignar orígenes de eventos de BizTalk a actividades de destino de BAM.</span><span class="sxs-lookup"><span data-stu-id="28a81-150">Tracking profile used to map BizTalk event sources to BAM target activities.</span></span>|  
|<span data-ttu-id="28a81-151">HelloOrchestration.xls</span><span class="sxs-lookup"><span data-stu-id="28a81-151">HelloOrchestration.xls</span></span>|<span data-ttu-id="28a81-152">Hoja de estilos de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="28a81-152">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="28a81-153">OperationsSamples.cs</span><span class="sxs-lookup"><span data-stu-id="28a81-153">OperationsSamples.cs</span></span>|<span data-ttu-id="28a81-154">Archivo de origen de C# que contiene código que demuestra varios aspectos del modelo de objetos Operaciones.</span><span class="sxs-lookup"><span data-stu-id="28a81-154">C# source file containing code that demonstrates various aspects of the Operations object model.</span></span>|  
|<span data-ttu-id="28a81-155">OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="28a81-155">OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs</span></span>|<span data-ttu-id="28a81-156">Archivos de información de proyectos, soluciones y ensamblados para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="28a81-156">Project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="28a81-157">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="28a81-157">Setup.bat</span></span>|<span data-ttu-id="28a81-158">Usado para crear e inicializar este ejemplo mediante la modificación del ejemplo de orquestación HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="28a81-158">Used to build and initialize this sample by modifying the HelloWorld orchestration sample.</span></span> <span data-ttu-id="28a81-159">Instala una orquestación de ejemplo, implementa una definición de actividad de BAM y un archivo de editor de perfiles de seguimiento, configura puertos y coloca un archivo de ejemplo en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="28a81-159">It installs a sample orchestration, deploys a BAM Activity Definition and a Tracking Profile Editor file, configures ports, and drops a sample file into the receive location.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="28a81-160">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-160">How to Use This Sample</span></span>  
 <span data-ttu-id="28a81-161">Use este ejemplo para explorar la funcionalidad disponible en el modelo de objetos Operaciones.</span><span class="sxs-lookup"><span data-stu-id="28a81-161">Use this sample to explore the functionality available in the Operations object model.</span></span> <span data-ttu-id="28a81-162">Modifique las rutinas que existen para buscar y trabajar con mensajes de un modo diferente o para agregar código nuevo que replique partes del concentrador de grupo en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="28a81-162">Modify existing routines to find and work with messages differently or add new code that replicates portions of the Group Hub in the BizTalk Server Management console.</span></span>  
  
 <span data-ttu-id="28a81-163">Considere también la opción de llevar a cabo algunas de las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="28a81-163">You may also consider some of the following tasks:</span></span>  
  
-   <span data-ttu-id="28a81-164">Escribir una aplicación que replique el subconjunto más usado del concentrador de grupo en una aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="28a81-164">Write an application that replicates the most-used subset of the Group Hub into a custom application.</span></span>  
  
-   <span data-ttu-id="28a81-165">Escribir una aplicación de suministro personalizada que cree puertos y envíe un mensaje de prueba a través de socios comerciales nuevos.</span><span class="sxs-lookup"><span data-stu-id="28a81-165">Write a custom provisioning application that creates ports and sends a test message through for new trading partners.</span></span>  
  
-   <span data-ttu-id="28a81-166">Modificar el programa de ejemplo en una utilidad de línea de comandos que proporcione información acerca de un único pedido o de un intervalo de pedidos en la pantalla, en un archivo XML o en un informe de texto.</span><span class="sxs-lookup"><span data-stu-id="28a81-166">Modify the sample program into a command-line utility that provides information about a single purchase order or a range of purchase orders to the screen, an XML file, or a text report.</span></span>  
  
## <a name="installing-sample-support-files"></a><span data-ttu-id="28a81-167">Instalación de archivos adicionales del ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-167">Installing Sample Support Files</span></span>  
 <span data-ttu-id="28a81-168">En esta sección se le guiará por los procedimientos necesarios para instalar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="28a81-168">This section walks through the procedures required to install and run the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28a81-169">Antes de instalar y ejecutar este ejemplo, debe comprobar que BAM está instalado y que funciona.</span><span class="sxs-lookup"><span data-stu-id="28a81-169">Before installing and running this sample, you must verify that BAM has been installed and is functioning.</span></span> <span data-ttu-id="28a81-170">Si BAM no está instalado, el ejemplo no funcionará.</span><span class="sxs-lookup"><span data-stu-id="28a81-170">If BAM has not been installed, this sample will not work.</span></span>  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a><span data-ttu-id="28a81-171">Procedimiento para compilar e instalar los archivos adicionales de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-171">To compile and install the support files for this sample</span></span>  
  
1.  <span data-ttu-id="28a81-172">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="28a81-172">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  <span data-ttu-id="28a81-173">Ejecute el archivo Setup.bat, que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28a81-173">Run Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="28a81-174">Crea directorios de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="28a81-174">Creates send and receive directories</span></span>  
  
    -   <span data-ttu-id="28a81-175">Crea e inicia puertos de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="28a81-175">Creates and starts send and receive ports</span></span>  
  
    -   <span data-ttu-id="28a81-176">Compila e implementa la orquestación HelloWorld en la carpeta `<Samples Path>`\Orchestrations\HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="28a81-176">Compiles and deploys the HelloWorld orchestration in the `<Samples Path>`\Orchestrations\HelloWorld folder.</span></span>  
  
    -   <span data-ttu-id="28a81-177">Modifica el token de clave pública para la orquestación HelloWorld</span><span class="sxs-lookup"><span data-stu-id="28a81-177">Modifies the public key token for the HelloWorld orchestration</span></span>  
  
    -   <span data-ttu-id="28a81-178">Implementa la definición de actividad de BAM y el archivo del editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="28a81-178">Deploys the BAM Activity Definition and Tracking Profile Editor file</span></span>  
  
    -   <span data-ttu-id="28a81-179">Cambia el nombre del directorio de salida</span><span class="sxs-lookup"><span data-stu-id="28a81-179">Renames the out directory</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28a81-180">Para anular la instalación, presione CTRL+C la primera vez que aparezca el mensaje “Presione cualquier tecla para continuar”.</span><span class="sxs-lookup"><span data-stu-id="28a81-180">To abort the installation, press CTRL+C at the first "press any key to continue" prompt.</span></span> <span data-ttu-id="28a81-181">De este modo se detiene la secuencia de comandos y se deja el estado original del ejemplo HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="28a81-181">This stops the script and leaves the HelloWorld sample in its original state.</span></span> <span data-ttu-id="28a81-182">Si se presiona CTRL+C en el segundo y último mensaje, la instalación no se detiene.</span><span class="sxs-lookup"><span data-stu-id="28a81-182">Pressing CTRL+C on the second and final prompt does not stop the installation.</span></span> <span data-ttu-id="28a81-183">Llegado este caso, ejecute Cleanup.bat para desinstalar el ejemplo OperationsOM y restaurar el ejemplo HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="28a81-183">In this case, run Cleanup.bat to uninstall the OperationsOM sample and restore the HelloWorld sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="28a81-184">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-184">Running This Sample</span></span>  
 <span data-ttu-id="28a81-185">Use el siguiente procedimiento para ejecutar el ejemplo OperationsOM.</span><span class="sxs-lookup"><span data-stu-id="28a81-185">Use the following procedure to run the OperationsOM sample.</span></span>  
  
#### <a name="to-compile-and-run-the-sample"></a><span data-ttu-id="28a81-186">Procedimiento para compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-186">To compile and run the sample</span></span>  
  
1.  <span data-ttu-id="28a81-187">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, seleccione **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="28a81-187">Click **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="28a81-188">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Instancias de host**.</span><span class="sxs-lookup"><span data-stu-id="28a81-188">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="28a81-189">Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="28a81-189">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28a81-190">Puede ser necesario reiniciar la instancia de host BizTalkServerApplication para establecer la base de datos de trabajo correcta para BAM si no ha reiniciado la instancia de host desde la configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="28a81-190">Restarting the BizTalkServerApplication host instance may be necessary to set the correct working database for BAM if you have not restarted the host instance since configuring the product.</span></span>  
  
4.  <span data-ttu-id="28a81-191">En el Explorador de Windows, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="28a81-191">From Windows Explorer, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  <span data-ttu-id="28a81-192">Haga doble clic en el **OperationsOM.sln** archivo de proyecto para cargar en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="28a81-192">Double-click the **OperationsOM.sln** project file to load it into Visual Studio.</span></span>  
  
6.  <span data-ttu-id="28a81-193">Presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="28a81-193">Press F5 to run the sample.</span></span>  
  
     <span data-ttu-id="28a81-194">-O BIEN-</span><span class="sxs-lookup"><span data-stu-id="28a81-194">-- OR --</span></span>  
  
     <span data-ttu-id="28a81-195">En el **generar** menú, haga clic en **volver a generar solución**.</span><span class="sxs-lookup"><span data-stu-id="28a81-195">On the **Build** menu, click **Rebuild Solution**.</span></span> <span data-ttu-id="28a81-196">Una vez completada la compilación, utilice el Explorador de Windows para navegar a `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` y, a continuación, haga doble clic en **OperationsSamples.exe**.</span><span class="sxs-lookup"><span data-stu-id="28a81-196">When the build is complete, use Windows Explorer to navigate to `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` and then double-click **OperationsSamples.exe**.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="28a81-197">Clases o métodos usados en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="28a81-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="28a81-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span><span class="sxs-lookup"><span data-stu-id="28a81-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a81-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="28a81-199">See Also</span></span>  
 [<span data-ttu-id="28a81-200">Admin\OperationsOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="28a81-200">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)