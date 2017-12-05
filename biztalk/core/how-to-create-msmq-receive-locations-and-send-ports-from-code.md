---
title: "Crear MSMQ ubicaciones de recepción y puertos de envío de código | Documentos de Microsoft"
description: "Crear mediante programación MSMQ ubicaciones de recepción y puertos de envío en el servidor BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebb4119-deeb-4287-aa65-7597ff0cc435
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f00a0bfe14eeb7d4205973b3fef96e23026616
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a><span data-ttu-id="445c3-103">Crear ubicaciones de recepción de MSMQ y puertos de envío mediante programación</span><span class="sxs-lookup"><span data-stu-id="445c3-103">Create MSMQ Receive Locations and Send Ports programmatically</span></span>
<span data-ttu-id="445c3-104">En este tema se explica cómo usar WMI para crear un puerto o una ubicación para el adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="445c3-104">This topic explains how to use WMI to create a port or location for the MSMQ adapter.</span></span>  
  
 <span data-ttu-id="445c3-105">Para obtener más información, consulte **crear una ubicación de recepción con una fecha y hora programación configuración mediante WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="445c3-105">For more information, see **Creating a Receive Location with a Datetime Schedule Configuration Using WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="setting-property-values"></a><span data-ttu-id="445c3-106">Configurar valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="445c3-106">Setting Property Values</span></span>  
 <span data-ttu-id="445c3-107">El proceso de creación un puerto o una ubicación es siempre el mismo:</span><span class="sxs-lookup"><span data-stu-id="445c3-107">The process of creating a port or location is always the same:</span></span>  
  
1.  <span data-ttu-id="445c3-108">Crear un objeto del tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="445c3-108">Create an object of the right type.</span></span>  
  
2.  <span data-ttu-id="445c3-109">Establecer el valor de propiedades en el objeto.</span><span class="sxs-lookup"><span data-stu-id="445c3-109">Set the value of properties on the object.</span></span>  
  
3.  <span data-ttu-id="445c3-110">Confirmar los valores del objeto en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="445c3-110">Commit the object values to the database.</span></span>  
  
 <span data-ttu-id="445c3-111">Todos los adaptadores tienen determinadas propiedades, como **HostName**en común.</span><span class="sxs-lookup"><span data-stu-id="445c3-111">All adapters have certain properties, such as **HostName**, in common.</span></span> <span data-ttu-id="445c3-112">Establezca estas propiedades comunes mediante su asignación directa en el objeto.</span><span class="sxs-lookup"><span data-stu-id="445c3-112">You set these common properties by directly assigning them to the object.</span></span> <span data-ttu-id="445c3-113">En el siguiente código C# se muestra un caso típico:</span><span class="sxs-lookup"><span data-stu-id="445c3-113">The following C# code shows a typical case:</span></span>  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 <span data-ttu-id="445c3-114">Asigne los valores a las propiedades que no comparten todos los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="445c3-114">You assign values to properties that not all adapters share.</span></span> <span data-ttu-id="445c3-115">Cree un documento XML en una cadena y asigne dicha cadena a la propiedad CustomCfg.</span><span class="sxs-lookup"><span data-stu-id="445c3-115">You create an XML document in a string and assign that string to the CustomCfg property.</span></span> <span data-ttu-id="445c3-116">En el siguiente código C# se muestra un caso típico para un adaptador de archivos:</span><span class="sxs-lookup"><span data-stu-id="445c3-116">The following C# code shows a typical case for a FILE adapter:</span></span>  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 <span data-ttu-id="445c3-117">Los nombres de las etiquetas del elemento CustomProps son nombres internos que el adaptador utiliza para las propiedades.</span><span class="sxs-lookup"><span data-stu-id="445c3-117">The names of the tags in the CustomProps element are the internal names that the adapter uses for the properties.</span></span>  
  
 <span data-ttu-id="445c3-118">El adaptador de MSMQ tiene una única etiqueta, AdapterConfig, dentro de la etiqueta CustomProps.</span><span class="sxs-lookup"><span data-stu-id="445c3-118">The MSMQ adapter has a single tag, AdapterConfig, inside the CustomProps tag.</span></span> <span data-ttu-id="445c3-119">La etiquete AdapterConfig contiene una cadena de etiquetas XML para los valores de propiedad personalizados incluidos en una etiqueta Config.</span><span class="sxs-lookup"><span data-stu-id="445c3-119">The AdapterConfig tag contains a string of XML tags for the custom property values enclosed in a Config tag.</span></span> <span data-ttu-id="445c3-120">Sin embargo, las etiquetas están incluidas: "&lt;"reemplaza"\<"y"&gt;"reemplaza"\>".</span><span class="sxs-lookup"><span data-stu-id="445c3-120">However, the tags are encoded: "&lt;" replaces "\<" and "&gt;" replaces "\>".</span></span> <span data-ttu-id="445c3-121">Por ejemplo, el XML de un subconjunto del adaptador de propiedades de MSMQ puede aparecer de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="445c3-121">For example, the XML for a subset of the adapter for MSMQ properties might appear as follows:</span></span>  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 <span data-ttu-id="445c3-122">Tenga en cuenta que la **vt** no se utiliza el atributo.</span><span class="sxs-lookup"><span data-stu-id="445c3-122">Notice that the **vt** attribute is not used.</span></span> <span data-ttu-id="445c3-123">La cadena asignada a la **CustomCfg** propiedad como se indica a continuación aparece después de la codificación:</span><span class="sxs-lookup"><span data-stu-id="445c3-123">The string assigned to the **CustomCfg** property appears as follows after encoding:</span></span>  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a><span data-ttu-id="445c3-124">Nombres de propiedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="445c3-124">Custom Property Names</span></span>  
 <span data-ttu-id="445c3-125">La tabla siguiente describe los nombres internos del adaptador de MSMQ **enviar** propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="445c3-125">The following table describes the internal names of the MSMQ adapter **Send** custom properties.</span></span>  
  
|<span data-ttu-id="445c3-126">**Enviar el nombre de propiedad personalizada**</span><span class="sxs-lookup"><span data-stu-id="445c3-126">**Send custom property name**</span></span>|<span data-ttu-id="445c3-127">**Nombre para mostrar**</span><span class="sxs-lookup"><span data-stu-id="445c3-127">**Display name**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="445c3-128">acknowledgeType</span><span class="sxs-lookup"><span data-stu-id="445c3-128">acknowledgeType</span></span>|<span data-ttu-id="445c3-129">Tipo de confirmación</span><span class="sxs-lookup"><span data-stu-id="445c3-129">Acknowledgement Type</span></span>|  
|<span data-ttu-id="445c3-130">administrationQueue</span><span class="sxs-lookup"><span data-stu-id="445c3-130">administrationQueue</span></span>|<span data-ttu-id="445c3-131">Cola de administración</span><span class="sxs-lookup"><span data-stu-id="445c3-131">Administration Queue</span></span>|  
|<span data-ttu-id="445c3-132">certificado</span><span class="sxs-lookup"><span data-stu-id="445c3-132">certificate</span></span>|<span data-ttu-id="445c3-133">Huella digital de certificado</span><span class="sxs-lookup"><span data-stu-id="445c3-133">Certificate Thumbprint</span></span>|  
|<span data-ttu-id="445c3-134">encryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="445c3-134">encryptionAlgorithm</span></span>|<span data-ttu-id="445c3-135">Algoritmo de cifrado</span><span class="sxs-lookup"><span data-stu-id="445c3-135">Encryption Algorithm</span></span>|  
|<span data-ttu-id="445c3-136">maximumMessageSize</span><span class="sxs-lookup"><span data-stu-id="445c3-136">maximumMessageSize</span></span>|<span data-ttu-id="445c3-137">Tamaño máximo de mensaje (en KB)</span><span class="sxs-lookup"><span data-stu-id="445c3-137">Maximum Message Size (in KB)</span></span>|  
|<span data-ttu-id="445c3-138">password</span><span class="sxs-lookup"><span data-stu-id="445c3-138">password</span></span>|<span data-ttu-id="445c3-139">Contraseña</span><span class="sxs-lookup"><span data-stu-id="445c3-139">Password</span></span>|  
|<span data-ttu-id="445c3-140">priority</span><span class="sxs-lookup"><span data-stu-id="445c3-140">priority</span></span>|<span data-ttu-id="445c3-141">Prioridad del mensaje</span><span class="sxs-lookup"><span data-stu-id="445c3-141">Message Priority</span></span>|  
|<span data-ttu-id="445c3-142">cola</span><span class="sxs-lookup"><span data-stu-id="445c3-142">queue</span></span>|<span data-ttu-id="445c3-143">Cola de destino</span><span class="sxs-lookup"><span data-stu-id="445c3-143">Destination Queue</span></span>|  
|<span data-ttu-id="445c3-144">recuperable</span><span class="sxs-lookup"><span data-stu-id="445c3-144">recoverable</span></span>|<span data-ttu-id="445c3-145">Recoverable</span><span class="sxs-lookup"><span data-stu-id="445c3-145">Recoverable</span></span>|  
|<span data-ttu-id="445c3-146">segmentationSupport</span><span class="sxs-lookup"><span data-stu-id="445c3-146">segmentationSupport</span></span>|<span data-ttu-id="445c3-147">Admitir segmentación</span><span class="sxs-lookup"><span data-stu-id="445c3-147">Support Segmentation</span></span>|  
|<span data-ttu-id="445c3-148">sendBatchSize</span><span class="sxs-lookup"><span data-stu-id="445c3-148">sendBatchSize</span></span>|<span data-ttu-id="445c3-149">Tamaño del lote</span><span class="sxs-lookup"><span data-stu-id="445c3-149">Batch Size</span></span>|  
|<span data-ttu-id="445c3-150">sendQueueName</span><span class="sxs-lookup"><span data-stu-id="445c3-150">sendQueueName</span></span>|<span data-ttu-id="445c3-151">Cola de destino</span><span class="sxs-lookup"><span data-stu-id="445c3-151">Destination Queue</span></span>|  
|<span data-ttu-id="445c3-152">timeOut</span><span class="sxs-lookup"><span data-stu-id="445c3-152">timeOut</span></span>|<span data-ttu-id="445c3-153">Timeout</span><span class="sxs-lookup"><span data-stu-id="445c3-153">Timeout</span></span>|  
|<span data-ttu-id="445c3-154">timeOutUnits</span><span class="sxs-lookup"><span data-stu-id="445c3-154">timeOutUnits</span></span>|<span data-ttu-id="445c3-155">Unidad de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="445c3-155">Timeout Unit</span></span>|  
|<span data-ttu-id="445c3-156">transaccional</span><span class="sxs-lookup"><span data-stu-id="445c3-156">transactional</span></span>|<span data-ttu-id="445c3-157">Transaccional</span><span class="sxs-lookup"><span data-stu-id="445c3-157">Transactional</span></span>|  
|<span data-ttu-id="445c3-158">useAuthentication</span><span class="sxs-lookup"><span data-stu-id="445c3-158">useAuthentication</span></span>|<span data-ttu-id="445c3-159">Utilizar autenticación</span><span class="sxs-lookup"><span data-stu-id="445c3-159">Use Authentication</span></span>|  
|<span data-ttu-id="445c3-160">useDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="445c3-160">useDeadLetterQueue</span></span>|<span data-ttu-id="445c3-161">Usar cola de mensajes con problemas de entrega</span><span class="sxs-lookup"><span data-stu-id="445c3-161">Use Dead Letter Queue</span></span>|  
|<span data-ttu-id="445c3-162">useJournalQueue</span><span class="sxs-lookup"><span data-stu-id="445c3-162">useJournalQueue</span></span>|<span data-ttu-id="445c3-163">Usar cola de diario</span><span class="sxs-lookup"><span data-stu-id="445c3-163">Use Journal Queue</span></span>|  
|<span data-ttu-id="445c3-164">userName</span><span class="sxs-lookup"><span data-stu-id="445c3-164">userName</span></span>|<span data-ttu-id="445c3-165">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="445c3-165">User Name</span></span>|  
  
 <span data-ttu-id="445c3-166">La tabla siguiente describe los nombres internos del adaptador de MSMQ **recepción** propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="445c3-166">The following table describes the internal names of the MSMQ adapter **Receive** custom properties.</span></span>  
  
|<span data-ttu-id="445c3-167">**Recibe el nombre de propiedad personalizada**</span><span class="sxs-lookup"><span data-stu-id="445c3-167">**Receive custom property name**</span></span>|<span data-ttu-id="445c3-168">**Nombre para mostrar**</span><span class="sxs-lookup"><span data-stu-id="445c3-168">**Display name**</span></span>|  
|--------------------------------------|----------------------|  
|<span data-ttu-id="445c3-169">batchSize</span><span class="sxs-lookup"><span data-stu-id="445c3-169">batchSize</span></span>|<span data-ttu-id="445c3-170">Tamaño del lote</span><span class="sxs-lookup"><span data-stu-id="445c3-170">Batch Size</span></span>|  
|<span data-ttu-id="445c3-171">Contraseña</span><span class="sxs-lookup"><span data-stu-id="445c3-171">Password</span></span>|<span data-ttu-id="445c3-172">Contraseña</span><span class="sxs-lookup"><span data-stu-id="445c3-172">Password</span></span>|  
|<span data-ttu-id="445c3-173">Cola</span><span class="sxs-lookup"><span data-stu-id="445c3-173">Queue</span></span>|<span data-ttu-id="445c3-174">Cola</span><span class="sxs-lookup"><span data-stu-id="445c3-174">Queue</span></span>|  
|<span data-ttu-id="445c3-175">serialProcessing</span><span class="sxs-lookup"><span data-stu-id="445c3-175">serialProcessing</span></span>|<span data-ttu-id="445c3-176">Procesamiento en serie</span><span class="sxs-lookup"><span data-stu-id="445c3-176">Serial Processing</span></span>|  
|<span data-ttu-id="445c3-177">Transaccional</span><span class="sxs-lookup"><span data-stu-id="445c3-177">Transactional</span></span>|<span data-ttu-id="445c3-178">Transaccional</span><span class="sxs-lookup"><span data-stu-id="445c3-178">Transactional</span></span>|  
|<span data-ttu-id="445c3-179">userName</span><span class="sxs-lookup"><span data-stu-id="445c3-179">userName</span></span>|<span data-ttu-id="445c3-180">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="445c3-180">User Name</span></span>|  
  
## <a name="sample-code"></a><span data-ttu-id="445c3-181">Código muestra</span><span class="sxs-lookup"><span data-stu-id="445c3-181">Sample Code</span></span>  
 <span data-ttu-id="445c3-182">El siguiente programa C# crea una ubicación de recepción única para el adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="445c3-182">The following C# program creates a single receive location for the MSMQ adapter.</span></span> <span data-ttu-id="445c3-183">Se supone que el puerto de recepción, ReceivePort1, sale y usa una función auxiliar para codificar y aplicar el formato a las propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="445c3-183">It assumes that the receive port, ReceivePort1, exists and uses a helper function to encode and format the custom properties.</span></span>  
  
```  
using System;  
using System.Management;  
using System.Text;  
  
namespace CreateReceive  
{  
    ///   
    /// Program to create a receive location.  
    ///   
    class CreateReceive  
    {  
        /// The main entry point for the application.  
  
        [STAThread]  
        static void Main()  
        {  
            // Custom properties & values  
            string cfg =   
                    @"<queue>FORMATNAME:DIRECT=OS:MYMACHINE02\PRIVATE$\QUEUE2</queue>"  
                    + @"<batchSize>40</batchSize>"  
                    + @"<transactional>true</transactional>"  
                    + @"<serialProcessing>false</serialProcessing>";  
  
            CreateReceiveLocation (  
                    "Code Created Location",  
                    "ReceivePort1",  
                    "MSMQ",  
                    "BizTalkServerApplication",  
                    EncodeCustomProps(cfg),  // Encode the custom props  
                    "Microsoft.BizTalk.DefaultPipelines.PassThruReceive,"   
                            + " Microsoft.BizTalk.DefaultPipelines,"   
                            + " Version=3.0.1.0, Culture=neutral,"   
                            + " PublicKeyToken=31bf3856ad364e35",  
                    @"FORMATNAME:DIRECT=OS:MYMACHINE\PRIVATE$\QUEUE2"  
                );  
  
        }  
  
        static string EncodeCustomProps (string cp) {  
  
            // Enclose the properties and values in a Config> tag.  
            StringBuilder tmp = new StringBuilder( @"<Config>" + cp + @"</Config>");  
  
            // Encode the string  
            tmp = tmp.Replace("<","<");  
            tmp = tmp.Replace(">",">");  
  
            return (  
                // Enclose the encoded string with necessary tags  
                "<CustomProps><AdapterConfig vt=\"8\">"  
                + tmp.ToString()   
                + "</AdapterConfig></CustomProps>");  
  
        }  
  
        static void CreateReceiveLocation (  
            string name,            // Location name  
            string port,            // Receive port, already exists  
            string adapterName,     // The transport type  
            string hostName,        // BTS host  
            string customCfg,       // Encoded custom properties  
            string pipeline,        // Full specification of pipeline  
            string inboundTransport)// Inbound transport url  
        {  
            try   
            {  
                // Create options to store options in management object  
                PutOptions options = new PutOptions();  
                options.Type = PutType.CreateOnly;  
  
                // Create a management object  
                // Get the class  
                ManagementClass objReceiveLocationClass =   
                           new ManagementClass(  
                               "root\\MicrosoftBizTalkServer",   
                               "MSBTS_ReceiveLocation",   
                               null);  
                // Create an instance of the member of the class  
                ManagementObject objReceiveLocation =  
                          objReceiveLocationClass.CreateInstance();  
  
                // Fill in the properties  
                objReceiveLocation["Name"] = name;  
                objReceiveLocation["ReceivePortName"] = port;  
                objReceiveLocation["AdapterName"] = adapterName;  
                objReceiveLocation["HostName"] = hostName;  
                objReceiveLocation["PipelineName"] = pipeline;  
                objReceiveLocation["CustomCfg"] = customCfg;  
                objReceiveLocation["IsDisabled"] = true;  
                objReceiveLocation["InBoundTransportURL"] = inboundTransport;  
  
                // Put the options -- creates the receive location  
                objReceiveLocation.Put(options);  
            }  
            catch (Exception excep)  
            {  
                System.Console.WriteLine("Create Receive Location ({0}) failed - {1}",  
                                                name, excep.Message);  
            }  
        }  
    }  
}  
```