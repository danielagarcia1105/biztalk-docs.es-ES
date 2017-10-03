---
title: "El límite máximo de aceptable X12 ha alcanzado el número de control de conjunto de transacciones para la configuración de invitado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5a4aa5c-13a7-4234-916e-562b52644c51
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16ab48c7bc5615a17c4927d7bf971bdec87a9c2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-guest-settings"></a>Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones X12 en la configuración de Invitado
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|GlobalX12TsNumberError|  
|Texto del mensaje|Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones X12 en la configuración de Invitado. Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo ST 2, del administrador de acuerdos de socios comerciales.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control del conjunto de transacciones en el campo ST02 especificado en la configuración global, específicamente el número de referencia en el campo ST02.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control del conjunto de transacciones depende de los valores de los tres campos en ST02. El número máximo de caracteres es 9 para el número de referencia en el campo UNH1.2, 8 para el prefijo en UNH1.1 y 8 para el sufijo en UNH1.3 y 9 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (ST02.2) del número de control del conjunto de transacciones, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmentos GS y ST.  
  
2.  Haga clic en el campo Editar asociado con el campo ST02.  
  
3.  Defina el campo del centro del número de control de grupo (el número de referencia en ST02.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.