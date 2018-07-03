---
title: HTTPSolicitResponse | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a68e24cee95b25596ad5162223c34a75139c13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981301"
---
# <a name="httpsolicitresponse"></a><span data-ttu-id="406c6-102">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="406c6-102">HTTPSolicitResponse</span></span>
<span data-ttu-id="406c6-103">El ejemplo HTTPSolicitResponse muestra cómo crear una orquestación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que aproveche una aplicación ASP.NET para ayudar a procesar los datos de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="406c6-103">The HTTPSolicitResponse sample demonstrates how to create a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that leverages an ASP.NET application to help process orchestration data.</span></span> <span data-ttu-id="406c6-104">En este ejemplo, la orquestación hace uso de un puerto de solicitud y respuesta para enviar un mensaje a la aplicación ASP.NET y para recuperar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="406c6-104">In this sample, the orchestration makes use of a request/response port to send a message to the ASP.NET application and to retrieve the response.</span></span> <span data-ttu-id="406c6-105">La integración entre la orquestación de BizTalk Server y la aplicación ASP.NET se consigue mediante el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="406c6-105">You achieve the integration between the BizTalk Server orchestration and the ASP.NET application by using the HTTP adapter.</span></span> <span data-ttu-id="406c6-106">Para obtener más información, consulte [adaptador de HTTP](../core/http-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="406c6-106">For more information, see [HTTP Adapter](../core/http-adapter.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="406c6-107">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="406c6-107">What This Sample Does</span></span>  
 <span data-ttu-id="406c6-108">Este ejemplo se compone de una orquestación de BizTalk Server que recibe una solicitud con dos números que se van a multiplicar, y satisface la solicitud mediante la secuencia de pasos siguiente:</span><span class="sxs-lookup"><span data-stu-id="406c6-108">This sample consists of a BizTalk Server orchestration that receives a request containing two numbers to be multiplied, and satisfies that request using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="406c6-109">La orquestación de BizTalk Server recupera un archivo de entrada .xml de una carpeta concreta.</span><span class="sxs-lookup"><span data-stu-id="406c6-109">The BizTalk Server orchestration retrieves an .xml input file from a specific folder.</span></span>  
  
2.  <span data-ttu-id="406c6-110">La orquestación usa una solicitud HTTP para reenviar el XML desde el archivo a una aplicación ASP.NET de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="406c6-110">The orchestration uses an HTTP request to forward the XML from the file to a multiplier ASP.NET application.</span></span>  
  
3.  <span data-ttu-id="406c6-111">La aplicación ASP.NET de multiplicador responde a la solicitud HTTP realizando la multiplicación y devolviendo el resultado como XML en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="406c6-111">The multiplier ASP.NET application responds to the HTTP request by performing the multiplication and returning the result as XML in the HTTP response.</span></span>  
  
4.  <span data-ttu-id="406c6-112">La orquestación recibe el resultado como XML en una respuesta HTTP y escribe dicho resultado en un archivo .xml en una carpeta concreta.</span><span class="sxs-lookup"><span data-stu-id="406c6-112">The orchestration receives the result as XML in an HTTP response, and writes that result to an .xml file in a specific folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="406c6-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="406c6-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="406c6-114">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="406c6-114">\<*Samples Path*\>\AdaptersUsage\HTTPSolicitResponse</span></span>  
  
 <span data-ttu-id="406c6-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="406c6-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="406c6-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="406c6-116">File(s)</span></span>|<span data-ttu-id="406c6-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="406c6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="406c6-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="406c6-118">Cleanup.bat</span></span>|<span data-ttu-id="406c6-119">Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="406c6-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="406c6-120">HttpSolicitResponse.btproj, HttpSolicitResponse.sln</span><span class="sxs-lookup"><span data-stu-id="406c6-120">HttpSolicitResponse.btproj, HttpSolicitResponse.sln</span></span>|<span data-ttu-id="406c6-121">Proporciona archivos del proyecto y de origen para el proyecto de BizTalk que contiene la orquestación que usa la aplicación ASP.NET de multiplicador, los esquemas asociados, etc.</span><span class="sxs-lookup"><span data-stu-id="406c6-121">Provides project and source files for the BizTalk project that contains the orchestration that uses the multiplier ASP.NET application, the associated schemas, and so on.</span></span>|  
|<span data-ttu-id="406c6-122">HttpSolicitResponseBinding.xml</span><span class="sxs-lookup"><span data-stu-id="406c6-122">HttpSolicitResponseBinding.xml</span></span>|<span data-ttu-id="406c6-123">Se proporciona para la instalación automatizada, como el enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="406c6-123">Provides for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="406c6-124">MultiplyRequest.xsd, MultiplyResponse.xsd</span><span class="sxs-lookup"><span data-stu-id="406c6-124">MultiplyRequest.xsd, MultiplyResponse.xsd</span></span>|<span data-ttu-id="406c6-125">Proporciona esquemas para la solicitud de multiplicación y los mensajes XML de respuesta, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="406c6-125">Provides schemas for the multiplication request and response XML messages, respectively.</span></span>|  
|<span data-ttu-id="406c6-126">MultiplyTwoIntegers.odx</span><span class="sxs-lookup"><span data-stu-id="406c6-126">MultiplyTwoIntegers.odx</span></span>|<span data-ttu-id="406c6-127">Proporciona una orquestación de BizTalk Server que recibe un archivo .xml que solicita una operación de multiplicación, reenvía la solicitud a la aplicación ASP.NET de multiplicador y escribe su respuesta en un archivo.</span><span class="sxs-lookup"><span data-stu-id="406c6-127">Provides a BizTalk Server orchestration that receives an .xml file requesting a multiplication operation, forwards the request to the multiplier ASP.NET application, and writes its response to a file.</span></span>|  
|<span data-ttu-id="406c6-128">request_in.xml</span><span class="sxs-lookup"><span data-stu-id="406c6-128">request_in.xml</span></span>|<span data-ttu-id="406c6-129">Archivo de entrada de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="406c6-129">Sample input file.</span></span>|  
|<span data-ttu-id="406c6-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="406c6-130">Setup.bat</span></span>|<span data-ttu-id="406c6-131">Crea e inicializa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="406c6-131">Builds and initializes this sample.</span></span>|  
|<span data-ttu-id="406c6-132">En la carpeta \Multiplier:</span><span class="sxs-lookup"><span data-stu-id="406c6-132">In the \Multiplier folder:</span></span><br /><br /> <span data-ttu-id="406c6-133">Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln</span><span class="sxs-lookup"><span data-stu-id="406c6-133">Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln</span></span>|<span data-ttu-id="406c6-134">Contiene archivos que forman la aplicación ASP.NET que implementa el servicio de multiplicador, incluidos los archivos del proyecto y de la solución, archivos ASPX, archivos de origen de Microsoft Visual C# .NET, etc.</span><span class="sxs-lookup"><span data-stu-id="406c6-134">Contains files that constitute the ASP.NET application that implements the multiplier service, including project and solution files, ASPX files, Microsoft Visual C# .NET source files, and so on.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="406c6-135">Crear e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="406c6-135">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="406c6-136">Utilice el siguiente procedimiento para crear e inicializar el ejemplo HTTPSolicitResponse.</span><span class="sxs-lookup"><span data-stu-id="406c6-136">Use the following procedure to build and initialize the HTTPSolicitResponse sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="406c6-137">Si el nombre de la ubicación de recepción contiene caracteres en mayúscula, el ejemplo no funcionará.</span><span class="sxs-lookup"><span data-stu-id="406c6-137">This sample doesn't work if the name of the receive location contains any uppercase characters.</span></span>  
  
#### <a name="to-build-and-initialize-the-sample"></a><span data-ttu-id="406c6-138">Para crear e iniciar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="406c6-138">To build and initialize the sample</span></span>  
  
1. <span data-ttu-id="406c6-139">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="406c6-139">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="406c6-140">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="406c6-140">\<*Samples Path*\>\AdaptersUsage\HTTPSolicitResponse</span></span>  
  
2. <span data-ttu-id="406c6-141">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="406c6-141">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="406c6-142">Crea las carpetas de entrada y de salida para este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406c6-142">Creates the input and output folders for this sample:</span></span>  
  
      <span data-ttu-id="406c6-143">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput</span><span class="sxs-lookup"><span data-stu-id="406c6-143">\<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput</span></span>  
  
      <span data-ttu-id="406c6-144">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput</span><span class="sxs-lookup"><span data-stu-id="406c6-144">\<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput</span></span>  
  
   - <span data-ttu-id="406c6-145">Compila y configura la aplicación ASP.NET de multiplicador que usa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="406c6-145">Compiles and configures the multiplier ASP.NET application used by this sample.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="406c6-146">Al crear el grupo de aplicaciones en el Administrador de IIS, establezca el **DefaultAppPool** versión de .NET Framework para **.Net Framework v4.0**.</span><span class="sxs-lookup"><span data-stu-id="406c6-146">While creating application pool in IIS Manager, set the **DefaultAppPool** .NET Framework version to **.Net Framework v4.0**.</span></span>  
  
   - <span data-ttu-id="406c6-147">Compila e implementa la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se usa en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="406c6-147">Compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration used in this sample.</span></span>  
  
   - <span data-ttu-id="406c6-148">Crea y enlaza la ubicación y los puertos de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesarios.</span><span class="sxs-lookup"><span data-stu-id="406c6-148">Creates and binds the necessary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and ports.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="406c6-149">Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos:</span><span class="sxs-lookup"><span data-stu-id="406c6-149">This sample displays the following warnings when creating and binding the ports:</span></span>  
  
     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
     > [!NOTE]
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
   - <span data-ttu-id="406c6-150">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="406c6-150">Enables the receive location, and starts the send port.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="406c6-151">La orquestación de este ejemplo usa un puerto bidireccional para la interacción HTTP con la aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="406c6-151">The orchestration in this sample uses a two-way port for the HTTP interaction with the ASP.NET application.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="406c6-152">Debe confirmar que BizTalk no ha informado de ningún error durante el proceso de generación e inicialización antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="406c6-152">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="406c6-153">Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="406c6-153">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="406c6-154">Utilice este par de claves para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="406c6-154">Use this key pair to sign the resulting assemblies.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="406c6-155">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="406c6-155">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="406c6-156">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="406c6-156">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="406c6-157">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="406c6-157">Running the Sample</span></span>  
 <span data-ttu-id="406c6-158">Utilice el siguiente procedimiento para ejecutar el ejemplo HTTPSolicitResponse.</span><span class="sxs-lookup"><span data-stu-id="406c6-158">Use the following procedure to run the HTTPSolicitResponse sample.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="406c6-159">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="406c6-159">To run the sample</span></span>  
  
1.  <span data-ttu-id="406c6-160">Pegue una copia del archivo request_in.xml en la carpeta HttpSolicitResponseInput.</span><span class="sxs-lookup"><span data-stu-id="406c6-160">Paste a copy of the file request_in.xml into the folder HttpSolicitResponseInput.</span></span>  
  
2.  <span data-ttu-id="406c6-161">Observe el archivo .xml creado en la carpeta HttpSolicitResponseOutput.</span><span class="sxs-lookup"><span data-stu-id="406c6-161">Observe the .xml file created in the folder HttpSolicitResponseOutput.</span></span> <span data-ttu-id="406c6-162">El nombre de este archivo .xml se basa en el GUID de Id. del mensaje.</span><span class="sxs-lookup"><span data-stu-id="406c6-162">The name of this .xml file is based on the message ID GUID.</span></span> <span data-ttu-id="406c6-163">Este archivo contiene el resultado de la operación de multiplicación con formato XML.</span><span class="sxs-lookup"><span data-stu-id="406c6-163">This file contains the XML-formatted result of the multiplication operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="406c6-164">Para realizar una operación de multiplicación diferente, puede cambiar los valores de los operandos en el archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="406c6-164">You can change the operand values in the input file to perform a different multiplication operation.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="406c6-165">Comentarios</span><span class="sxs-lookup"><span data-stu-id="406c6-165">Comments</span></span>  
 <span data-ttu-id="406c6-166">Puede adaptar este ejemplo para comunicarse con un sistema externo diferente que muestre una interfaz HTTP.</span><span class="sxs-lookup"><span data-stu-id="406c6-166">You can adapt this sample to communicate with a different external system that exposes an HTTP interface.</span></span>  
  
 <span data-ttu-id="406c6-167">Los archivos MultiplyRequest.xsd y MultiplyResponse.xsd son los esquemas XML que definen el formato de los datos de entrada y salida para la aplicación ASP.NET de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="406c6-167">The files MultiplyRequest.xsd and MultiplyResponse.xsd are the XML schemas that define the format of the input and output data for the multiplier ASP.NET application.</span></span> <span data-ttu-id="406c6-168">La orquestación usa estos archivos para definir los tipos de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="406c6-168">The orchestration uses these files to define the request and response message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406c6-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="406c6-169">See Also</span></span>  
 [<span data-ttu-id="406c6-170">Ejemplos de adaptadores de HTTP</span><span class="sxs-lookup"><span data-stu-id="406c6-170">HTTP Adapter Samples</span></span>](../core/http-adapter-samples.md)