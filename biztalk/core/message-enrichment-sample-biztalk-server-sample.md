---
title: Mensaje Enrichment (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01fa66b344548654a4d2e2e2f2b8700b604ec0e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998509"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a><span data-ttu-id="ece62-102">Message Enrichment (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ece62-102">Message Enrichment Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="ece62-103">El ejemplo Message Enrichment muestra cómo anexar encabezados de intercambio a mensajes de conjunto de transacciones para documentos X12 y EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="ece62-103">The Message Enrichment sample demonstrates how to append interchange headers to transaction-set messages for X12 and EDIFACT documents.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ece62-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-104">What This Sample Does</span></span>  
 <span data-ttu-id="ece62-105">Este ejemplo muestra cómo anexar encabezados UNA, UNB y UNG para EDIFACT, así como encabezados ISA para X12 a conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="ece62-105">This sample demonstrates how to append UNA, UNB, and UNG headers for EDIFACT, and ISA headers for X12, to transaction sets.</span></span> <span data-ttu-id="ece62-106">En concreto, este ejemplo realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ece62-106">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="ece62-107">Al colocar el mensaje de prueba en la carpeta \Message Enrichment\In, el puerto de recepción lo selecciona, lo procesa y lo coloca en el Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ece62-107">When you drop the test message to the \Message Enrichment\In folder, the receive port picks it up, processes it, and drops it in the MessageBox.</span></span>  
  
2.  <span data-ttu-id="ece62-108">MessageEnrichmentOrchestration toma el mensaje de prueba del Cuadro de mensajes porque se suscribe a mensajes basándose en una expresión de filtro establecida en su forma Recepción.</span><span class="sxs-lookup"><span data-stu-id="ece62-108">The MessageEnrichmentOrchestration picks the test message up from the MessageBox, because it subscribes to messages based on a filter expression set on its receive shape.</span></span>  
  
3.  <span data-ttu-id="ece62-109">La orquestación lee los encabezados de intercambio a partir de las propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ece62-109">The orchestration reads the interchange headers from the context properties of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ece62-110">Los encabezados UNA y UNG son opcionales en un mensaje EDIFACT de modo que pueden faltar en las propiedades de contexto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ece62-110">UNA and UNG headers are optional in an EDIFACT message, so can be missing in the context properties of a message.</span></span>  
  
4.  <span data-ttu-id="ece62-111">La orquestación escribe tanto los encabezados de intercambio como el cuerpo del mensaje en un único mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="ece62-111">The orchestration writes both the interchange headers and the message body into a single new message.</span></span>  
  
5.  <span data-ttu-id="ece62-112">La orquestación promociona más propiedades que se establecen en el tipo de correlación ReceivePortNameCorrelationType en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ece62-112">The orchestration promotes additional properties that are set in the ReceivePortNameCorrelationType correlation type onto the message.</span></span> <span data-ttu-id="ece62-113">Éstas permiten que los usuarios de la orquestación seleccionen una lista de las propiedades que necesitan para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="ece62-113">These allow users of the orchestration to select a list of the properties they need for their subscription.</span></span> <span data-ttu-id="ece62-114">Estas propiedades se escriben en una forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="ece62-114">These properties are written in a construct message shape.</span></span> <span data-ttu-id="ece62-115">No todas las propiedades de contexto escritas en el mensaje original se escriben en el mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="ece62-115">Not all context properties that were written to the original message are written to the new message.</span></span>  
  
6.  <span data-ttu-id="ece62-116">La orquestación coloca el mensaje nuevo en el Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ece62-116">The orchestration drops the new message into the MessageBox.</span></span>  
  
7.  <span data-ttu-id="ece62-117">El puerto de envío selecciona el mensaje nuevo y lo envía a través del adaptador de Archivo a la carpeta \Message Enrichment\Out.</span><span class="sxs-lookup"><span data-stu-id="ece62-117">The send port picks up the new message and sends it via the FILE adapter to the \Message Enrichment\Out folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ece62-118">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="ece62-119">Este ejemplo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] carpeta de instalación: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="ece62-119">This sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment.</span></span>  
  
 <span data-ttu-id="ece62-120">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="ece62-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ece62-121">Archivos</span><span class="sxs-lookup"><span data-stu-id="ece62-121">File(s)</span></span>|<span data-ttu-id="ece62-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ece62-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ece62-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="ece62-123">Cleanup.bat</span></span>|<span data-ttu-id="ece62-124">Anula la implementación del escenario de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ece62-124">Undeploys the example scenario.</span></span> <span data-ttu-id="ece62-125">Para que se realice correctamente, no debe haber instancias activas de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ece62-125">In order for it to succeed there must be no active instances of the orchestration.</span></span> <span data-ttu-id="ece62-126">De lo contrario, no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="ece62-126">Otherwise, it will fail.</span></span>|  
|<span data-ttu-id="ece62-127">MessageEnrichment.sln</span><span class="sxs-lookup"><span data-stu-id="ece62-127">MessageEnrichment.sln</span></span>|<span data-ttu-id="ece62-128">Contiene los proyectos MessageEnrichment y MessageEnrichmentLibrary.</span><span class="sxs-lookup"><span data-stu-id="ece62-128">Contains the MessageEnrichment and MessageEnrichmentLibrary projects.</span></span>|  
|<span data-ttu-id="ece62-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ece62-129">Setup.bat</span></span>|<span data-ttu-id="ece62-130">Implementa un escenario de ejemplo que se compone de un puerto de recepción, un puerto de envío y una orquestación.</span><span class="sxs-lookup"><span data-stu-id="ece62-130">Deploys an example scenario that consists of a receive port, send port, and orchestration.</span></span>|  
|<span data-ttu-id="ece62-131">EDIFACT_example.edi</span><span class="sxs-lookup"><span data-stu-id="ece62-131">EDIFACT_example.edi</span></span>|<span data-ttu-id="ece62-132">Mensaje EDIFACT de entrada.</span><span class="sxs-lookup"><span data-stu-id="ece62-132">An input EDIFACT message.</span></span>|  
|<span data-ttu-id="ece62-133">X12_example.edi</span><span class="sxs-lookup"><span data-stu-id="ece62-133">X12_example.edi</span></span>|<span data-ttu-id="ece62-134">Mensaje X12 de entrada.</span><span class="sxs-lookup"><span data-stu-id="ece62-134">An input X12 message.</span></span>|  
|<span data-ttu-id="ece62-135">MessageEnrichment.btproj</span><span class="sxs-lookup"><span data-stu-id="ece62-135">MessageEnrichment.btproj</span></span>|<span data-ttu-id="ece62-136">Proyecto que contiene las orquestaciones y los esquemas de MessageEnrichment.</span><span class="sxs-lookup"><span data-stu-id="ece62-136">The project containing the MessageEnrichment orchestrations and schemas.</span></span>|  
|<span data-ttu-id="ece62-137">MessageEnrichmentBindings.xml</span><span class="sxs-lookup"><span data-stu-id="ece62-137">MessageEnrichmentBindings.xml</span></span>|<span data-ttu-id="ece62-138">Archivo que contiene enlaces para la orquestación, los puertos y las entidades.</span><span class="sxs-lookup"><span data-stu-id="ece62-138">The file containing bindings for the orchestration, the ports, and the parties.</span></span>|  
|<span data-ttu-id="ece62-139">MessageEnrichmentOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="ece62-139">MessageEnrichmentOrchestration.odx</span></span>|<span data-ttu-id="ece62-140">Orquestación que anexa los encabezados al mensaje.</span><span class="sxs-lookup"><span data-stu-id="ece62-140">The orchestration that appends the headers to the message.</span></span>|  
|<span data-ttu-id="ece62-141">MessageEnrichmentOrchestration.odx.cs</span><span class="sxs-lookup"><span data-stu-id="ece62-141">MessageEnrichmentOrchestration.odx.cs</span></span>|<span data-ttu-id="ece62-142">Código de la orquestación que anexa los encabezados al mensaje.</span><span class="sxs-lookup"><span data-stu-id="ece62-142">The orchestration code that appends the headers to the message.</span></span>|  
|<span data-ttu-id="ece62-143">EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="ece62-143">EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="ece62-144">Esquema EDIFACT para el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="ece62-144">The EDIFACT schema for the input message.</span></span>|  
|<span data-ttu-id="ece62-145">Enriched_EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="ece62-145">Enriched_EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="ece62-146">Esquema EDIFACT para el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="ece62-146">The EDIFACT schema for the output message.</span></span>|  
|<span data-ttu-id="ece62-147">X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="ece62-147">X12_00401_864.xsd</span></span>|<span data-ttu-id="ece62-148">Esquema X12 para el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="ece62-148">The X12 schema for the input message.</span></span>|  
|<span data-ttu-id="ece62-149">Enriched_X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="ece62-149">Enriched_X12_00401_864.xsd</span></span>|<span data-ttu-id="ece62-150">Esquema X12 para el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="ece62-150">The X12 schema for the output message.</span></span>|  
|<span data-ttu-id="ece62-151">Headers.xsd</span><span class="sxs-lookup"><span data-stu-id="ece62-151">Headers.xsd</span></span>|<span data-ttu-id="ece62-152">Esquemas para los encabezados agregados a los mensajes de entrada.</span><span class="sxs-lookup"><span data-stu-id="ece62-152">The schemas for the headers added to the input messages.</span></span>|  
|<span data-ttu-id="ece62-153">MessageEnrichmentLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="ece62-153">MessageEnrichmentLibrary.csproj</span></span>|<span data-ttu-id="ece62-154">Proyecto que contiene los archivos Headers.cs, OrchestrationUtilities.cs y ParseHeaders.cs.</span><span class="sxs-lookup"><span data-stu-id="ece62-154">The project containing the Headers.cs, OrchestrationUtilities.cs, and ParseHeaders.cs files.</span></span>|  
|<span data-ttu-id="ece62-155">Headers.cs</span><span class="sxs-lookup"><span data-stu-id="ece62-155">Headers.cs</span></span>|<span data-ttu-id="ece62-156">Incluye las clases que representan los datos de los encabezados.</span><span class="sxs-lookup"><span data-stu-id="ece62-156">Includes classes representing headers data.</span></span>|  
|<span data-ttu-id="ece62-157">OrchestrationUtilities.cs</span><span class="sxs-lookup"><span data-stu-id="ece62-157">OrchestrationUtilities.cs</span></span>|<span data-ttu-id="ece62-158">Incluye métodos de utilidad empleados por la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ece62-158">Includes utility methods used by orchestration.</span></span>|  
|<span data-ttu-id="ece62-159">ParseHeaders.cs</span><span class="sxs-lookup"><span data-stu-id="ece62-159">ParseHeaders.cs</span></span>|<span data-ttu-id="ece62-160">Incluye los valores predeterminados de UNA que se usan en los mensajes nuevos.</span><span class="sxs-lookup"><span data-stu-id="ece62-160">Includes the default values for UNA that are used in the new messages.</span></span> <span data-ttu-id="ece62-161">Estos valores se toman del método SerializeEDIFACTHeaders en ParseHeaders.cs.</span><span class="sxs-lookup"><span data-stu-id="ece62-161">These values are taken from the SerializeEDIFACTHeaders method in ParseHeaders.cs.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="ece62-162">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-162">How to Use This Sample</span></span>  
 <span data-ttu-id="ece62-163">Use este ejemplo como ejemplo de trabajo de las acciones necesarias para anexar encabezados de intercambio a mensajes de conjuntos de transacciones EDI.</span><span class="sxs-lookup"><span data-stu-id="ece62-163">Use this sample as a working example of the actions required to append interchange headers to EDI transaction-set messages.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="ece62-164">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-164">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="ece62-165">Para crear e inicializar el ejemplo Message Enrichment, deberá crear e implementar el proyecto de BizTalk para este ejemplo, configurar la ubicación y el puerto de recepción, así como configurar dos puertos de envío diferentes.</span><span class="sxs-lookup"><span data-stu-id="ece62-165">To build and initialize the Message Enrichment sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="ece62-166">Para crear e implementar el proyecto de BizTalk para este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-166">To build and deploy the BizTalk project for this sample</span></span>  
  
1. <span data-ttu-id="ece62-167">Con Notepad.Exe, abra [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span><span class="sxs-lookup"><span data-stu-id="ece62-167">Using Notepad.Exe, open [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span></span>  
   <span data-ttu-id="ece62-168">MessageEnrichment\properties\AssemblyInfo.cs y agregue la siguiente línea en la parte inferior del archivo:</span><span class="sxs-lookup"><span data-stu-id="ece62-168">MessageEnrichment\properties\AssemblyInfo.cs and add the following line at the bottom of the file:</span></span>  
  
   ```  
   [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
   ```  
  
2. <span data-ttu-id="ece62-169">Guarde el archivo AssemblyInfo.cs modificado y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="ece62-169">Save the modified AssemblyInfo.cs file and then exit Notepad.</span></span>  
  
3. <span data-ttu-id="ece62-170">En una ventana de comandos, vaya a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="ece62-170">In a command window, move to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ece62-171">SDK\Samples\EDI\Message Enrichment</span><span class="sxs-lookup"><span data-stu-id="ece62-171">SDK\Samples\EDI\Message Enrichment</span></span>  
  
4. <span data-ttu-id="ece62-172">Ejecute **Setup.bat**, que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ece62-172">Run **Setup.bat**, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="ece62-173">Crea la recepción (**en**) y enviar (**out**) para este ejemplo en la carpeta \MessageEnrichment.</span><span class="sxs-lookup"><span data-stu-id="ece62-173">Creates the receive (**in**) and send (**out**) folders for this sample in the \MessageEnrichment folder.</span></span>  
  
   -   <span data-ttu-id="ece62-174">Escribe un par de claves en MessageEnrichmentLibrary\testkey.snk</span><span class="sxs-lookup"><span data-stu-id="ece62-174">Writes a key pair to MessageEnrichmentLibrary\testkey.snk</span></span>  
  
   -   <span data-ttu-id="ece62-175">Crea e implementa el proyecto MessageEnrichmentLibrary.btproj.</span><span class="sxs-lookup"><span data-stu-id="ece62-175">Builds and deploys the MessageEnrichmentLibrary.btproj project.</span></span>  
  
   -   <span data-ttu-id="ece62-176">Crea e implementa el proyecto MessageEnrichment.btproj.</span><span class="sxs-lookup"><span data-stu-id="ece62-176">Builds and deploys the MessageEnrichment.btproj project.</span></span>  
  
   -   <span data-ttu-id="ece62-177">Lee la información de enlaces de MessageEnrichmentBindings.xml.</span><span class="sxs-lookup"><span data-stu-id="ece62-177">Reads binding information in MessageEnrichmentBindings.xml.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="ece62-178">El enlace para este proyecto requiere que el host de BizTalk está marcado como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="ece62-178">The binding for this project requires that the BizTalk host is marked as Authentication Trusted.</span></span>  <span data-ttu-id="ece62-179">Para usar esta opción con un host que no sea de confianza, modifique el archivo MessageEnrichmentBindings.xml y cambie las entradas HostTrusted=”true” a HostTrusted=”false”.</span><span class="sxs-lookup"><span data-stu-id="ece62-179">In order to use this with a host that is not trusted, modify the MessageEnrichmentBindings.xml and change the HostTrusted=”true” entries to HostTrusted=”false”.</span></span>  
  
   -   <span data-ttu-id="ece62-180">Actualiza los enlaces de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ece62-180">Updates orchestration bindings.</span></span>  
  
   -   <span data-ttu-id="ece62-181">Actualiza los puertos de envío, grupos de puertos de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="ece62-181">Updates send ports, send port groups, and receive ports.</span></span>  
  
   -   <span data-ttu-id="ece62-182">Actualiza entidades e inscripciones.</span><span class="sxs-lookup"><span data-stu-id="ece62-182">Updates parties and enlistments.</span></span>  
  
   -   <span data-ttu-id="ece62-183">Inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ece62-183">Starts the send port.</span></span>  
  
   -   <span data-ttu-id="ece62-184">Habilita la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="ece62-184">Enables the receive location.</span></span>  
  
   -   <span data-ttu-id="ece62-185">Da de alta e inicia la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ece62-185">Enlists and starts the orchestration.</span></span>  
  
   <span data-ttu-id="ece62-186">Ahora, el servidor BizTalk Server estará preparado para trabajar con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ece62-186">BizTalk Server is ready now to work with this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="ece62-187">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-187">Running This Sample</span></span>  
 <span data-ttu-id="ece62-188">Utilice el siguiente procedimiento para ejecutar el ejemplo Message Enrichment.</span><span class="sxs-lookup"><span data-stu-id="ece62-188">Use the following procedure to run the Message Enrichment sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="ece62-189">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-189">To run this sample</span></span>  
  
1.  <span data-ttu-id="ece62-190">Copie el archivo EDIFACT_examples.edi de la carpeta \MessageEnrichment\Instances en la carpeta \MessageEnrichment\In.</span><span class="sxs-lookup"><span data-stu-id="ece62-190">Copy the EDIFACT_examples.edi file from the \MessageEnrichment\Instances folder into the \MessageEnrichment\In folder.</span></span>  
  
2.  <span data-ttu-id="ece62-191">Verifique si los archivos EDIFACT_examples.edi desaparecen de la carpeta \MessageEnrichment\In y aparecen en la carpeta \MessageEnrichment\Out.</span><span class="sxs-lookup"><span data-stu-id="ece62-191">Verify that the EDIFACT_examples.edi files disappears from the \MessageEnrichment\In folder, and appears in the \MessageEnrichment\Out folder.</span></span>  
  
3.  <span data-ttu-id="ece62-192">Abra el archivo de la carpeta \MessageEnrichment\Out.</span><span class="sxs-lookup"><span data-stu-id="ece62-192">Open the file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="ece62-193">Verifique que se trata de una representación XML del archivo EDIFACT_examples.edi de la carpeta \MessageEnrichment\Instances, y que su contenido es idéntico al del archivo EDIFACT_examples.edi, excepto por el hecho de que el archivo de salida tiene encabezados UNA, UNB y UNG de EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="ece62-193">Verify that it is an XML representation of the EDIFACT_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the EDIFACT_examples.edi file, with the exception that the output file has EDIFACT UNA, UNB, and UNG headers.</span></span>  
  
4.  <span data-ttu-id="ece62-194">Repita los pasos 1 y 2 con el archivo X12_examples.edi de la carpeta \MessageEnrichment\Instances.</span><span class="sxs-lookup"><span data-stu-id="ece62-194">Repeat steps 1 and 2 with the X12_examples.edi file from the \MessageEnrichment\Instances folder.</span></span>  
  
5.  <span data-ttu-id="ece62-195">Abra el archivo nuevo de la carpeta \MessageEnrichment\Out.</span><span class="sxs-lookup"><span data-stu-id="ece62-195">Open the new file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="ece62-196">Verifique que se trata de una representación XML del archivo X12_examples.edi de la carpeta \MessageEnrichment\Instances, y que su contenido es idéntico al del archivo X12_examples.edi, excepto por el hecho de que el archivo de salida tiene encabezados ISA de X12.</span><span class="sxs-lookup"><span data-stu-id="ece62-196">Verify that it is an XML representation of the X12_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the X12_examples.edi file, with the exception that the output file has X12 ISA headers.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="ece62-197">Clases o métodos usados en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece62-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="ece62-198">None</span><span class="sxs-lookup"><span data-stu-id="ece62-198">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece62-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="ece62-199">See Also</span></span>  
 [<span data-ttu-id="ece62-200">EDI y AS2 (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ece62-200">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)