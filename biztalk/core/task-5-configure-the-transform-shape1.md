---
title: 'Tarea 5: Configurar la transformación de forma1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e5b690774061e95fb34a070e19890d3a2a4eb0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003069"
---
# <a name="task-5-configure-the-transform-shape"></a>Tarea 5: Configurar la forma transformación
Utilice el siguiente procedimiento para configurar la forma Transformación.  
  
### <a name="to-configure-the-transform-shape"></a>Para configurar la forma Transformación  
  
1. Arrastre una forma Construir mensaje después de ReceiveBeginDocResponse.  
  
   - **Mensajes construidos:** EditLineMsg  
  
   - **Nombre:** ConstructEditLineMessageWithData  
  
     Haga clic en la parte central, seleccione **Insertar forma**y, a continuación, seleccione **transformar**.  
  
     ![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")  
  
     Mediante la forma Transformación, asigne datos a partir de los datos que se envían a los datos enviados.  
  
     Para su entorno de trabajo, enviaría un documento (en lugar de BeginDoc) con todos los valores posibles, lo que le permite construir todos los mensajes posibles, BeginDoc, EditLine y EndDoc. Para este ejemplo, no obstante, sólo hay datos codificados.  
  
2. Haga doble clic en **Transform_1** para abrir.  
  
   1.  Seleccione origen y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.  
  
        ![](../core/media/jde-transform-source.gif "JDE_transform_source")  
  
   2.  Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EditLineMsg**y haga clic en **Aceptar**.  
  
        ![](../core/media/jde-transform-destination.gif "JDE_transform_destination")  
  
3. En el Explorador de soluciones, haga doble clic en **Transform_1.btm** para abrir la herramienta de asignación. Vincule los cuatro siguientes elementos:  
  
   - mnCMJobNo  
  
   - szCMComputerID  
  
   - mnProcessID  
  
   - mnTransactionID  
  
     ![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")  
  
     Para facilitar su uso, este ejemplo tiene valores codificados. Haga clic en el elemento del esquema de destino y establezca el siguiente valor.  
  
     ![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEditLine xmlns:ns0="http://schemas.microsoft.com/  
         [JDE://CSALES/B4200310]">  
      <ns0:cCMLineAction>A</ns0:cCMLineAction>  
      <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
      <ns0:cCMWriteToWFFlag>2</ns0:cCMWriteToWFFlag>  
      <ns0:szItemNo>210</ns0:szItemNo>  
      <ns0:mnQtyOrdered>1</ns0:mnQtyOrdered>  
      <ns0:cSalesTaxableYN>N</ns0:cSalesTaxableYN>  
      <ns0:szTransactionUOM>EA</ns0:szTransactionUOM>  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   </ns0:F4211FSEditLine>  
   ```  
  
4. Arrastre una forma Construir mensaje después de ReceiveEditLine.  
  
   - **Mensajes construidos:** EndDocMsg  
  
   - **Nombre:** ConstructEndDocMessageWithData  
  
     Haga clic en el medio y seleccione **Insertar forma**y, a continuación, seleccione **transformar**.  
  
5. Haga doble clic en **Transform_2** para abrir.  
  
   1.  Seleccione **origen** y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.  
  
   2.  Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EndDocMsg**y haga clic en **Aceptar**.  
  
6. En el Explorador de soluciones, haga doble clic en **Transform_2.btm** para abrir la herramienta de asignación. Vincule los cuatro siguientes elementos:  
  
   - mnCMJobNo  
  
   - szCMComputerID  
  
   - mnProcessID  
  
   - mnTransactionID  
  
     Para facilitar su uso, este ejemplo tiene valores codificados. Haga clic en el elemento del esquema de destino y establezca el siguiente valor.  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
       [JDE://CSALES/B4200310]">  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
      <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
   </ns0:F4211FSEndDoc>  
   ```  
  
## <a name="see-also"></a>Vea también  
 [Tarea 1: Creación de los puertos](../core/task-1-create-the-ports2.md)   
 [Tarea 2: Creación de los mensajes](../core/task-2-create-the-messages1.md)   
 [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [Tarea 4: Configurar la forma Construir mensaje](../core/task-4-configure-the-construct-message-shape2.md)