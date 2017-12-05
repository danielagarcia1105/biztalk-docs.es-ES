---
title: "Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b81599-bd26-44dc-9cf3-73868248764c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f54effeeeb83d7a863298dcac4118ab1495ce3c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario"></a>Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de reenvío
Antes de comenzar este paso, debe completar [preparando para utilizar el Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).  
  
### <a name="to-configure-the-swift-adapter"></a>Para configurar el adaptador SWIFT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk, expanda **configuración de plataforma**, expanda **adaptador**, haga clic en **INTERACT**, seleccione **New**y, a continuación, haga clic en **controlador de envío**.  
  
3.  En el **INTERACT – propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha, desde el **nombre de Host** lista desplegable, seleccione **interacthost**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de transporte interactuar** cuadro de diálogo la **propiedades** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Argumentos**|Escriba el siguiente argumento: – SagMessagePartner \<interactuar socio de mensaje de cliente creado en SAG\> **Nota:** el cliente en el argumento es el MessagePartner configurado en SAG.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessageBody**|En la lista desplegable, seleccione **FALSE**. **Nota:** si se establece en TRUE, conserva el cuerpo del mensaje en la base de datos de seguimiento de BizTalk. Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Habilitar**|False:|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte interactuar.  
  
6.  Haga clic en **Aceptar** para cerrar la interacción: cuadro de diálogo Propiedades de controlador de adaptador.  
  
7.  En el cuadro de mensaje, haga clic en **Aceptar**y, a continuación, reinicie la instancia de host de interacción.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar almacén y escenario de reenvío (inserción)](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [Paso 2: Agregar configuración de SWIFTNet la Paramfile para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)   
 [Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 4: Probar el escenario integral de almacenamiento y reenvío de InterAct](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)