---
title: "Campo de MSH reemplazará | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- headers, overriding
- MSH Map tab [Configuration Explorer]
- headers, MSH Map tab
- messages, message headers
ms.assetid: f5b2c820-57e7-4a56-9d9f-713563bd7335
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82603ded113fa25c839661fb7874d97f8b3bb074
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msh-field-overrides"></a>Invalidaciones de campo de MSH
Cada mensaje HL7 tiene un encabezado del mensaje. Usar [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], puede reemplazar cualquier valor de encabezado de mensaje en función de sus necesidades de negocio. Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **MSH mapa** tab para manualmente invalidar los valores de encabezado de mensaje sin utilizar ninguna asignación o una orquestación.  
  
## <a name="configuring-msh-field-overrides"></a>Invalida la configuración de campo de MSH  
 Usa el **MSH mapa** pestaña [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (en el nivel superior **partes** pestaña) para configurar invalidaciones de campo de MSH. Cuando escriba un valor para un campo de MSH mediante esta pestaña, ese valor reemplaza al valor de MSH existente en una salida HL7 mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía a la entidad seleccionada. Puede escribir nuevos valores para muchos campos de MSH, o seleccionar valores de una lista desplegable de los campos MSH15 y MSH16.  
  
 La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **MSH mapa** ficha.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")  
  
 Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración y configure MSH campo invalidaciones.  
  
#### <a name="to-open-btahl7-configuration-explorer"></a>Para abrir el Explorador de configuración de BTAHL7  
  
-   Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.  
  
#### <a name="to-configure-msh-field-overrides"></a>Para configurar invalidaciones de campo de MSH  
  
1.  En el Explorador de configuración de BTAHL7, en la **MSH mapa** ficha, realice lo siguiente:  
  
    > [!NOTE]
    >  Para invalidar el valor existente en null, escriba  **\\** .  
  
    |Use|Para|  
    |--------------|----------------|  
    |**MSH.3**|Campo de tipo de mensaje invalida para este encabezado de mensaje.|  
    |**MSH.4**|Campo de tipo de mensaje invalida para este encabezado de mensaje.|  
    |**MSH.5**|Campo de tipo de mensaje invalida para este encabezado de mensaje.|  
    |**MSH.6**|Campo de tipo de mensaje invalida para este encabezado de mensaje.|  
    |**MSH.8**|Campo de tipo de mensaje invalida para este encabezado de mensaje.|  
    |**MSH.9**|Invalida el campo de tipo de mensaje para este encabezado de mensaje|  
    |**MSH.12**|Campo de tipo de mensaje invalida para este encabezado de mensaje.|  
    |**MSH.15**|Seleccione una de las siguientes opciones para un reemplazo de confirmación para el tipo de confirmación de aceptación:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar siempre Aceptar confirmaciones.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de Aceptar.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de Aceptar después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar a Aceptar confirmaciones solo si se produce un error.|  
    |**MSH.16**|Seleccione una de las siguientes opciones para un reemplazo de confirmación para el tipo de confirmación de la aplicación:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar confirmaciones de aplicación siempre.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de aplicación nunca.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de aplicación después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar confirmaciones de aplicación sólo si se produce un error.|  
  
2.  Haga clic en **Guardar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de registro](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [Procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
[Registro operativo, el procesamiento por lotes de mensajes, validación y configuración de asknowledgment](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)