---
title: Ha alcanzado el límite máximo del número aceptable de control de grupo funcional de Edifact para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ea1bd6-8c39-4d11-81a5-75d4a861e041
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 533f1067effa99f4152c908c70adf16eeb067c7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010453"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-guest-settings"></a>Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional Edifact en la configuración de Invitado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| Versión del producto |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    Identificador del evento     |                                                                                                         -                                                                                                          |
|  Origen del evento   |                                                               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
|    Componente    |                                                                                                     Motor EDI                                                                                                     |
|  Nombre simbólico  |                                                                                            GlobalEdifactUngNumberError                                                                                             |
|  Texto del mensaje   | Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional Edifact en la configuración de Invitado. Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo UNB 5, del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control de grupo del campo UNG5 especificado en la configuración global, específicamente el número de referencia en el campo UNG5.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control de grupo depende de los valores de los tres campos en UNG5. El número máximo de caracteres es 14 para el número de referencia en el campo UNG5.2, 13 para el prefijo en UNG5.1, 13 para el sufijo en UNG5.3 y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNG5.2) del número de control de grupo, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmentos UNG y UNH.  
  
2.  Haga clic en el campo Editar asociado con el campo UNG5.  
  
3.  Defina el campo del centro del número de control de grupo (el número de referencia en UNG5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.