---
title: "Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 831a311a23e6d24f1a655d0df604032a02cb782d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a>Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de avance (extracción)
Antes de comenzar este paso, debe completar [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).  
  
### <a name="to-configure-the-swift-adapter"></a>Para configurar el adaptador SWIFT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en **INTERACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.  
  
3.  En el **INTERACT – propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **interacthost**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de transporte interactuar** cuadro de diálogo la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: – SagMessagePartner \<interactuar socio de mensaje de cliente creado en SAG > **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessageBody**|En la lista desplegable, seleccione **FALSE**. **Nota:** si se establece en TRUE, conserva el cuerpo del mensaje en la base de datos de seguimiento de BizTalk. Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|False:|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte interactuar.  
  
6.  Haga clic en **Aceptar** para cerrar la interacción: cuadro de diálogo Propiedades de controlador de adaptador.  
  
7.  En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de interacción.  
  
8.  Repita el paso 1.  
  
9. En el árbol de consola, expanda Administración de BizTalk Server, expanda el **BizTalk** de grupo, expanda **configuración de plataforma**, expanda **adaptador**, seleccione INTERACT, abra  **BizTalkServerApplication** y, a continuación, haga clic en **propiedades**.  
  
10. En el **propiedades de transporte interactuar** cuadro de diálogo la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: – SagMessagePartner \<interactuar socio de mensaje de cliente creado en SAG > **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessageBody**|En la lista desplegable, seleccione **FALSE**. **Nota:** si se establece en TRUE, conserva el cuerpo del mensaje en la base de datos de seguimiento de BizTalk. Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|True|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
11. Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte interactuar.  
  
12. Seleccione **establecer este controlador como predeterminado** opción.  
  
13. Haga clic en **Aceptar** para cerrar el cuadro de diálogo de propiedades del controlador de adaptador de INTERACT:.  
  
14. En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie el **BizTalkServerApplication** instancia de host.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md)   
 [Paso 3: Crear una orquestación con el puerto de envío dinámico para el almacén de interacción y el escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md)   
 [Paso 4: Probar el almacén de interacción y el escenario de-to-End de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)