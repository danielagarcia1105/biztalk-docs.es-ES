---
title: 'Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje) | Microsoft Docs'
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
ms.openlocfilehash: deb9d6160fc0b094f0af6f75ab4ab8e5be22462c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998693"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a>Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)
En este paso, creará el esquema para el mensaje de evento de desencadenador. Por ejemplo, podría ser el sistema de admisión de descarga y la transferencia (ADT) que envía un mensaje para el sistema de información de Hospital (HIS). Necesita este esquema para definir el formato del mensaje.  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>Para crear el proyecto para el mensaje de evento de desencadenador  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**, a continuación, haga clic en **proyecto**.  
  
2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.  
  
3. En la sección plantillas, haga clic en **proyecto vacío de BTAHL7**, en el **nombre** , escriba **BTAHL7V231Body proyecto**y, a continuación, haga clic en **Aceptar**.  
  
4. En el Explorador de soluciones, bajo el nodo para el nuevo proyecto, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
5. En el cuadro de diálogo Agregar referencia, en el **proyectos** ficha, seleccione **BTAHL7V231Common Project1**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="step-3a-add-the-schema"></a>Paso 3A: agregar el esquema  
 Use el procedimiento siguiente para agregar el nuevo esquema al proyecto.  
  
#### <a name="to-add-the-schema-to-the-project"></a>Para agregar el esquema al proyecto  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En Agregar nuevo elemento cuadro de diálogo, en el **categorías** sección, expanda **elementos de proyecto de BizTalk**y, a continuación, seleccione **BTAHL7 esquemas**.  
  
3.  En la sección de plantillas, haga doble clic en **BTAHL7 esquemas**.  
  
4.  En el cuadro de diálogo Selector de esquema HL7, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Clase de mensaje**|Deje el valor predeterminado de **V2.X** seleccionado.|  
    |**Versión**|Seleccione **2.3.1**.|  
    |**Tipo de mensaje**|Seleccione **ADT**.|  
    |**Evento de desencadenador**|Seleccione **A03**.|  
  
5.  Haga clic en **finalizar** para agregar el esquema al proyecto.  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>Paso 3B: asignar una clave segura para el ensamblado e implementar  
 Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>Para asignar una clave segura e implementar el ensamblado  
  
1. En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**y, a continuación, haga clic en **propiedades**.  
  
2. En la página de páginas de propiedades del proyecto, haga clic en **ensamblado**.  
  
3. En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
4. En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End a otro tutorial, haga clic en **key.snk**y, a continuación, haga clic en **abierto**.  
  
5. En el cuadro de diálogo páginas de propiedades del proyecto, haga clic en **Aceptar** para guardar los cambios.  
  
6. En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece un mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
   Continúe con [paso 4: crear el puerto de recepción para aceptar ADT ^ mensajes A03 desde sistemas ADT mediante el adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).