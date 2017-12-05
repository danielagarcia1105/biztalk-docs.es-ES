---
title: "Generación de confirmación de error error el límite máximo de X12 transacciones terceros | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c78a7cef-24ae-4d09-9043-2f53c301302d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e845960a85ebe2ebf90b8549634a0097676c80c5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-party"></a>Generación de confirmación de error error el límite máximo de X12 parte de la transacción
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de BizTalk Server|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Error en la generación de confirmación; se ha alcanzado el límite máximo del número aceptable de control de grupo de transacciones de X12 para la entidad {0}. Para restablecer el contador, vaya a Entidad, en la pantalla de función de remitente, en el campo ST 2 del administrador de acuerdos de socios comerciales.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio X12 porque el número de control que especificó en el número de control del conjunto de transacciones (ST2) de la confirmación es mayor que el valor máximo permitido para ST2. En esta instancia, BizTalk Server usó las propiedades de entidad de EDI para crear la confirmación.  
  
 El valor máximo del número de control del conjunto de transacciones depende del número de dígitos usado para el número de control. La longitud máxima de los tres campos es 9; la longitud máxima de los campos prefijo y sufijo es 8.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de control (ST2.2) del número de referencia del conjunto de transacciones (ST2) en la página Definición de segmentos GS y ST en un valor inferior al límite máximo. Configure esta propiedad en el cuadro de diálogo Propiedades globales de EDI de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].