---
title: 'Paso 3: Crear e implementar un Project_hl7_main de eventos (mensaje) desencadenador | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 263d131fffbeec996904d303be3fecd1eacf40c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013173"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a>Paso 3: Crear e implementar un Project_hl7_main de desencadenador eventos (mensaje)
En este paso, creará el esquema utilizado por un mensaje de evento de desencadenador. Por ejemplo, el sistema de admisión de descarga y la transferencia (ADT) envía un mensaje para el sistema de información de Hospital (HIS). Utilice este esquema para definir el formato del mensaje.  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>Para crear el proyecto para el mensaje de evento de desencadenador  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.  
  
3. En el **plantillas** lista, haga clic en **proyecto vacío de BTAHL7**.  
  
4. En el **nombre** , escriba **BTAHL7V24Body proyecto**y, a continuación, haga clic en **Aceptar**.  
  
5. En el Explorador de soluciones, bajo el nodo para el nuevo **BTAHL7V24Body** del proyecto, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
6. En el cuadro de diálogo Agregar referencia, haga clic en el **proyectos** ficha, seleccione **Interrogative_24Schemas**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="step-3a-add-the-schemas"></a>Paso 3A: agregar los esquemas  
 Utilice el procedimiento siguiente para agregar los nuevos esquemas al proyecto.  
  
#### <a name="to-add-the-schemas-to-the-project"></a>Para agregar los esquemas al proyecto  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7V24Body proyecto**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento, expanda **elementos de proyecto de BizTalk**y, a continuación, haga doble clic en **BTAHL7 esquemas** en el panel derecho.  
  
3.  En el cuadro de diálogo Selector de esquema HL7, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Clase de mensaje**|Mantener **V2.X** seleccionado.|  
    |**Versión**|Seleccione **2.4**.|  
    |**Tipo de mensaje**|Seleccione **QRY**.|  
    |**Evento de desencadenador**|Seleccione **Q01**.|  
  
4.  Haga clic en **finalizar** para agregar el esquema al proyecto.  
  
     Esto crea el archivo de esquema de consulta QRY_Q01_24_GLO_DEF.xsd.  
  
    > [!NOTE]
    >  No cierre el cuadro de diálogo Selector de esquema HL7.  
  
5.  En el cuadro de diálogo Selector de esquema HL7, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Clase de mensaje**|Mantener **V2.X** seleccionado.|  
    |**Versión**|Seleccione **2.4**.|  
    |**Tipo de mensaje**|Seleccione **DSR**.|  
    |**Evento de desencadenador**|Seleccione **Q01**.|  
  
6.  Haga clic en **finalizar** para agregar el esquema al proyecto.  
  
     Esto crea el archivo de esquema de respuesta DSR_Q01_24_GLO_DEF.xsd.  
  
7.  Haga clic en **cancelar** para cerrar el **Selector de esquema HL7** cuadro de diálogo.  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>Paso 3B: asignar una clave segura para el ensamblado e implementar  
 Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>Para asignar una clave segura e implementar el ensamblado  
  
1. En el Explorador de soluciones, haga clic en **BTAHL7V24Body** del proyecto y, a continuación, haga clic en **propiedades**.  
  
2. En el **páginas de propiedades BTAHL7V24Body** cuadro de diálogo, haga clic en **ensamblado**.  
  
3. En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
4. En el **archivo clave de ensamblado** cuadro de diálogo, vaya a \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador HL7\SDK\Interrogative tutorial, haga clic en **key.snk**y, a continuación, haga clic en **abierto**.  
  
5. En el **páginas de propiedades BTAHL7V24Body** cuadro de diálogo, haga clic en **Aceptar** para guardar los cambios.  
  
6. En el Explorador de soluciones, haga clic en **BTAHL7V24Body proyecto**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece un mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
   Continúe con [paso 4: crear el puerto de recepción para aceptar mensajes de consulta ADT](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md).