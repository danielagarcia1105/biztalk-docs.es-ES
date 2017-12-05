---
title: Mediante el seguimiento del adaptador de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- Adapter Trace Utility, running
- enabling, Adapter Trace Utility
ms.assetid: ddc6b2c7-9dee-43c1-950b-8fd580bfcb26
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1e14234363ace4b953fa4766a97502753572e6f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="using-biztalk-adapter-tracing"></a>Usar el seguimiento del adaptador BizTalk
Este tema describe cómo instalar la herramienta de registro de seguimiento y cómo habilitar el seguimiento del adaptador de BizTalk.  
  
## <a name="install-the-trace-log-tool"></a>Instalar la herramienta de registro de seguimiento  
  
#### <a name="to-install-the-trace-log-tool-tracelogexe"></a>Para instalar la herramienta de registro de seguimiento (tracelog.exe)  
  
1.  Descargue la herramienta de registro de seguimiento del sitio web [Actualización del Kit de desarrollo de software de Microsoft® Windows® para Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) (puede estar en inglés).  
  
    > [!NOTE]
    >  Instale esta versión (6.0) del SDK, incluso si ejecuta [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]. Si instala el **Windows SDK para Windows Server 2008 y .NET Framework 3.5** versión (v. 6.1), no se instalará la herramienta de registro de seguimiento.  
  
2.  Inicie el programa de instalación web **Microsoft® Windows® Software Development Kit Update for Windows Vista** . Para ello, haga clic en el vínculo del archivo **PSDK-x86.exe** en la parte inferior de la página web.  
  
    > [!NOTE]
    >  Si usa una versión de 64 bits de Windows, seleccione los archivos correctos para descargarlos en el sistema.  
  
3.  En el cuadro de diálogo **Select an Installation Type** , elija la opción para la instalación **Custom** y, a continuación, haga clic en **Next**.  
  
4.  Acepte la ubicación de instalación predeterminada y, a continuación, haga clic en **Next**.  
  
5.  En el cuadro de diálogo **Custom Installation** , haga clic hasta deshabilitar todas las características disponibles.  
  
6.  Expanda la característica **Microsoft Windows Core SDK** y, a continuación, expanda la característica **Tools** .  
  
7.  Seleccione la característica **Tools (Intel 64-bit)** y, a continuación, haga clic en **Will be installed on local hard drive**.  
  
8.  Haga clic en **Next**y de nuevo en **Next** para iniciar la instalación.  
  
    > [!NOTE]
    >  Después de instalar **Microsoft® Windows® Software Development Kit Update for Windows Vista** , se le puede solicitar que reinicie el equipo en función las demás características que elija para instalar junto con la herramienta de registro de seguimiento. Esto se debe a que determinados componentes de **Microsoft® Windows® Software Development Kit Update for Windows Vista** no funcionarán correctamente hasta que se haya completado el reinicio. No es necesario reiniciar para utilizar la herramienta de registro de seguimiento.  
  
## <a name="enable-biztalk-adapter-tracing-with-tracecmd"></a>Habilite el seguimiento del adaptador de BizTalk con trace.cmd  
  
#### <a name="to-enable-biztalk-adapter-tracing"></a>Para habilitar el seguimiento del adaptador de BizTalk  
  
1.  En un símbolo del sistema, cambie el directorio actual al directorio donde está instalado el servidor BizTalk Server. De forma predeterminada, el servidor BizTalk Server está instalado en el [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] directory.  Si utiliza una versión de 64 bits de Windows y el servidor BizTalk Server, la ruta de instalación es [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)].  
  
2.  Escriba el siguiente comando y presione ENTRAR:  
  
     **Trace - tools "Ruta de acceso de la herramienta de registro de seguimiento"**  
  
     De forma predeterminada, la herramienta de registro de seguimiento (tracelog.exe) se encuentra en el directorio **C:\Archivos de programa\Microsoft SDKs\Windows\v6.0\Bin** . Si usa una versión de 64 bits de Windows, la herramienta de registro de seguimiento se encuentra en **C:\Archivos de programa (x86)\Microsoft SDKs\Windows\v6.0\Bin**.  Debe escribir la ruta de la herramienta de registro de seguimiento entre comillas.  
  
     Por ejemplo, escriba el siguiente comando y presione ENTRAR:  
  
     **Trace - tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**  
  
    > [!NOTE]
    >  El conmutador **-tools** indica al archivo Trace.cmd la ubicación del archivo Tracelog.exe.  
    >   
    >  Si el comando se ejecuta correctamente, el resultado será similar al siguiente:  
    >   
    >  **seguimiento 2.0: administrar BizTalk 2006 versión Bits seguimiento.**  
    >   
    >  **Estableciendo TRACE_TOOL_SEARCH_PATH en "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**  
  
## <a name="capture-trace-output-with-tracecmd"></a>Capturar la salida del seguimiento con trace.cmd  
  
#### <a name="to-capture-trace-output"></a>Para capturar la salida del seguimiento  
  
1.  En un símbolo del sistema, cambie el directorio actual al directorio donde está instalado el servidor BizTalk Server.  
  
2.  En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR:  
  
     **Trace - inicio**  
  
3.  Reproduzca la situación para la que desea capturar la salida del seguimiento.  
  
4.  En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR:  
  
     **Trace - detener**  
  
5.  Después de detener el seguimiento, un archivo binario que se denomina **Btstrace.bin** se genera en la carpeta donde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado.  
  
6.  Envíe el archivo **Btstrace.bin** a los Servicios de soporte técnico de Microsoft para que lo analicen.  
  
## <a name="see-also"></a>Vea también  
 [Uso de adaptadores](../core/using-adapters.md)   
 [Solucionar problemas del adaptador de Windows SharePoint Services](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)