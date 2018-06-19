---
title: Cómo modificar BTSWebSvcWiz.exe.config | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, code samples
- Web services, debugging
ms.assetid: 8466e460-faa9-45ea-9586-19174858d194
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4862e347fd74c1431f253a1cccedbd844c97c63c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971130"
---
# <a name="how-to-modify-btswebsvcwizexeconfig"></a>Cómo modificar BTSWebSvcWiz.exe.config
Puede habilitar el seguimiento depurar el Asistente para publicación de servicios Web de BizTalk mediante el comentario de la \<agregar\> nodo en el archivo BTSWebSvcWiz.exe.config. Si el nodo de agente de escucha de seguimiento no se hace referencia y la *initializeData* parámetro se ha modificado, BizTalk Server escribe la salida del archivo de seguimiento en el directorio actual. Como alternativa, puede establecer el seguimiento de nivel de **ApplicationTraceSwitch** y establezca el nombre de ruta de acceso al archivo de seguimiento.  
  
 BTSWebSvcWiz.exe.config está ubicado en el mismo directorio que el archivo BTSWebSvcWiz.exe, que normalmente es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
 El siguiente es un ejemplo de una línea \<agregar\> nodo en el archivo BTSWebSvcWiz.exe.config:  
  
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
  
 Esta función de seguimiento utiliza la clase Trace de .NET Framework. Para obtener más información acerca de la clase de seguimiento, vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886).  
  
 Para obtener información acerca de **TextWriterTraceListener**, vea "TextWriterTraceListener" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ayudar a la colección [http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267).  
  
## <a name="see-also"></a>Vea también  
 [Depuración de servicios web publicados](../core/debugging-published-web-services.md)