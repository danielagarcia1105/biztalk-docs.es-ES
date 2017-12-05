---
title: Un adaptador con el SDK de adaptador LOB de WCF de seguimiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a4f4758-3e3e-48c4-b4cf-414c2b05d539
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca4b68f23f791de3ecd68bc69b85c2908b6d7a0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="592c2-102">Seguimiento de un adaptador con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="592c2-102">Trace an adapter with the WCF LOB Adapter SDK</span></span>
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="592c2-103">el seguimiento se basa en Systems.Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="592c2-103"> tracing is built on top of Systems.Diagnostics.</span></span> <span data-ttu-id="592c2-104">Usar Microsoft.ServiceModel.Channels origen de seguimiento para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="592c2-104">You use Microsoft.ServiceModel.Channels trace source for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] runtime.</span></span>  <span data-ttu-id="592c2-105">Usar origen de seguimiento Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse para [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="592c2-105">You use Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse trace source for [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="592c2-106">Los seguimientos de WCF se escriben en el origen denominado System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="592c2-106">WCF traces are written to the source named System.ServiceModel.</span></span>  
  
 <span data-ttu-id="592c2-107">El programador de adaptadores puede proporcionar un nombre de origen de seguimiento para el adaptador utiliza la clase Microsoft.ServiceModel.Channels.Common.AdapterTrace.</span><span class="sxs-lookup"><span data-stu-id="592c2-107">The adapter developer can provide a trace source name for the adapter using Microsoft.ServiceModel.Channels.Common.AdapterTrace class.</span></span> <span data-ttu-id="592c2-108">El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera una clase de contenedor de seguimiento que puede usarse por el desarrollador de adaptadores para proporcionar la instrumentación en el código del adaptador.</span><span class="sxs-lookup"><span data-stu-id="592c2-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] generates a trace wrapper class that can be used by the adapter developer to provide instrumentation in the adapter code.</span></span>  
  
 <span data-ttu-id="592c2-109">Para obtener información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx).</span><span class="sxs-lookup"><span data-stu-id="592c2-109">For information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>
  
 <span data-ttu-id="592c2-110">Para obtener información acerca del análisis de seguimientos de WCF, vea [herramienta Service Trace Viewer (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx).</span><span class="sxs-lookup"><span data-stu-id="592c2-110">For information about analyzing traces in WCF, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx).</span></span> 
  
## <a name="sample-trace-wrapper-utility-class"></a><span data-ttu-id="592c2-111">Clase de utilidad de contenedor de seguimiento de ejemplo</span><span class="sxs-lookup"><span data-stu-id="592c2-111">Sample Trace Wrapper Utility Class</span></span>  
  
```  
public class EchoAdapterUtilities  
{  
    static AdapterTrace trace = new AdapterTrace("Microsoft.Adapters.Samples.Echo.EchoAdapter");  
  
    /// <summary>  
    /// Gets the AdapterTrace  
    /// </summary>  
    public static AdapterTrace Trace  
    {  
        get  
        {  
            return trace;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="592c2-112">La clase de utilidad anterior, a continuación, ser usada por el programador de adaptadores en todo el código de adaptador para proporcionar datos de instrumentación para los consumidores de adaptador.</span><span class="sxs-lookup"><span data-stu-id="592c2-112">The previous utility class can then be used by the adapter developer throughout the adapter code to provide instrumentation data for the adapter consumers.</span></span>  
  
 <span data-ttu-id="592c2-113">EchoAdapterUtilities.Trace.Trace (System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Conexión abre correctamente!");</span><span class="sxs-lookup"><span data-stu-id="592c2-113">EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully opened!");</span></span>  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a><span data-ttu-id="592c2-114">Habilitar el seguimiento para el adaptador y la ejecución del SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="592c2-114">Enable Tracing for the Adapter and WCF LOB Adapter SDK Runtime</span></span>  
 <span data-ttu-id="592c2-115">Puede habilitar el seguimiento que se proporcionan en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] agregando la siguiente sección en el archivo app.config de la aplicación que utiliza el adaptador.</span><span class="sxs-lookup"><span data-stu-id="592c2-115">You can enable tracing provided in the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] by adding the following section in the app.config file of the application using the adapter.</span></span>  
  
```  
<system.diagnostics>  
  <sources>  
    <source name="Microsoft.Adapters.Samples.Echo.EchoAdapter" switchValue="Verbose">  
      <listeners>  
        <add name="xmlTrace" />  
      </listeners>  
    </source>  
    <source name="Microsoft.ServiceModel.Channels" switchValue="Verbose">  
      <listeners>  
        <add name="xmlTrace" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\TestEchoAdapter_Browse.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="592c2-116">Puede utilizar el elemento Agregar para especificar el nombre y el tipo del agente de escucha de seguimiento que desea usar.</span><span class="sxs-lookup"><span data-stu-id="592c2-116">You can use the add element to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="592c2-117">En nuestro ejemplo de configuración, se denomina el agente de escucha "xmlTrace" y se agrega la escucha de seguimiento estándar de .NET Framework (System.Diagnostics.XmlWriterTraceListener) como el tipo que deseamos utilizar.</span><span class="sxs-lookup"><span data-stu-id="592c2-117">In our example configuration, we named the Listener "xmlTrace" and added the standard .NET Framework trace listener (System.Diagnostics.XmlWriterTraceListener) as the type we want to use.</span></span> <span data-ttu-id="592c2-118">Puede agregar cualquier número de agentes de escucha de seguimiento para cada origen.</span><span class="sxs-lookup"><span data-stu-id="592c2-118">You can add any number of trace listeners for each source.</span></span> <span data-ttu-id="592c2-119">Por ejemplo, en los ejemplos siguientes, también hemos agregado otro agente de escucha denominado "textTrace" que usa el agente de escucha de seguimiento de .NET Framework System.Diagnostics.TextWriterTraceListener.</span><span class="sxs-lookup"><span data-stu-id="592c2-119">For example, in the following examples, we also added another listener named "textTrace" that uses the .NET Framework trace listener System.Diagnostics.TextWriterTraceListener.</span></span> <span data-ttu-id="592c2-120">Si el agente de escucha de seguimiento emite el seguimiento en un archivo, debe especificar la ubicación del archivo de salida y el nombre del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="592c2-120">If the trace listener emits the trace to a file, you must specify the output file location and name in the configuration file.</span></span> <span data-ttu-id="592c2-121">Esto se hace estableciendo initializeData para el nombre del archivo para ese agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="592c2-121">This is done by setting initializeData to the name of the file for that listener.</span></span>  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a><span data-ttu-id="592c2-122">Habilitación del seguimiento de la Agregar referencia de servicio de adaptador complemento</span><span class="sxs-lookup"><span data-stu-id="592c2-122">Enabling Tracing for the Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="592c2-123">Puede habilitar el seguimiento para este complemento agregando la siguiente sección en el archivo devenv.exe.config ubicado en `\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`.</span><span class="sxs-lookup"><span data-stu-id="592c2-123">You can enable tracing for this plug-in by adding the following section in the devenv.exe.config file located in `\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`.</span></span>
  
```  
<system.diagnostics>  
   <sources>  
    <source name="Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse" switchValue="Verbose, ActivityTracing">  
      <listeners>  
        <add name="textTrace"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\aasr.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
    <add initializeData="C:\logs\aasr.log" type="System.Diagnostics.TextWriterTraceListener" name="textTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" indentsize="4" />  
</system.diagnostics>  
```  
  
## <a name="enable-tracing-for-the-consume-adapter-service-add-in"></a><span data-ttu-id="592c2-124">Habilitar el seguimiento de los Consume Adapter Service complemento</span><span class="sxs-lookup"><span data-stu-id="592c2-124">Enable Tracing for the Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="592c2-125">Puede habilitar el seguimiento para este complemento agregando la siguiente sección en el archivo BTSNTSVC.exe.config ubicado en `\Program Files (x86)\Microsoft BizTalk Server`.</span><span class="sxs-lookup"><span data-stu-id="592c2-125">You can enable tracing for this add-in by adding the following section in the BTSNTSVC.exe.config file located in `\Program Files (x86)\Microsoft BizTalk Server`.</span></span>  
  
```  
<system.diagnostics>  
   <sources>  
    <source name="Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse" switchValue="Verbose, ActivityTracing">  
      <listeners>  
        <add name="textTrace"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\aasr.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
    <add initializeData="C:\logs\aasr.log" type="System.Diagnostics.TextWriterTraceListener" name="textTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" indentsize="4" />  
</system.diagnostics>  
```  
  
## <a name="see-also"></a><span data-ttu-id="592c2-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="592c2-126">See Also</span></span>  
 [<span data-ttu-id="592c2-127">Solucionar problemas del adaptador creado mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="592c2-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)