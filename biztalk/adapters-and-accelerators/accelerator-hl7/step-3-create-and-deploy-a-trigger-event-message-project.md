---
title: 'Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49fd078f64cbd4163eef648f7a0d58fe6e8db6b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961282"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a>Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)
En este paso, creará el esquema para el mensaje de evento de desencadenador. Por ejemplo, es posible que el sistema de admisión de descarga y la transferencia (ADT) que envía un mensaje para el sistema de información de Hospital (HIS). Necesita este esquema para definir el formato del mensaje.  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>Para crear el proyecto para el mensaje de evento de desencadenador  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.  
  
3.  En la sección plantillas, haga clic en **proyecto vacío de BTAHL7**, en la **nombre** , escriba **BTAHL7V231Body proyecto**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de soluciones, bajo el nodo para el proyecto nuevo, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
5.  En el cuadro de diálogo Agregar referencia, en la **proyectos** ficha, seleccione **BTAHL7V231Common Proyecto1**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="step-3a-add-the-schema"></a>Paso 3A: agregue el esquema  
 Utilice el procedimiento siguiente para agregar el nuevo esquema al proyecto.  
  
#### <a name="to-add-the-schema-to-the-project"></a>Para agregar el esquema al proyecto  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En Agregar nuevo elemento cuadro de diálogo, en la **categorías** sección, expanda **elementos de proyecto de BizTalk**y, a continuación, seleccione **BTAHL7 esquemas**.  
  
3.  En la sección de plantillas, haga doble clic en **BTAHL7 esquemas**.  
  
4.  En el cuadro de diálogo Selector de esquema HL7, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Message (clase)**|Deje el valor predeterminado de **V2.X** seleccionado.|  
    |**Versión**|Seleccione **2.3.1**.|  
    |**Tipo de mensaje**|Seleccione **ADT**.|  
    |**Evento de desencadenador**|Seleccione **A03**.|  
  
5.  Haga clic en **finalizar** para agregar el esquema al proyecto.  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>Paso 3B: asignar una clave segura para el ensamblado e implementar  
 Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>Para asignar una clave segura e implementar el ensamblado  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**y, a continuación, haga clic en **propiedades**.  
  
2.  En la página de páginas de propiedades de proyecto, haga clic en **ensamblado**.  
  
3.  En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
4.  En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial HL7\SDK\End-to-End, haga clic en **key.snk**y, a continuación, haga clic en **abiertos**.  
  
5.  En el cuadro de diálogo páginas de propiedades de proyecto, haga clic en **Aceptar** para guardar los cambios.  
  
6.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece ningún mensaje de implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
 Continúe con [paso 4: crear el puerto de recepción para aceptar ADT ^ A03 mensajes desde sistemas ADT usa el adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).