---
title: Habilitar el registro de System.Net | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eea50b9-1f46-45fc-a327-585adb4583a0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e672f2b9e7ae8b0ef3889493273660c8ef9140c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-systemnet-logging"></a><span data-ttu-id="00b50-102">Habilitar el registro de System.Net</span><span class="sxs-lookup"><span data-stu-id="00b50-102">Enabling System.Net Logging</span></span>
<span data-ttu-id="00b50-103">Puede habilitar el registro para el `System.Net` y `System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] espacio de nombres para el servicio BTSNtSvc.exe.</span><span class="sxs-lookup"><span data-stu-id="00b50-103">You can enable logging for the `System.Net` and `System.Net.Sockets`[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] namespace for the BTSNtSvc.exe service.</span></span> <span data-ttu-id="00b50-104">Esto originará la creación de un archivo de registro detallado con información que puede ayudar a identificar problemas relacionados con la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="00b50-104">This will cause a detailed log file to be created containing information that may help you identify issues with your BizTalk Server installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00b50-105">Se trata de una característica de Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] y funcionará en [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="00b50-105">This is a feature of the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] and will work in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] or later.</span></span>  
  
 <span data-ttu-id="00b50-106">Está habilitado el seguimiento modificando el archivo de configuración de aplicación para **BTSNtSvc.exe**, **BTSNtSvc.exe.config**. Puede encontrarse en la ruta de instalación de BizTalk Server; si instaló BizTalk Server en la ubicación predeterminada, el archivo BtsNtSvc.exe estará en el directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00b50-106">Tracing is enabled by modifying the application configuration file for **BTSNtSvc.exe**,  **BTSNtSvc.exe.config**. It can be found in the BizTalk Server installation path; if you installed BizTalk Server to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="00b50-107">Para modificar **BTSNtSvc.exe.config**, abra el archivo de configuración y pegue el código siguiente en el `<configuration>` elemento mediante el Bloc de notas o el editor de texto que prefiera.</span><span class="sxs-lookup"><span data-stu-id="00b50-107">To modify **BTSNtSvc.exe.config**, open the configuration file and paste the code below into the `<configuration>` element using Notepad or your favorite text editor.</span></span>  
  
```  
<system.diagnostics>  
  <sources>  
    <source name="System.Net" switchValue="Verbose">  
      <listeners>  
        <add name="System.Net"/>  
      </listeners>  
    </source>  
    <source name="System.Net.Sockets" switchValue="Verbose">  
      <listeners>  
        <add name="System.Net"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="System.Net"  
          type="System Diagnostics.TextWriterTraceListener"  
          initializeData="System.Net..log"/>  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="00b50-108">El archivo de registro se escribirá en el mismo directorio que contiene BTSNtSvc.exe.</span><span class="sxs-lookup"><span data-stu-id="00b50-108">The log file will be written to the same directory that contains BTSNtSvc.exe.</span></span> <span data-ttu-id="00b50-109">Si ha instalado en la ubicación predeterminada, se escribirán en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00b50-109">If you installed to the default location, it will be written to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b50-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="00b50-110">See Also</span></span>  
 [<span data-ttu-id="00b50-111">Interpretar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="00b50-111">Interpreting Network Tracing</span></span>](http://go.microsoft.com/fwlink/?LinkId=78679)