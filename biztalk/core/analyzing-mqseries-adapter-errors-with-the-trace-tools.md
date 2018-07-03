---
title: Análisis de errores del adaptador de MQSeries con las herramientas de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, about Adapter Trace Utility
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- errors, MQSeries adapters
- MQSeries adapters, Adapter Trace Utility
- Adapter Trace Utility, running
- MQSeries adapters, errors
- Adapter Trace Utility
ms.assetid: fdc73d99-3b73-491d-9b2f-7064364fefa7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de3ac3f94edb6ca1c3f7f366ef5c0578eb69d76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999037"
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a>Analizar errores con las herramientas de seguimiento del adaptador de MQSeries
Las herramientas de seguimiento sirven para analizar errores de mensajería al ejecutar la aplicación. El adaptador de MQSeries debe usarse conjuntamente con dos herramientas: una para el adaptador y la aplicación de BizTalk (trace.cmd), y la otra para MQSAgent (MQSTrace.cmd). Ambas herramientas utilizan tracelog.exe. Debe instalar tracelog.exe si no lo tiene.  

 Con tanto en trace.cmd como en MQSTrace.cmd tiene que establecer una opción (**-herramientas**) para que estas herramientas puedan encontrar el archivo tracelog.exe.  

## <a name="install-the-trace-utility"></a>Instalar la Utilidad de seguimiento  
 Siga este procedimiento para instalar la herramienta Utilidad de seguimiento del adaptador de BizTalk:  

1.  Para descargar el archivo Tracelog.exe, visite el sitio Web de descargas de Microsoft Platform SDK en [ http://go.microsoft.com/fwlink/?LinkId=21975 ](http://go.microsoft.com/fwlink/?LinkId=21975).  

2.  Iniciar el programa de instalación Web de Platform SDK haciendo clic en el vínculo para el **PSDK-x86.exe** archivo en la parte inferior de la página Web.  

3.  Cuando así lo solicite el programa, seleccione la opción de instalación personalizada.  

4.  En el cuadro de diálogo **Custom Installation** , haga clic hasta deshabilitar todas las características disponibles.  

5.  Expanda la característica **Microsoft Windows Core SDK** y, a continuación, expanda la característica **Tools** .  

6.  Seleccione la característica **Tools (Intel 64-bit)** y, a continuación, haga clic en **Will be installed on local hard drive**.  

7.  Haga clic en **Next**y de nuevo en **Next** para iniciar la instalación.  

8.  Busque el *unidad*:\\*MicrosoftPlatformSDKInstallationFolder\bin* carpeta y, a continuación, copie el archivo Tracelog.exe a la carpeta de instalación de Microsoft BizTalk Server. El directorio de instalación de BizTalk Server contiene también el archivo Trace.cmd.  

## <a name="enable-the-trace-utility"></a>Habilitar la Utilidad de seguimiento  
 Siga este procedimiento para habilitar la herramienta Utilidad de seguimiento del adaptador de BizTalk:  

1.  Mover el directorio que contiene trace.cmd. La ubicación predeterminada es el directorio de Microsoft BizTalk Server.  

2.  Escriba el siguiente comando, sustituya el directorio que contiene el archivo tracelog.exe file en su PC por el directorio que está entre comillas y, a continuación, presione ENTRAR:  

     **Trace - tools "c:\Program Files\Microsoft SDK\Bin"**  

3.  Desplácese hasta el directorio que contenga el archivo MQSTrace.cmd.  

4.  Escriba el siguiente comando, sustituya el directorio que contiene el archivo tracelog.exe file en su PC por el directorio que está entre comillas y, a continuación, presione ENTRAR:  

     **MQSTrace-tools "c:\Program Files\Microsoft SDK\Bin"**  

## <a name="run-the-trace-utility"></a>Ejecutar la Utilidad de seguimiento  
 Siga este procedimiento para ejecutar la Utilidad de seguimiento del adaptador de BizTalk:  

1. En el símbolo del sistema, escriba **trace.cmd-start - high**, y, a continuación, presione ENTRAR.  

2. Ejecute la situación de error.  

3. En el símbolo del sistema, escriba **trace.cmd-detener**, y, a continuación, presione ENTRAR.  

4. El archivo bts2006.bin contiene la salida de la herramienta de seguimiento. Póngase en contacto con los servicios de soporte técnico de Microsoft para su análisis. Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645).  

   Siga este procedimiento para ejecutar la Utilidad de seguimiento de MQSAgent:  

5. En el símbolo del sistema, escriba **MQSTrace.cmd-start - high**, y, a continuación, presione ENTRAR.  

6. Ejecute la situación de error.  

7. En el símbolo del sistema, escriba **MQSTrace.cmd-detener**.  

8. El archivo MQSAdapterTrace.bin contiene la salida de la herramienta de seguimiento. Póngase en contacto con los servicios de soporte técnico de Microsoft para su análisis. Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645).
