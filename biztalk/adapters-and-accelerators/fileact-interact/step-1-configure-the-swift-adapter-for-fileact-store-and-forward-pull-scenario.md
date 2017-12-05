---
title: "Paso 1: Configurar el adaptador de SWIFT para el escenario de extracción hacia delante y de almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc271544-6bc8-4d62-aba0-3fe3295f2a2a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41e57df0f77718e3e36b5d0d68896def6a768be7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario"></a>Paso 1: Configurar el adaptador de SWIFT para el escenario de extracción hacia delante y de almacenamiento de FileAct
Completa [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) antes de comenzar este paso.
  
## <a name="configure-the-swift-adapter"></a>Configure el adaptador de SWIFT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en  **FILEACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.  
  
3.  En el **FILEACT – adaptador HandlerProperties** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **FileActHost**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de transporte FILEACT** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: - SagMessagePartner \<Fileact cliente mensaje asociado se crean en SAG\> **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**FACryptoMode**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|False|  
    |**Extremo de eventos**|Escriba el extremo SAG adecuado.|  
    |**PhysicalFolderName**|Escriba el nombre de la carpeta en el servidor. Por ejemplo, C:\Fileact\ServerLocation.|  
    |**PollingInterval**|Escriba el valor adecuado para PollingInterval. Por ejemplo, 5. Esto indica que el intervalo (en segundos) después de que el adaptador comprueba el estado de transferencia de archivos.|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte FILEACT.  
  
6.  Haga clic en **Aceptar** para cerrar el FILEACT: cuadro de diálogo Propiedades de controlador de adaptador.  
  
7.  En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de FileAct.  
  
8.  Repita el paso 1.  
  
9. En el árbol de consola, expanda **administración de BizTalk Server**, expanda la **BizTalk** de grupo, expanda **configuración de plataforma**, expanda **adaptador**, seleccione **FILEACT**, abra **BizTalkServerApplication** y, a continuación, haga clic en **propiedades**.  
  
10. En el **propiedades de transporte FILEACT** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: – SagMessagePartner \<Fileact cliente mensaje asociado se crean en SAG\> **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessageBody**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM. **Nota:** si se establece en TRUE, conserva el cuerpo del mensaje en la base de datos de seguimiento de BizTalk. Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|**True**|  
    |**Extremo de eventos**|Escriba el extremo SAG adecuado.|  
    |**PhysicalFolderName**|Escriba el nombre de la carpeta en el servidor. Por ejemplo, C:\Fileact\ServerLocation.|  
    |**PollingInterval**|Escriba el valor adecuado para PollingInterval. Por ejemplo, 5. Esto indica que el intervalo (en segundos) después de que el adaptador comprueba el estado de transferencia de archivos.|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
11. Haga clic en Aceptar para cerrar el cuadro de diálogo Propiedades de transporte FILEACT.  
  
12. Seleccione convertir en la opción de controlador de forma predeterminada.  
  
13. Haga clic en Aceptar para cerrar el FILEACT: cuadro de diálogo Propiedades de controlador de adaptador.  
  
14. En el cuadro de mensaje, haga clic en Aceptar y, a continuación, reinicie la instancia de host BizTalkServerApplication.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Crear puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [Paso 3: Crear y enlazar una orquestación con el puerto de envío dinámico para el almacén de archivos de Act y escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md)   
 [Paso 4: Probar el escenario integral de almacenamiento y reenvío (extracción) de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-pull-end-to-end-scenario.md)