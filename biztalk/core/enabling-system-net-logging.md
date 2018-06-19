---
title: Habilitar el registro de System.Net | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eea50b9-1f46-45fc-a327-585adb4583a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e672f2b9e7ae8b0ef3889493273660c8ef9140c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239940"
---
# <a name="enabling-systemnet-logging"></a>Habilitar el registro de System.Net
Puede habilitar el registro para el `System.Net` y `System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] espacio de nombres para el servicio BTSNtSvc.exe. Esto originará la creación de un archivo de registro detallado con información que puede ayudar a identificar problemas relacionados con la instalación de BizTalk Server.  
  
> [!NOTE]
>  Se trata de una característica de Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] y funcionará en [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] o posterior.  
  
 Está habilitado el seguimiento modificando el archivo de configuración de aplicación para **BTSNtSvc.exe**, **BTSNtSvc.exe.config**. Puede encontrarse en la ruta de instalación de BizTalk Server; si instaló BizTalk Server en la ubicación predeterminada, el archivo BtsNtSvc.exe estará en el directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
 Para modificar **BTSNtSvc.exe.config**, abra el archivo de configuración y pegue el código siguiente en el `<configuration>` elemento mediante el Bloc de notas o el editor de texto que prefiera.  
  
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
  
 El archivo de registro se escribirá en el mismo directorio que contiene BTSNtSvc.exe. Si ha instalado en la ubicación predeterminada, se escribirán en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Interpretar el seguimiento de red](http://go.microsoft.com/fwlink/?LinkId=78679)