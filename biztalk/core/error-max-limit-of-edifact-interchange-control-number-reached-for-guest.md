---
title: Ha alcanzado el límite máximo del número aceptable de control de intercambio de Edifact para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5d2dcc0-61fd-47c9-9339-8a85319c5398
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5063f4c62bdc32c84209d8b556b4778be4b6fd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980493"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-guest-settings"></a>Se ha alcanzado el límite máximo permitido para el número de control de intercambio Edifact en la configuración de Invitado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
| Versión del producto |                                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                           |
|    Identificador del evento     |                                                                                                       -                                                                                                       |
|  Origen del evento   |                                                            EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
|    Componente    |                                                                                                  Motor EDI                                                                                                   |
|  Nombre simbólico  |                                                                                          GlobalEdifactUnbNumberError                                                                                          |
|  Texto del mensaje   | Se ha alcanzado el límite máximo permitido para el número de control de intercambio Edifact en la configuración de Invitado. Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo UNB, del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control de intercambio en el campo ISA13 especificado en la configuración global, específicamente el número de referencia en el campo UNB5.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control de intercambio depende de los valores de los tres campos en UNB5. El número máximo de caracteres es 14 para el número de referencia en el campo UNB5.2, 13 para el prefijo en UNB5.1, 13 para el sufijo en UNB5.3 y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNB5.2) del número de control de intercambio, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmento UNB.  
  
2.  Haga clic en el campo Editar asociado con el campo UNB5.  
  
3.  Defina el campo del centro del número de control de intercambio (el número de referencia en UNB5.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.