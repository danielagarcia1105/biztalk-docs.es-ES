---
title: "Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18653322-b748-4954-93f7-9a7a39e406f8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d2946bcd37e0e7641a2d3bf750f88cd3199fc74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario"></a>Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct
Completa [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) antes de comenzar este paso.
  
## <a name="configure-the-swift-adapter"></a>Configure el adaptador de SWIFT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en  **FILEACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.  
  
3.  En el **FILEACT – adaptador HandlerProperties** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **fileacthost**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de transporte FILEACT** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: - SagMessagePartner \<Fileact cliente mensaje asociado se crean en SAG > **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**FACryptoMode**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|False|  
    |**Extremo de eventos**|Escriba el extremo SAG adecuado.|  
    |**PhysicalFolderName**|Escriba el nombre de la carpeta en el servidor. Por ejemplo, C:\Fileact\ServerLocation.|  
    |**PollingInterval**|Escriba el intervalo adecuado (en segundos) después de que el adaptador comprueba el estado de transferencia de archivos.|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte FILEACT.  
  
6.  Haga clic en **Aceptar** para cerrar el FILEACT: cuadro de diálogo Propiedades de controlador de adaptador.  
  
7.  En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de FileAct.  
  
## <a name="complete-steps"></a>Complete los pasos
 [Escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)   
 [Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 4: Probar el escenario de reenvío-to-End y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)