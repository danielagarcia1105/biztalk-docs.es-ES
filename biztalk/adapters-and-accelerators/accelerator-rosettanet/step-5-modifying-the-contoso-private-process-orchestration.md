---
title: "Paso 5: Modificar la orquestación de procesos privados de Contoso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a222ee518cf0555de60094411df73bf5a5d486a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a>Paso 5: Modificar la orquestación de procesos privados de Contoso
En este paso, modificará la orquestación de procesos privados para integrarse con el sistema de planeamiento de recursos empresariales (ERP) de Contoso. El sistema ERP de Contoso usa esquemas definidos internamente para la disponibilidad y el precio del producto. Si personaliza el proceso privado para el 3A2 - precio y el proceso de interfaz de socio (PIP) disponibilidad, podrá integrar con el sistema ERP mediante el uso de información de esquema de asignación.  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a>Para agregar una referencia a los ensamblados de Contoso PriceAndAvailability y Rnpip  
  
1.  Con la solución de Contoso que se muestra en el Explorador de soluciones, haga clic en el **PrivateResponder** del proyecto y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, haga clic en **Examinar**. Mover a  *\<unidad\>*: \Program BizTalk \<versión\> Accelerator for RosettaNet\Bin carpeta y, a continuación, seleccione los ensamblados siguientes**:**  
  
    -   Microsoft.Solutions.BTARN.CommonTypes.dll  
  
    -   Microsoft.Solutions.BTARN.ConfigurationManager.dll  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas.dll  
  
    -   Microsoft.Solutions.BTARN.PublicResponder.dll  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll  
  
    -   Microsoft.Solutions.BTARN.Shared.dll  
  
    -   Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll  
  
3.  Haga clic en **Agregar**.  
  
4.  En el cuadro de diálogo Agregar referencia, haga clic en el **proyectos** ficha, seleccione la **ContosoPriceAndAvailability** y **HeaderHelper** proyectos y, a continuación, haga clic en  **Agregar**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  En el cuadro de diálogo del entorno de desarrollo de Microsoft, haga clic en **Aceptar**.  
  
### <a name="to-create-new-message-types"></a>Para crear nuevos tipos de mensaje  
  
1.  En el Explorador de soluciones, haga doble clic en el **PrivateResponder** orquestación para abrirlo.  
  
2.  En el Explorador de soluciones, haga clic en **Vista orquestación**.  
  
3.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  En la ventana Propiedades, en la **identificador** , escriba **PIP3A2RequestMessage**.  
  
5.  En el **tipo de mensaje** , haga clic en la flecha de lista desplegable, expanda **esquemas**y, a continuación, seleccione  **\<seleccionar del ensamblado mencionado\>**.  
  
6.  En el cuadro Seleccionar Typedialog de artefacto, seleccione **Microsoft.Solutions.BTARN.Schemas.RNPIPs** en el panel izquierdo, seleccione **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3** en el panel derecho, y a continuación, haga clic en **Aceptar**.  
  
7.  Repita los pasos del 3 al 6 para crear todos los tipos de mensaje para la solución con la siguiente información:  
  
    |Identificador|Ensamblado|Tipo de mensaje|  
    |----------------|--------------|------------------|  
    |PIP3A2ResponseMessage|Microsoft.Solutions.BTARN.<br />Schemas.RNPips|_3A2PriceAndAvailability<br />ResponseMessageGuideline_v1_3|  
    |Contoso3A2ResponseMessage|ContosoPriceAndAvailability|rootPriceResponse|  
    |Contoso3A2RequestMessage|ContosoPriceAndAvailability|rootPriceRequest|  
  
8.  Ha terminado de crear los tipos de mensaje para la solución.  
  
### <a name="to-create-new-variables"></a>Para crear nuevas variables  
  
1.  En Vista orquestación, haga clic en **Variables,** y, a continuación, haga clic en **nueva Variable**.  
  
2.  En la ventana Propiedades, en la **identificador** , escriba **contosoResponseXML**.  
  
3.  En el **tipo** cuadro, seleccione  **\<clase .NET\>**  en la lista desplegable.  
  
4.  En el artefacto seleccione escriba cuadro de diálogo, en el panel izquierdo, bajo el **proyecto actual** y **referencias** nodos, seleccione **System.Xml**, seleccione  **XmlDocument** en la lista en el panel derecho y, a continuación, haga clic en **Aceptar**.  
  
5.  En **Vista orquestación**, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.  
  
6.  En la ventana Propiedades, en la **identificador** , escriba **submitMessage**.  
  
7.  En el **tipo** cuadro, seleccione  **\<clase .NET\>**  en la lista desplegable.  
  
8.  En el cuadro de diálogo Seleccionar tipo de artefacto, en el panel izquierdo, expanda **proyecto actual** y **referencias** nodos, seleccione **Microsoft.Solutions.BTARN.Shared**, seleccione  **SubmitRNIF** en la lista en el panel derecho y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-change-the-orchestration-filter-expression"></a>Para modificar la expresión de filtro de orquestación  
  
1.  En el Diseñador de orquestaciones, seleccione la **ReceiveFromPublicProcessResponder** forma.  
  
2.  En la ventana Propiedades, en la **expresión de filtro** cuadro, haga clic en el cuadro de valor y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) para abrir el cuadro de diálogo Expresión de filtro.  
  
3.  En el cuadro de diálogo Expresión de filtro, en la **Group By** sección, haga clic en el **o** valor en la primera línea y, a continuación, seleccione **AND** en la lista desplegable.  
  
4.  En el cuadro de diálogo Expresión de filtro, haga clic en **haga clic aquí para agregar una nueva fila**y, a continuación, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable.  
  
5.  En la misma fila, haga clic en **valor**y, a continuación, escriba en **"3A2"**.  
  
6.  En la misma fila, haga clic en **AND** en el **Group By** cuadro y, a continuación, seleccione **o** en la lista desplegable.  
  
7.  En el cuadro de diálogo Expresión de filtro, seleccione la fila que acaba de crear y, a continuación, haga clic en el botón de flecha arriba una vez para mover la fila de una sola vez.  
  
8.  Haga clic en **haga clic aquí para agregar una nueva fila**y, a continuación, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable.  
  
9. En la misma fila, haga clic en **valor**y, a continuación, escriba en **"3A2"**.  
  
10. Haga clic en Aceptar.  
  
### <a name="to-modify-the-business-process-workflow"></a>Para modificar el flujo de trabajo del proceso de negocio  
  
1.  Arrastre un **asignación de mensajes** forma del cuadro de herramientas a la superficie de diseño y colóquelo bajo el **ReceiveFromPublicProcessResponder** forma. Seleccione el **ConstructMessage_1** forma a la que se creó y, en la **propiedades** ventana, en la **nombre** , escriba **ConstructPIP3A2RequestMessage** .  
  
2.  Arrastre un **transformar** dar forma a la superficie de diseño y colóquelo bajo el **ConstructPIP3A2RequestMessage** forma. Seleccione el **ConstructMessage_1** forma a la que se creó y, en la **propiedades** ventana, en la **nombre** , escriba **ConstructContoso3A2RequestMessage** .  
  
3.  Arrastre un **enviar** dar forma a la superficie de diseño y colóquelo bajo el **ConstructContoso3A2RequestMessage** forma.  
  
4.  Arrastre un **recepción** dar forma a la superficie de diseño y colóquelo bajo el **Send_1** forma.  
  
5.  En la superficie de diseño de orquestación, haga clic en un área vacía.  
  
6.  En la ventana Propiedades, seleccione la **tipo de transacción** propiedad y, a continuación, haga clic en **larga ejecución**.  
  
7.  Arrastre un **ámbito** dar forma a la superficie de diseño y colóquelo bajo el **Receive_1** forma.  
  
8.  En la ventana Propiedades, de la **tipo de transacción** lista desplegable de propiedades, seleccione **atómica** para el **ámbito** forma.  
  
9. Arrastre un **reglas de llamada** dar forma a la superficie de diseño y colóquela en la etiqueta que dice **coloca una forma en el cuadro de herramientas aquí** dentro de la **ámbito** forma. En la ventana de propiedades para el **reglas de llamada** forma, en la **nombre** , escriba **Execute3A2Vocabulary**.  
  
10. Arrastre un **transformar** dar forma a la superficie de diseño y colóquelo bajo el **Scope_1** forma. Haga clic en el **ConstructMessage_1** forma. En la ventana Propiedades, en la **nombre** , escriba **Construct3A2ResponseMessage**.  
  
11. Arrastre un **expresión** dar forma a la superficie de diseño y colóquelo bajo el **Construct3A2ResponseMessageTransform** forma.  
  
12. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo**, haga clic en **guardar todo** para guardar el proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Paso 6: Configuración de las formas de orquestación (Contoso)](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)