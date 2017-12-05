---
title: 'Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f4d3e08-611a-4af1-a3e3-957ace3b74e6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab603f12e1f2c431f83af00dc79b57a9e416c251
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario"></a>Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar
Los pasos siguientes explican cómo configurar el controlador de envío para el adaptador de Interact. Antes de comenzar el procedimiento, debe completar los requisitos enumerados en [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).  
  
### <a name="to-configure-the-swift-adapter"></a>Para configurar el adaptador SWIFT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en  **INTERACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.  
  
3.  En el **INTERACT – propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **interacthost**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **INTERACTTransport propiedades** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: **SagMessagePartner**\<interactuar socio de mensaje de cliente creado en SAG\> **Nota:** el cliente en el argumento es el MessagePartner SAG configurado en.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessageBody**|En la lista desplegable, seleccione `FALSE`. **Nota:** si se establece en `TRUE`, conserva el cuerpo del mensaje en la base de datos de seguimiento. Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.|  
    |**LogMessages**|En la lista desplegable, seleccione `TRUE`. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|False|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte interactuar.  
  
6.  Haga clic en **Aceptar** para cerrar la interacción: cuadro de diálogo Propiedades de controlador de adaptador.  
  
7.  En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de interacción.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar en tiempo real escenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md)   
 [Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [Paso 4: Probar el escenario integral de InterAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)