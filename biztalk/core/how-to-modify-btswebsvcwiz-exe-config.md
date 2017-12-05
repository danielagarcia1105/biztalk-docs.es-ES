---
title: "Cómo modificar BTSWebSvcWiz.exe.config | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, code samples
- Web services, debugging
ms.assetid: 8466e460-faa9-45ea-9586-19174858d194
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4862e347fd74c1431f253a1cccedbd844c97c63c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-modify-btswebsvcwizexeconfig"></a><span data-ttu-id="20e9d-102">Cómo modificar BTSWebSvcWiz.exe.config</span><span class="sxs-lookup"><span data-stu-id="20e9d-102">How to Modify BTSWebSvcWiz.exe.config</span></span>
<span data-ttu-id="20e9d-103">Puede habilitar el seguimiento depurar el Asistente para publicación de servicios Web de BizTalk mediante el comentario de la \<agregar\> nodo en el archivo BTSWebSvcWiz.exe.config.</span><span class="sxs-lookup"><span data-stu-id="20e9d-103">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add\> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="20e9d-104">Si el nodo de agente de escucha de seguimiento no se hace referencia y la *initializeData* parámetro se ha modificado, BizTalk Server escribe la salida del archivo de seguimiento en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="20e9d-104">If the trace listener node is uncommented and the *initializeData* parameter is unchanged, BizTalk Server writes the trace file output to the current directory.</span></span> <span data-ttu-id="20e9d-105">Como alternativa, puede establecer el seguimiento de nivel de **ApplicationTraceSwitch** y establezca el nombre de ruta de acceso al archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="20e9d-105">Alternatively, you can set the trace level of **ApplicationTraceSwitch** and set the path name of the trace file.</span></span>  
  
 <span data-ttu-id="20e9d-106">BTSWebSvcWiz.exe.config está ubicado en el mismo directorio que el archivo BTSWebSvcWiz.exe, que normalmente es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20e9d-106">BTSWebSvcWiz.exe.config is located in the same directory as the BTSWebSvcWiz.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="20e9d-107">El siguiente es un ejemplo de una línea \<agregar\> nodo en el archivo BTSWebSvcWiz.exe.config:</span><span class="sxs-lookup"><span data-stu-id="20e9d-107">The following is an example of an uncommented \<add\> node in BTSWebSvcWiz.exe.config file:</span></span>  
  
```  
<system.diagnostics>  
  <switches>  
    <!-- TraceLevel 0=Off, 1=Error, 2=Warning, 3=Info, 4=Verbose -->  
    <add name="ApplicationTraceSwitch" value="4" />  
  </switches>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <!--add name="Trace"  
       type="System.Diagnostics.TextWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
       initializeData="BTSWebSvcWiz.trace.log" /-->  
    </listeners>  
  </trace>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="20e9d-108">Esta función de seguimiento utiliza la clase Trace de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20e9d-108">This tracing feature uses the Trace class in the .NET Framework.</span></span> <span data-ttu-id="20e9d-109">Para obtener más información acerca de la clase de seguimiento, vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886).</span><span class="sxs-lookup"><span data-stu-id="20e9d-109">For more information about the Trace class, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886).</span></span>  
  
 <span data-ttu-id="20e9d-110">Para obtener información acerca de **TextWriterTraceListener**, vea "TextWriterTraceListener" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ayudar a la colección [http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267).</span><span class="sxs-lookup"><span data-stu-id="20e9d-110">For information about **TextWriterTraceListener**, see "TextWriterTraceListener" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e9d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="20e9d-111">See Also</span></span>  
 [<span data-ttu-id="20e9d-112">Depuración de servicios web publicados</span><span class="sxs-lookup"><span data-stu-id="20e9d-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)