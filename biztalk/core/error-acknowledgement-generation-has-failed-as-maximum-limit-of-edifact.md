---
title: "Generación de confirmación; error porque se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración global | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6adc02d7-ebc4-4da0-a19a-3a423d63499d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 252f0fd6dbe77eb83018e2bb34d4a6cd07cdbdf2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-global-settings"></a>Error en la generación de confirmación; se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración global
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Error en la generación de confirmación; se ha alcanzado el límite máximo del número aceptable de control de grupo de transacciones de Edifact para la configuración de invitado. Para restablecer el contador, vaya a la pantalla de función de remitente de configuración global, al campo UNH 1 del administrador de acuerdos de socios comerciales.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio EDIFACT porque el número de control que especificó en el número de referencia del conjunto de transacciones (UNH1) de la confirmación es mayor que el valor máximo permitido para UNH1. En esta instancia, BizTalk Server usó las propiedades globales de EDI para crear la confirmación.  
  
 El valor máximo del número de referencia del conjunto de transacciones depende del número de dígitos usado para el número de referencia. El número máximo de caracteres es 14 para el número de referencia, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de referencia del conjunto de transacciones (UNH1) en la página Definición de segmentos UNG y UNH en un valor inferior al límite máximo. Configure esta propiedad en el cuadro de diálogo Propiedades globales de EDI de la consola de administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].