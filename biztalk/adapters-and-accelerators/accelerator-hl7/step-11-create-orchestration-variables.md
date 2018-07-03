---
title: 'Paso 11: Creación de Variables de orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfe49f533989e339e6eb4318460a444ed0d8b741
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991165"
---
# <a name="step-11-create-orchestration-variables"></a>Paso 11: Creación de Variables de orquestación
En este paso, creará las variables de orquestación de las instancias de mensajes enviados y recibidos por la orquestación.  
  
 El Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) serializador espera los siguientes nombres de elemento. Si crea un mensaje de varias partes con otros nombres de elemento, el serializador rechaza el mensaje. Los nombres de partes de mensaje son:  
  
- MSHSegment  
  
- BodySegments  
  
- Segmentos de Z  
  
  La siguiente es información importante sobre los elementos del segmento de Z:  
  
- Todos los mensajes contienen tres partes como se describió anteriormente, independientemente de si un segmento de Z está presente o no.  
  
- Utilice una parte del segmento de Z para que contenga los datos de la instancia de mensaje, que es final y no está definido en el esquema (que también significa que no se ha declarado).  
  
- Si no hay ningún dato no declarado, la parte del segmento Z está en blanco. No ve los elementos del segmento Z al ver el XML intermedio en el asignador de BizTalk; Sin embargo, en la herramienta de mantenimiento de BizTalk y el seguimiento de actividad (HAT), verá tres partes a cada mensaje.  
  
### <a name="to-create-orchestration-variables"></a>Para crear variables de orquestación  
  
1. Haga clic en el **Vista orquestación** ficha junto a la **el Explorador de soluciones** pestaña debajo el Explorador de soluciones.  
  
2. En el **Vista orquestación** panel, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3. Cambiar el **identificador** propiedad en el **propiedades** panel para **DoorbellInputMessage**y, a continuación, presione **ENTRAR**.  
  
4. En el **propiedades** panel, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7_Project.Doorbell**.  
  
5. Repita los pasos 2 y 3 para crear otro mensaje denominado **DoorbellOutputMessage**.  
  
6. En el **propiedades** panel, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.  
  
7. En el **Vista orquestación** panel, expanda el **tipos** nodo. Haga clic en **tipos de mensaje de varias partes**y, a continuación, haga clic en **nuevo tipo de mensaje de varias partes**.  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] crea un nuevo tipo de mensaje denominado **MultipartType_1** junto con un nuevo mensaje denominado **MessagePart_1**.  
  
8. Haga clic en **MultipartType_1**y en el **propiedades** ventana, haga clic en **identificador** y escriba el nuevo nombre **DoorbellFinalMessageType**, y, a continuación, presione **ENTRAR**.  
  
   > [!NOTE]
   >  En los pasos 9 a 15, creará las partes del mensaje de varias partes. Es importante el orden en que se crean las partes de un mensaje de varias partes. Cree siempre el encabezado, el cuerpo y, luego, el segmento de Z.  
  
   > [!NOTE]
   >  Una vez que ha creado y denominado las partes del mensaje, no cambie el nombre de ellos. Si es necesario, elimine la antigua parte del cuerpo y cree un nuevo elemento de cuerpo con un nuevo nombre.  
  
9. En el **tipos** ventana, en **tipos de mensaje de varias partes**, expanda **DoorbellFinalMessageType**y, a continuación, haga clic en **MessagePart_1**. En el **propiedades** panel, escriba **MSHSegment** para **identificador**y, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo**, expanda **clases .NET**y, a continuación, haga clic en \< **seleccionar ensamblados de referencia de\>**.  
  
10. En el **Seleccionar tipo de artefacto** cuadro de diálogo, en el panel izquierdo, haga clic en **System.Xml**. En el panel derecho, haga clic en **XmlDocument**y, a continuación, haga clic en **Aceptar**.  
  
11. En la ventana Vista orquestación, haga clic en **DoorbellFinalMessageType**y, a continuación, haga clic en **nueva parte de mensaje** crear MessagePart_1.  
  
12. En el **propiedades** ventana, escriba **BodySegments** para **identificador**y, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo**, expanda **esquemas**y, a continuación, seleccione **BTAHL7Schemas.ADT_A04_22_GLO_DEF** en la lista desplegable.  
  
13. Establecer el **parte del cuerpo del mensaje** propiedad **True**.  
  
14. En el **Vista orquestación** ventana, haga clic en **DoorbellFinalMessageType**y, a continuación, haga clic en **nueva parte de mensaje**.  
  
15. En el **propiedades** panel, escriba **ZSegments** para **identificador**y, a continuación, presione **ENTRAR**. Haga clic en **tipo**, expanda **clases .NET**y, a continuación, haga clic en **System.String** en la lista desplegable.  
  
    > [!NOTE]
    >  Usa **System.String** para Z segmentos parte del mensaje, porque un segmento Z contiene datos de cadena que no deben ser conformes a un esquema.  
  
16. En el **Vista orquestación** ventana, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
17. En el **propiedades** ventana, escriba **DoorbellFinalMessage** para **identificador**y, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo de mensaje**, expanda **tipos de mensaje de varias partes**y, a continuación, haga clic en **BTAHL7_Project.DoorbellFinalMessageType**.  
  
18. En el **Vista orquestación** ventana, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.  
  
19. En el **propiedades** panel, escriba **HeaderInfo** para **identificador**, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo**, haga doble clic en \< **clase .NET\>**.  
  
20. En el **Seleccionar tipo de artefacto** ventana, en el panel izquierdo, haga clic en **System.Xml**. En el panel derecho, haga clic en **XmlDocument**y, a continuación, haga clic en **Aceptar**.  
  
21. En el **archivo** menú, haga clic en **guardar todo**.  
  
    Continúe con [paso 12: configurar formas de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)