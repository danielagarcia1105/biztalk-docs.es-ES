---
title: "Ha alcanzado el límite máximo del número de control de grupo funcional Edifact aceptable para la entidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fde516b-59f1-49a1-8456-127469df0e02
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4a47e0866c78e692f8c992afbd6b24cde95632
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-party"></a>Se ha alcanzado el límite máximo permitido del número de control de grupo funcional Edifact para la entidad
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|PartyEdifactUngNumberError|  
|Texto del mensaje|Se ha alcanzado el límite máximo permitido del número de control de grupo funcional Edifact para la entidad {0}. Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo UNG 5, del administrador de acuerdos de socios comerciales.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio EDIFACT saliente porque el número de control de grupo del campo UNG5 especificado en la configuración de la entidad, específicamente el número de referencia en el campo UNG5.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control de grupo depende de los valores de los tres campos en UNG5. El número máximo de caracteres es 14 para el número de referencia en el campo UNG5.2, 13 para el prefijo en UNG5.1, 13 para el sufijo en UNG5.3 y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNG5.2) del número de control de grupo, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades de EDI de la entidad resuelta para el intercambio, abra la página Definición de segmentos UNG y UNH para la entidad como receptor de intercambio.  
  
2.  Haga clic en el campo Editar asociado con el campo UNG5.  
  
3.  Defina el campo del centro del número de control de grupo (el número de referencia en UNG5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.