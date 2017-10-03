---
title: 'Paso 3: Agregar un esquema de desencadenador de eventos (mensaje) | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4eed7ead2f0d50e7841ed6c39ffdcee86c6524f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-add-a-trigger-event-message-schema"></a>Paso 3: Agregar un esquema de desencadenador de eventos (mensaje)
En este paso, cree un nuevo proyecto basado en vacío [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] plantilla de proyecto. Para este proyecto, agregue el esquema que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usará para validar los mensajes del lote entrante (ADT ^ A03). Agregue una referencia al proyecto que contiene los esquemas comunes v2.3.1, asigne un nombre seguro al proyecto y, a continuación, implemente el proyecto.  
  
### <a name="to-add-the-project-containing-the-message-schema"></a>Para agregar el proyecto que contiene el esquema de mensaje  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
3.  En el **plantillas** sección, seleccione **proyecto vacío de BTAHL7**.  
  
4.  En el **nombre** cuadro, escriba **BTAHL7V231Body** como el nombre del proyecto.  
  
5.  En el **solución** cuadro, seleccione **agregar a solución**.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el Explorador de soluciones, bajo el nodo para el proyecto nuevo, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
8.  En el cuadro de diálogo Agregar referencia, en la **proyectos** , haga clic en **proyecto BTAHL7V231Common** en el **nombre del proyecto** columna, haga clic en **agregar**, y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-add-the-schema-to-the-project"></a>Para agregar el esquema al proyecto  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento, expanda **elementos de proyecto de BizTalk**y, a continuación, haga clic en **BTAHL7 esquemas**. En el **plantillas** panel, haga clic en **BTAHL7 esquemas**y, a continuación, haga clic en **agregar**.  
  
3.  En el **Selector de esquema HL7** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Message (clase)**|Mantener **V2.X** como seleccionado.|  
    |**Versión**|Seleccione **2.3.1**.|  
    |**Tipo de mensaje**|Seleccione **ADT**.|  
    |**Evento de desencadenador**|Seleccione **A03**.|  
  
4.  Haga clic en **crear** para agregar el esquema al proyecto, a continuación, haga clic en **cancelar** para cerrar el cuadro de diálogo. Tenga en cuenta que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se agrega el esquema ADT_A03_231_GLO_DEF.xsd al proyecto BTAHL7V231Body.  
  
### <a name="to-assign-a-strong-key-and-deploy"></a>Para asignar una clave segura e implementar  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body**y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo página de propiedades de BTAHL7V231Body, haga clic en **firma**.  
  
3.  Comprobar **firmar el ensamblado** casilla de verificación.  
  
4.  En **elegir un archivo de clave de nombre seguro** de lista desplegable de la lista, seleccione  **\<Examinar... >.**  
  
5.  Vaya a  **\<* unidad*>: \Batching Tutorial **, seleccione **key.snk**y, a continuación, haga clic en **abiertos**.  
  
6.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece ningún mensaje de successful-deploy, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
 Continúe con [paso 4: crear un puerto de recepción para aceptar el mensaje por lotes](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md).