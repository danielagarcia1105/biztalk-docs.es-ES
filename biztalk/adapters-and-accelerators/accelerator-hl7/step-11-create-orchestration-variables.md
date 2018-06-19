---
title: 'Paso 11: Crear Variables de orquestación | Documentos de Microsoft'
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
ms.openlocfilehash: a640b938628ebe3dcd6757e3f6fdfd7b1108880d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962250"
---
# <a name="step-11-create-orchestration-variables"></a>Paso 11: Crear Variables de orquestación
En este paso, creará las variables de orquestación de las instancias de mensajes enviados y recibidos por la orquestación.  
  
 El Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) serializador espera los siguientes nombres de elemento. Si crea un mensaje de varias partes con ningún otro nombre de parte, el serializador rechaza el mensaje. Los nombres de parte de mensaje son:  
  
-   MSHSegment  
  
-   BodySegments  
  
-   Segmentos de Z  
  
 La siguiente es información importante acerca de los elementos del segmento de Z:  
  
-   Todos los mensajes contienen tres partes como se describió anteriormente, independientemente de si está presente un segmento de Z o no.  
  
-   Usar un elemento de segmento de Z para contener los datos de la instancia de mensaje, que es final y no está definido en el esquema (lo que también significa que no se ha declarado).  
  
-   Si no hay ningún dato no declarado, la parte del segmento de Z está en blanco. No ve los elementos del segmento de Z al ver el XML intermedio en el asignador de BizTalk; Sin embargo, en la herramienta de mantenimiento de BizTalk y seguimiento de actividad (HAT), verá tres partes para cada mensaje.  
  
### <a name="to-create-orchestration-variables"></a>Para crear variables de orquestación  
  
1.  Haga clic en el **Vista orquestación** ficha junto a la **el Explorador de soluciones** ficha bajo el Explorador de soluciones.  
  
2.  En el **Vista orquestación** panel, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Cambiar el **identificador** propiedad en el **propiedades** panel para **DoorbellInputMessage**y, a continuación, presione **ENTRAR**.  
  
4.  En el **propiedades** panel, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7_Project.Doorbell**.  
  
5.  Repita los pasos 2 y 3 para crear otro mensaje denominado **DoorbellOutputMessage**.  
  
6.  En el **propiedades** panel, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.  
  
7.  En el **Vista orquestación** panel, expanda el **tipos** nodo. Haga clic en **tipos de mensaje de varias partes**y, a continuación, haga clic en **nuevo tipo de mensaje de varias partes**.  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]crea un nuevo tipo de mensaje denominado **MultipartType_1** junto con un nuevo mensaje denominado **MessagePart_1**.  
  
8.  Haga clic en **MultipartType_1**y en el **propiedades** ventana, haga clic en **identificador** y escriba el nuevo nombre **DoorbellFinalMessageType**, y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  En los pasos 9 a 15, creará las partes del mensaje de varias partes. Es importante el orden en que se crean las partes de un mensaje de varias partes. Cree siempre el encabezado, el cuerpo y, luego, el segmento de Z.  
  
    > [!NOTE]
    >  Una vez que ha creado y denominado las partes del mensaje, no cambie el nombre de ellos. Si es necesario, elimine la antigua parte del cuerpo y crear un nuevo elemento de cuerpo con un nuevo nombre.  
  
9. En el **tipos** ventana, en **tipos de mensaje de varias partes**, expanda **DoorbellFinalMessageType**y, a continuación, haga clic en **MessagePart_1**. En el **propiedades** panel, escriba **MSHSegment** para **identificador**y, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo**, expanda **clases .NET**y, a continuación, haga clic en \< **seleccionar ensamblados de referencia de\>**.  
  
10. En el **Seleccionar tipo de artefacto** cuadro de diálogo, en el panel izquierdo, haga clic en **System.Xml**. En el panel derecho, haga clic en **XmlDocument**y, a continuación, haga clic en **Aceptar**.  
  
11. En la ventana Vista orquestación, haga clic en **DoorbellFinalMessageType**y, a continuación, haga clic en **nueva parte de mensaje** para crear MessagePart_1.  
  
12. En el **propiedades** ventana, escriba **BodySegments** para **identificador**y, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo**, expanda **esquemas**y, a continuación, seleccione **BTAHL7Schemas.ADT_A04_22_GLO_DEF** en la lista desplegable.  
  
13. Establecer el **parte del cuerpo del mensaje** propiedad **True**.  
  
14. En el **Vista orquestación** ventana, haga clic en **DoorbellFinalMessageType**y, a continuación, haga clic en **nueva parte de mensaje**.  
  
15. En el **propiedades** panel, escriba **ZSegments** para **identificador**y, a continuación, presione **ENTRAR**. Haga clic en **tipo**, expanda **clases .NET**y, a continuación, haga clic en **System.String** en la lista desplegable.  
  
    > [!NOTE]
    >  Usa **System.String** para la Z segmentos parte del mensaje, porque un segmento de Z contiene datos de cadena que no es necesario para que se ajuste a un esquema.  
  
16. En el **Vista orquestación** ventana, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
17. En el **propiedades** ventana, escriba **DoorbellFinalMessage** para **identificador**y, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo de mensaje**, expanda **tipos de mensaje de varias partes**y, a continuación, haga clic en **BTAHL7_Project.DoorbellFinalMessageType**.  
  
18. En el **Vista orquestación** ventana, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.  
  
19. En el **propiedades** panel, escriba **HeaderInfo** para **identificador**, a continuación, presione **ENTRAR**. En la lista desplegable para **tipo**, haga doble clic en \< **clase .NET\>**.  
  
20. En el **Seleccionar tipo de artefacto** ventana, en el panel izquierdo, haga clic en **System.Xml**. En el panel derecho, haga clic en **XmlDocument**y, a continuación, haga clic en **Aceptar**.  
  
21. En el **archivo** menú, haga clic en **guardar todo**.  
  
 Continúe con [paso 12: configurar formas de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)