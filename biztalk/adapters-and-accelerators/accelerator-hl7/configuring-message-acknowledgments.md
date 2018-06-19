---
title: Configurar confirmaciones de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- messages, acknowledgements
- configuring, acknowledgements
ms.assetid: 6ebcfc32-0a0b-4388-938f-6569a2014b91
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 339e80776dac32e25f96da5c62675f1a8d6075ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962578"
---
# <a name="configuring-message-acknowledgments"></a>Configurar confirmaciones de mensajes
Usa el [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] configuración explorador **confirmación** ficha para especificar las propiedades de confirmación de confirmaciones entrantes y generadas.  
  
 La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **confirmación** ficha.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-ack.gif "hl7_ops_ack")  
  
 Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración y configurar confirmaciones de mensaje.  
  
### <a name="to-open-btahl7-configuration-explorer"></a>Para abrir el Explorador de configuración de BTAHL7  
  
-   Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
### <a name="to-configure-message-acknowledgments"></a>Para configurar confirmaciones de mensajes  
  
1.  En el Explorador de configuración de BTAHL7, en la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **confirmaciones** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipo de confirmación**|Seleccione una de las opciones siguientes:<br /><br /> -   **None**. Seleccione esta opción si no desea configurar las confirmaciones.<br />-   **OriginalMode**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** opciones solo.<br />-   **EnhancedMode**. Seleccione esta opción para configurar todas las opciones de confirmación disponibles.<br />-   **DeferredMode**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** opciones solo.<br />-   **StaticMode**. Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.|  
    |**Tipo de confirmación de aceptación de MSH 15**|Seleccione una de las opciones siguientes:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar siempre Aceptar confirmaciones.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de Aceptar.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de Aceptar después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar a Aceptar confirmaciones solo si se produce un error.|  
    |**Tipo de confirmación de aplicación 16 de MSH**|Seleccione una de las opciones siguientes:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar confirmaciones de aplicación siempre.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de aplicación nunca.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de aplicación después de la transmisión correcta de un mensaje.<br /><br /> **ER**. Seleccione esta opción si desea enviar confirmaciones de aplicación sólo si se produce un error.|  
    |**MSH1: separador de campos**|Escriba un único carácter como separador de campos. El valor predeterminado es un carácter de barra vertical (**&#124;**), y los caracteres máximos permitidos es un carácter. Tenga en cuenta que si necesita modificar MSH1, a continuación, debe utilizar una orquestación que escribe el valor adecuado de MSH1 en el contexto del mensaje HL7. El serializador de BTAHL7 lee el valor desde el contexto y usa en el mensaje serializado.|  
    |**MSH2: codificación de caracteres**|Escribir caracteres únicos como los caracteres de codificación según el estándar HL7. El valor predeterminado son caracteres de codificación ^, ~, \\, y &. Los caracteres mínimos necesarios son dos caracteres y el máximo permitido son cuatro caracteres. Tenga en cuenta que si MSH2_3 o MSH2_4 (el escape y el subcomponente dinámicos delimitadores) no se especifican en el mensaje original, el mensaje de confirmación rellena automáticamente esos campos. Por ejemplo, si el segmento de mensaje MSH original es `MSH&#124;^~&#124;`, donde se especifican solo los delimitadores de componente y la repetición, a continuación, el mensaje de confirmación rellena automáticamente este campo para incluir el componente tercero y cuarto como `MSH&#124;^~\&` si estos valores no se configuraron en las secciones de confirmación en el Explorador de configuración de BTAHL7.|  
    |**MSH 3**|Escriba los valores de campo para confirmaciones generados para la aplicación de envío. La longitud máxima permitida de 180 caracteres colectivamente.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH5** valor del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
    |**MSH 5**|Escriba los valores de campo para confirmaciones generados para la aplicación de destino. La longitud máxima permitida de 180 caracteres colectivamente.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH3** valor del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
    |**MSH8: seguridad**|Escriba un carácter de seguridad opcional.|  
    |**9 DE MSH**|Escriba los valores de campo de tipo de mensaje de confirmaciones generado.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH9** valor del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
    |**MSH15: acepte el tipo de confirmación**|Seleccione una de las siguientes opciones para el tipo de confirmación de aceptación:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar siempre Aceptar confirmaciones.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de Aceptar.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de Aceptar después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar a Aceptar confirmaciones solo si se produce un error.|  
    |**Si se ejecuta correctamente**|Escriba el texto para una confirmación estático para una entrega de mensajes correctos.|  
    |**En caso de error**|Escriba el texto para una confirmación estático para la entrega de un mensaje sin éxito.|  
    |**Puerto de envío de enrutar confirmación para enviar una canalización de solicitudes y respuestas**|Seleccione esta opción para enviar un mensaje de confirmación sincrónico para la aplicación de LOB de origen. Esta opción solo está disponible en un puerto de envío de petición-respuesta.<br /><br /> Si no se selecciona esta opción, la canalización de recepción genera el mensaje de confirmación en función de la configuración de confirmación.|  
  
2.  Haga clic en **Guardar**.  
  
## <a name="see-also"></a>Vea también  
 [Opciones de configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)   
 [Configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)   
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)