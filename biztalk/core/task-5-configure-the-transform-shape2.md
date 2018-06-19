---
title: 'Tarea 5: Configurar la transformación Shape2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e92874e-9021-4cf6-bab6-d4173308c469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 596afdecc38f25ef92dbeb368197d9c71adaffc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279636"
---
# <a name="task-5-configure-the-transform-shape"></a>Tarea 5: Configurar la forma transformación
Utilice el siguiente procedimiento para configurar la forma Transformación.  
  
### <a name="to-configure-the-transform-shape"></a>Para configurar la forma Transformación  
  
1.  Arrastre una forma Construir mensaje después de ReceiveBeginDocResponse.  
  
    -   **Mensajes construidos:** EditLineMsg  
  
    -   **Nombre:** ConstructEditLineMessageWithData  
  
    1.  Pulse el botón derecho en el centro, seleccione **Insertar forma**y, a continuación, seleccione **transformar**.  
  
         ![Insertar forma transformación](../core/media/insert-shape-transform.gif "insert_shape_transform")  
  
    2.  Mediante la forma Transformación, asigne datos a partir de los datos que se envían a los datos enviados.  
  
     Para su entorno de trabajo, enviaría un documento (en lugar de BeginDoc) con todos los valores posibles, lo que le permite construir todos los mensajes posibles, BeginDoc, EditLine y EndDoc. Para este ejemplo, no obstante, sólo hay datos codificados.  
  
2.  Haga doble clic en la forma Transform_1 para abrirla.  
  
    1.  Seleccione origen y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.  
  
         ![Transformar origen](../core/media/transform-source.gif "transform_source")  
  
    2.  Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EditLineMsg**y haga clic en **Aceptar**.  
  
         ![Destino de la transformación](../core/media/transform-destination.gif "transform_destination")  
  
3.  En el Explorador de soluciones, haga doble clic en **Transform_1.btm** para abrir la herramienta de asignación. Vincule los cuatro siguientes elementos:  
  
    -   mnCMJobNo  
  
    -   szCMComputerID  
  
    -   mnProcessID  
  
    -   mnTransactionID  
  
     ![Ejemplo de asignación de transformación](../core/media/example-transformmapping.gif "example_transformmapping")  
  
     Para facilitar su uso, este ejemplo tiene valores codificados. Haga clic en el elemento del esquema de destino y establezca el siguiente valor.  
  
     ![Asignación](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")  
  
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
  
4.  Arrastre una forma Construir mensaje después de ReceiveEditLine.  
  
    -   **Mensajes construidos:** EndDocMsg  
  
    -   **Nombre:** ConstructEndDocMessageWithData  
  
         Pulse el botón derecho en el medio y seleccione **Insertar forma**y, a continuación, seleccione **transformar**.  
  
5.  Haga doble clic en la forma Transform_2 para abrirla.  
  
    1.  Seleccione **origen** y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.  
  
    2.  Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EndDocMsg**y haga clic en **Aceptar**.  
  
6.  En el Explorador de soluciones, haga doble clic en **Transform_2.btm** para abrir la herramienta de asignación. Vincule los cuatro siguientes elementos:  
  
    -   mnCMJobNo  
  
    -   szCMComputerID  
  
    -   mnProcessID  
  
    -   mnTransactionID  
  
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
 [Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md)   
 [Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md)   
 [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md)