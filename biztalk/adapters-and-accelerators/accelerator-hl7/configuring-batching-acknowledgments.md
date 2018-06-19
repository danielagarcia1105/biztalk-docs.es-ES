---
title: Configurar el procesamiento por lotes de confirmaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
ms.assetid: f3529638-e036-4270-ae6d-1bdc3ef98727
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e6c9b3a6fadfcc0407c1b4fa206d0f966fa7dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962858"
---
# <a name="configuring-batching-acknowledgments"></a>Configurar confirmaciones de procesamiento por lotes
Usa [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Explorador de configuración para especificar las propiedades de confirmación de confirmaciones entrantes y generadas.  
  
### <a name="to-run-btahl7-configuration-explorer"></a>Para ejecutar el Explorador de configuración de BTAHL7  
  
-   Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
### <a name="to-configure-message-batching-acknowledgments"></a>Para configurar el procesamiento por lotes las confirmaciones de mensajes  
  
-   En el Explorador de configuración de BTAHL7, en la **Explorador de configuración de BTAHL7** cuadro de diálogo la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **confirmaciones** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipo de confirmación**|Seleccione una de las opciones siguientes:<br /><br /> -   **None**. Seleccione si no desea configurar las confirmaciones.<br />-   **OriginalMode**. Seleccione esta opción para configurar el **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** opciones solo.<br />-   **EnhancedMode**. Seleccione esta opción para configurar todas las opciones de confirmación disponibles.<br />-   **DeferredMode**. Seleccione esta opción para configurar el **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** opciones solo.<br />-   **StaticMode**. Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.|  
    |**Tipo de confirmación de aceptación de MSH 15**|Seleccione una de las opciones siguientes:<br /><br /> -   **AL**. Seleccione esta opción para enviar siempre acepta confirmaciones.<br />-   **NE**. Seleccione esta opción para no enviar nunca acepte confirmaciones.<br />-   **SU**. Seleccione esta opción para enviar acepta confirmaciones después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción para enviar acepta confirmaciones solo si se produce un error.|  
    |**Tipo de confirmación de aplicación 15 de MSH**|Seleccione una de las opciones siguientes:<br /><br /> -   **AL**. Seleccione esta opción para enviar siempre confirmaciones de aplicación.<br />-   **NE**. Seleccione esta opción para no enviar nunca confirmaciones de aplicación.<br />-   **SU**. Seleccione esta opción para enviar confirmaciones de aplicación después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción para enviar confirmaciones de aplicación sólo si se produce un error.|  
    |**MSH1: separador de campos**|Escriba un único carácter como separador de campos. El valor predeterminado es un carácter de barra vertical (**&#124;**), y los caracteres máximos permitidos es un carácter. Tenga en cuenta que si necesita modificar MSH1, a continuación, debe utilizar una orquestación que escribe el valor adecuado de MSH1 en el contexto del mensaje HL7. El serializador de BTAHL7 lee el valor desde el contexto y usa en el mensaje serializado.|  
    |**MSH2: codificación de caracteres**|Escribir caracteres únicos como los caracteres de codificación según el estándar HL7. El valor predeterminado son caracteres de codificación ^, ~, \\, y &. Los caracteres mínimos necesarios son dos caracteres y el máximo permitido son cuatro caracteres. Tenga en cuenta que si MSH2_3 o MSH2_4 (el escape y el subcomponente dinámicos delimitadores) no se especifican en el mensaje original, estos campos rellena automáticamente con el mensaje de confirmación (ACK). Por ejemplo, si el segmento de mensaje MSH original es `MSH&#124;^~&#124;`, donde se especifican solo los delimitadores de componente y la repetición, a continuación, el mensaje de confirmación rellena automáticamente este campo para incluir el componente tercero y cuarto como `MSH&#124;^~\&`, proporcionando que los valores de campo tenían no ya se ha configurado en la sección de confirmación en el Explorador de configuración de BTAHL7.|  
    |**MSH3**|Escriba los valores de campo para confirmaciones generados para la aplicación de envío. La longitud máxima permitida es de 180 caracteres colectivamente.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH5** los valores del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
    |**MSH5**|Escriba los valores de campo para confirmaciones generados para la aplicación de destino. La longitud máxima permitida es de 180 caracteres colectivamente.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH3** los valores del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
    |**MSH8: seguridad**|Escriba un carácter de seguridad opcional.|  
    |**MSH15: acepte el tipo de confirmación**|Seleccione una de las siguientes opciones para el tipo de confirmación de aceptación:<br /><br /> -   **AL**. Seleccione si desea enviar siempre Aceptar confirmaciones.<br />-   **NE**. Seleccione si no desea enviar nunca acepte confirmaciones.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de Aceptar después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar a Aceptar confirmaciones solo si se produce un error.|  
    |**Si se ejecuta correctamente**|Escriba el texto para confirmación estático para una entrega de mensajes correctos.|  
    |**En caso de error**|Escriba texto estático confirmación para la entrega de un mensaje sin éxito.|  
    |**Puerto de envío de enrutar confirmación para enviar una canalización de solicitudes y respuestas**|Seleccione esta opción para enviar un mensaje de confirmación sincrónico para la aplicación de LOB de origen. Esta opción solo está disponible en un puerto de envío de petición-respuesta.<br /><br /> Si no se selecciona esta opción, la canalización de recepción genera el mensaje de confirmación en función de la configuración de confirmación.|  
  
    > [!NOTE]
    >  Confirmaciones generadas para un mensaje por lotes con fragmentación desactivada contendrá MSH12.1 con valor 2.4. Puede modificar manualmente el número de versión mediante la aplicación de un mapa en la canalización de envío. Para obtener más información, consulte [crear y procesar confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración del procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)