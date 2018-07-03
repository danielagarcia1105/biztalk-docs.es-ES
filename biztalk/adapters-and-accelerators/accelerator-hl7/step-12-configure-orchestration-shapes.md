---
title: 'Paso 12: Configurar formas de orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, orchestration shapes
- orchestrations, shapes
- message enrichment tutorial, orchestrations
ms.assetid: 9388254b-2841-4489-838e-de913ceff151
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d269fa177e7c0da857fb903cef5013f434554d17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991477"
---
# <a name="step-12-configure-orchestration-shapes"></a>Paso 12: Configurar formas de orquestación
En este paso, completa la configuración de las formas de orquestación con el fin de quitar las etiquetas inteligentes de configuración incompleta. Designa **DoorbellOutputMessage** como la salida del primer proceso de transformación, que designa **DoorbellMap.btm** como la asignación de ese proceso. A continuación, designe **DoorbellFinalMessage** como resultado del segundo proceso de transformación y agregue la expresión que enriquece el mensaje con datos de los campos adicionales.  
  
 **Requisito previo:** [artículo de KB 941261](http://support.microsoft.com/kb/941261) deben aplicarse antes de configurar la configuración de orquestación.  
  
### <a name="to-configure-orchestration-shapes"></a>Para configurar las formas de orquestación  
  
1. En la superficie de la vista de diseño de orquestación de Visual Studio, haga clic en el **ConstructMessage_1** forma.  
  
2. En el **propiedades** ventana, haga clic en el **mensajes construidos** propiedad, seleccione **DoorbellOutputMessage** desde la lista desplegable y, a continuación, presione  **Escriba**.  
  
3. En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellTransform** forma dentro de la **ConstructMessage_1** forma. En el **propiedades** ventana, haga clic en **nombre de asignación**y, a continuación, haga clic en el botón de puntos suspensivos (...) en el campo de atributo.  
  
4. En el cuadro de diálogo Configuración de transformación, seleccione **mapa existente**. En el **nombre completo de asignación** la lista desplegable, haga clic en **BTAHL7_Project.DoorbellMap**.  
  
5. Haga clic en **origen** en el panel izquierdo.  
  
6. Haga clic en el cuadro vacío en **nombre de Variable** y haga clic en **DoorBellInputMessage** en la lista desplegable.  
  
7. Haga clic en **destino** en el panel izquierdo.  
  
8. Haga clic en el cuadro vacío en **nombre de Variable** y haga clic en **DoorbellOutputMessage** en la lista desplegable.  
  
9. Haga clic en **Aceptar** para guardar los cambios.  
  
10. En la superficie de la vista de diseño de orquestación, haga clic en el **ConstructMessage_2** forma.  
  
11. En el **propiedades** ventana, haga clic en **mensajes construidos**, seleccione **DoorbellFinalMessage** desde la lista desplegable y, a continuación, presione **ENTRAR**.  
  
12. En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellFinalTransform** forma dentro de la **ConstructMessage_2** forma. En el **propiedades** ventana, haga clic en **expresión**y, a continuación, haga clic en el botón de puntos suspensivos (...) para abrir el Editor de expresiones de BizTalk.  
  
13. En el Editor de expresiones de BizTalk, haga clic en el campo de texto y pegue el texto siguiente:  
  
    ```  
    HeaderInfo = new System.Xml.XmlDocument();   
    HeaderInfo.LoadXml("<ns0:MSH_25_GLO_DEF xmlns:ns0=\"http://microsoft.com/HealthCare/HL7/2X\">  
        <MSH><MSH.2_EncodingCharacters>^~\\&</MSH.2_EncodingCharacters><MSH.3_SendingApplication>  
        <HD.0_NamespaceId>SrcApp</HD.0_NamespaceId><HD.1_UniversalId>SrcAppUid</HD.1_UniversalId>  
        </MSH.3_SendingApplication><MSH.4_SendingFacility><HD.0_NamespaceId>srcFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>srcFacUid</HD.1_UniversalId></MSH.4_SendingFacility><MSH.5_ReceivingApplication>  
        <HD.0_NamespaceId>dstApp</HD.0_NamespaceId><HD.1_UniversalId>dstAppUid</HD.1_UniversalId>  
        </MSH.5_ReceivingApplication><MSH.6_ReceivingFacility><HD.0_NamespaceId>dstFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>dstFacUid</HD.1_UniversalId></MSH.6_ReceivingFacility><MSH.7_DateTimeOfMessage>  
        <TS.1>200307092343</TS.1></MSH.7_DateTimeOfMessage><MSH.8_Security>sec</MSH.8_Security>  
        <MSH.9_MessageType><CM_MSG.0_MessageType>ADT</CM_MSG.0_MessageType>  
        <CM_MSG.1_TriggerEvent>A04</CM_MSG.1_TriggerEvent></MSH.9_MessageType>  
        <MSH.10_MessageControlId>msgid2134</MSH.10_MessageControlId><MSH.11_ProcessingId>  
        <PT.0_ProcessingId>P</PT.0_ProcessingId></MSH.11_ProcessingId><MSH.12_VersionId>  
       <VID_0_VersionId>2.2</VID_0_VersionId></MSH.12_VersionId></MSH></ns0:MSH_25_GLO_DEF>");  
  
    DoorbellFinalMessage.MSHSegment = HeaderInfo;  
    DoorbellFinalMessage.BodySegments = DoorbellOutputMessage;  
    DoorbellFinalMessage.ZSegments = "";  
  
    DoorbellFinalMessage(BTAHL7Schemas.MSH1) = 124;   
    DoorbellFinalMessage(BTAHL7Schemas.MessageEncoding) = 65001;  
    DoorbellFinalMessage(BTAHL7Schemas.MSH2) = "^~\\&";  
    DoorbellFinalMessage(BTAHL7Schemas.ParseError) = false;   
    DoorbellFinalMessage(BTAHL7Schemas.ZPartPresent) = false;  
    DoorbellFinalMessage(BTAHL7Schemas.SegmentDelimiter2Char) = true;  
  
    ```  
  
14. Haga clic en **Aceptar**.  
  
    > [!IMPORTANT]
    >  En la expresión "HeaderInfo.LoadXml", elimine los retornos de carro y espacios dentro de la expresión. La instrucción "HeaderInfo.LoadXml" debe estar en una línea.  
    > 
    > [!NOTE]
    >  El primer bloque de texto anterior es un ejemplo de un encabezado XML codificados de forma rígida. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador requiere un segmento de encabezado. Puede personalizar estos valores de encabezado según las necesidades de su entorno. El segundo bloque de texto anterior define las tres partes de mensaje necesarias en un mensaje de varias partes. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador requiere un mensaje de varias partes. El tercer bloque de texto anterior contiene las propiedades promocionadas que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] examina el serializador con el fin de serializar un mensaje XML en un mensaje de archivo sin formato de HL7.  
  
    Continúe con [paso 13: crear y configurar puertos](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)