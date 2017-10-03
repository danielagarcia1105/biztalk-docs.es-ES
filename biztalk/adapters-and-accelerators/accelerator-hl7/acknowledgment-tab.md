---
title: "Ficha de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.tab.acknowledgement
helpviewer_keywords:
- acknowledgements, configuring
- Acknowledgement tab [Configuration Explorer]
- configuring, acknowledgements
ms.assetid: f00d698c-1a33-4885-853f-c6b58d49d937
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28dcf3d0faee6ebf37a827f3773f33b955ce5447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-tab"></a>Ficha de confirmación
Usa el **confirmación** ficha para especificar las propiedades de confirmación de confirmaciones entrantes y generadas.  
  
 En el **Explorador de configuración de BTAHL7** cuadro de diálogo, en la **confirmaciones** ficha, realice lo siguiente:  
  
|Use|Para|  
|--------------|----------------|  
|**Tipo de confirmación**|Seleccione una de las opciones siguientes:<br /><br /> -   **None**. Seleccione esta opción si no desea configurar las confirmaciones.<br />-   **OriginalMode**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**y el **MSH8 – seguridad** opciones solo.<br />-   **EnhancedMode**. Seleccione esta opción para configurar todas las opciones de confirmación disponibles.<br />-   **DeferredMode**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**y el **MSH8 – seguridad** opciones solo.<br />-   **StaticMode**. Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.|  
|**Tipo de confirmación de aceptación de MSH 15**|Seleccione una de las opciones siguientes:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar siempre Aceptar confirmaciones.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de Aceptar.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de Aceptar después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar a Aceptar confirmaciones solo si se produce un error.|  
|**Tipo de confirmación de aplicación 16 de MSH**|Seleccione una de las opciones siguientes:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar confirmaciones de aplicación siempre.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de aplicación nunca.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de aplicación después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar confirmaciones de aplicación sólo si se produce un error.|  
|**MSH1: separador de campos**|Escriba un único carácter como separador de campos. El valor predeterminado es **&#124;**, y los caracteres máximos permitidos es un carácter. Tenga en cuenta que si necesita modificar MSH1, a continuación, debe utilizar una orquestación que escribe el valor adecuado de MSH1 en el contexto del mensaje HL7. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador lee el valor desde el contexto y se usa en el mensaje serializado.|  
|**MSH2: codificación de caracteres**|Escriba los caracteres únicos para los caracteres de codificación según las especificaciones de HL7. El valor predeterminado son caracteres de codificación ^, ~, \\, y &. Los caracteres mínimos necesarios son dos caracteres y el máximo permitido son cuatro caracteres. Tenga en cuenta que si MSH2_3 o MSH2_4 (el escape y el subcomponente dinámicos delimitadores) no se especifican en el mensaje original, el mensaje de confirmación rellena automáticamente esos campos. Por ejemplo, si el segmento de mensaje MSH original es `MSH&#124;^~&#124;`, donde se especifican solo los delimitadores de componente y la repetición, a continuación, el mensaje de confirmación rellena automáticamente este campo para incluir el componente tercero y cuarto como `MSH&#124;^~\&` si estos valores no se configuraron en las secciones de confirmación de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.|  
|**MSH 3**|Escriba los valores de campo para confirmaciones generados para la aplicación de envío. La longitud máxima permitida es de 180 caracteres colectivamente.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH5** los valores del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
|**MSH 5**|Escriba los valores de campo para confirmaciones generados para la aplicación de destino. La longitud máxima permitida es de 180 caracteres colectivamente.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH3** los valores del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
|**MSH8: seguridad**|Escriba un carácter de seguridad opcional.|  
|**9 DE MSH**|Escriba los valores de campo de tipo de mensaje de confirmaciones generado.<br /><br /> Cuando no se configura, confirmaciones generadas contienen entrantes **MSH9** los valores del mensaje. **Nota:** esta opción solo se aplica a mensajes 2.X. **Nota:** para invalidar el valor existente en null, escriba  **\\** .|  
|**MSH15: acepte el tipo de confirmación**|Seleccione una de las siguientes opciones para el tipo de confirmación de aceptación:<br /><br /> -   **AL**. Seleccione esta opción si desea enviar siempre Aceptar confirmaciones.<br />-   **NE**. Seleccione esta opción si no desea enviar confirmaciones de Aceptar.<br />-   **SU**. Seleccione esta opción si desea enviar confirmaciones de Aceptar después de la transmisión correcta de un mensaje.<br />-   **ER**. Seleccione esta opción si desea enviar a Aceptar confirmaciones solo si se produce un error.|  
|**Si se ejecuta correctamente**|Escriba el texto para una confirmación estático para una entrega de mensajes correctos.|  
|**En caso de error**|Escriba el texto para una confirmación estático para la entrega de un mensaje sin éxito.|  
|**Puerto de envío de enrutar confirmación para enviar una canalización de solicitudes y respuestas**|Seleccione esta opción para enviar un mensaje de confirmación sincrónico para la aplicación de LOB de origen. Esta opción solo está disponible en un puerto de envío de petición-respuesta.<br /><br /> Si no se selecciona esta opción, la canalización de recepción genera el mensaje de confirmación en función de la configuración de confirmación.|