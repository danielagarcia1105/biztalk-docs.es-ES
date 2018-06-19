---
title: Un adaptador con el SDK de adaptador LOB de WCF de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a4f4758-3e3e-48c4-b4cf-414c2b05d539
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca4b68f23f791de3ecd68bc69b85c2908b6d7a0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965362"
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a>Seguimiento de un adaptador con el SDK de adaptador LOB de WCF
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]el seguimiento se basa en Systems.Diagnostics. Usar Microsoft.ServiceModel.Channels origen de seguimiento para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución.  Usar origen de seguimiento Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse para [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Los seguimientos de WCF se escriben en el origen denominado System.ServiceModel.  
  
 El programador de adaptadores puede proporcionar un nombre de origen de seguimiento para el adaptador utiliza la clase Microsoft.ServiceModel.Channels.Common.AdapterTrace. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera una clase de contenedor de seguimiento que puede usarse por el desarrollador de adaptadores para proporcionar la instrumentación en el código del adaptador.  
  
 Para obtener información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx).
  
 Para obtener información acerca del análisis de seguimientos de WCF, vea [herramienta Service Trace Viewer (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx). 
  
## <a name="sample-trace-wrapper-utility-class"></a>Clase de utilidad de contenedor de seguimiento de ejemplo  
  
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
  
 La clase de utilidad anterior, a continuación, ser usada por el programador de adaptadores en todo el código de adaptador para proporcionar datos de instrumentación para los consumidores de adaptador.  
  
 EchoAdapterUtilities.Trace.Trace (System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Conexión abre correctamente!");  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a>Habilitar el seguimiento para el adaptador y la ejecución del SDK de adaptador LOB de WCF  
 Puede habilitar el seguimiento que se proporcionan en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] agregando la siguiente sección en el archivo app.config de la aplicación que utiliza el adaptador.  
  
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
  
 Puede utilizar el elemento Agregar para especificar el nombre y el tipo del agente de escucha de seguimiento que desea usar. En nuestro ejemplo de configuración, se denomina el agente de escucha "xmlTrace" y se agrega la escucha de seguimiento estándar de .NET Framework (System.Diagnostics.XmlWriterTraceListener) como el tipo que deseamos utilizar. Puede agregar cualquier número de agentes de escucha de seguimiento para cada origen. Por ejemplo, en los ejemplos siguientes, también hemos agregado otro agente de escucha denominado "textTrace" que usa el agente de escucha de seguimiento de .NET Framework System.Diagnostics.TextWriterTraceListener. Si el agente de escucha de seguimiento emite el seguimiento en un archivo, debe especificar la ubicación del archivo de salida y el nombre del archivo de configuración. Esto se hace estableciendo initializeData para el nombre del archivo para ese agente de escucha.  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a>Habilitación del seguimiento de la Agregar referencia de servicio de adaptador complemento  
 Puede habilitar el seguimiento para este complemento agregando la siguiente sección en el archivo devenv.exe.config ubicado en `\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`.
  
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
  
## <a name="enable-tracing-for-the-consume-adapter-service-add-in"></a>Habilitar el seguimiento de los Consume Adapter Service complemento  
 Puede habilitar el seguimiento para este complemento agregando la siguiente sección en el archivo BTSNTSVC.exe.config ubicado en `\Program Files (x86)\Microsoft BizTalk Server`.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)