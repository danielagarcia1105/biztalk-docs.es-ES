---
title: "Configuración de la validación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108f13dfbdc7b42027f57e70d913202b4d4e3100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validation-settings"></a>Configuración de la validación
Usar [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], puede validar los mensajes en el estándar HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]garantiza que los mensajes que envíe o reciba un segmento de estructura y el cuerpo de mensaje que se ajusta al estándar HL7. También puede validar HL7 admitidas tipos de datos personalizados y permitir que los delimitadores finales. Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **validación** ficha para configurar la validación.  
  
## <a name="configuring-validation-settings"></a>Configuración de opciones de validación  
 Usa el **validación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (en el nivel superior **partes** pestaña) para configurar los valores de validación. Puede seleccionar los siguientes tipos de validación:  
  
-   Sintaxis, la estructura y la validación de esquema en segmentos de cuerpo, tomando como base el esquema de mensaje  
  
-   Validación de estándar HL7 en tipos de datos personalizados (DT, TS, TM y TN)  
  
-   Validación de los delimitadores de campo (se permiten los delimitadores finales)  
  
 Mediante esta pestaña, también puede establecer el espacio de nombres de esquema utilizado para la validación en los mensajes para esta entidad.  
  
 La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **validación** ficha.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
Pestaña validación de explorador de configuración de BTAHL7  
  
 Utilice los procedimientos siguientes para configurar los valores de validación.  
  
#### <a name="to-open-btahl7-configuration-explorer"></a>Para abrir el Explorador de configuración de BTAHL7  
  
-   Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.  
  
#### <a name="to-configure-validation-settings"></a>Procedimiento para configurar la configuración de validación  
  
1.  En el Explorador de configuración de BTAHL7 en el **validación** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Validar los segmentos de cuerpo**|Seleccione esta opción para realizar la validación del esquema, la estructura y la sintaxis.|  
    |**Validar el tipo de datos personalizados**|Seleccione esta opción para realizar una validación estándar HL7 en DT, TS, TM y TN tipos de datos personalizados.|  
    |**Permitir finales delimitadores (separadores)**|Seleccione esta opción para habilitar los delimitadores finales de campo en instancias de mensaje.|  
    |**Namespace de esquema**|Escriba la ubicación del espacio de nombres de esquema. El valor predeterminado es http://microsoft.com/HealthCare/HL7/2X.|  
  
2.  Haga clic en **Guardar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de registro](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [Configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)   
[Registro operativo, el procesamiento por lotes de mensajes, validación y configuración de asknowledgment](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)