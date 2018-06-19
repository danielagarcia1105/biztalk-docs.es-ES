---
title: Ha alcanzado el límite máximo del número aceptable de control de intercambio de Edifact para la entidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c00c357-4c7b-42ea-a031-15bad0195a75
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fdb92781d137f57a09ce8c45693c2928646af24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241324"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-party"></a>Se ha alcanzado el límite máximo permitido del número de control de intercambio Edifact para la entidad
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|PartyEdifactUnbNumberError|  
|Texto del mensaje|Se ha alcanzado el límite máximo permitido del número de control de intercambio Edifact para la entidad {0}. Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo UNB 5, del administrador de acuerdos de socios comerciales.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control de intercambio en el campo UNB5 especificado en la configuración de la entidad, específicamente el número de referencia en el campo UNB5.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control de intercambio depende de los valores de los tres campos en UNB5. El número máximo de caracteres es 14 para el número de referencia en el campo UNB5.2, 13 para el prefijo en UNB5.1, 13 para el sufijo en UNB5.3 y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNB5.2) del número de control de intercambio, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmento UNB para la entidad como receptora del intercambio.  
  
2.  Haga clic en el campo Editar asociado con el campo UNB5.  
  
3.  Defina el campo del centro del número de control de intercambio (el número de referencia en UNB5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.