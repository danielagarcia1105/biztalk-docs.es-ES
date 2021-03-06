---
title: El límite máximo aceptable Edifact que se ha alcanzado el número de control de conjunto de transacciones para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de9240d2fd5ea701f701e34698b645b272b904b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978965"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a>Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones Edifact en la configuración de Invitado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| Versión del producto |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    Identificador del evento     |                                                                                                         -                                                                                                          |
|  Origen del evento   |                                                               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
|    Componente    |                                                                                                     Motor EDI                                                                                                     |
|  Nombre simbólico  |                                                                                            GlobalEdifactUnhNumberError                                                                                             |
|  Texto del mensaje   | Se ha alcanzado el límite máximo permitido para el número de control de conjunto de transacciones Edifact en la configuración de Invitado. Para restablecer el contador, vaya a la pantalla de función de destinatario de configuración global, al campo UNH 1 del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control del conjunto de transacciones en el campo UNH1 especificado en la configuración global, específicamente el número de referencia en el campo UNH1.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control de grupo depende de los valores de los tres campos en UNH1. El número máximo de caracteres es 14 para el número de referencia en el campo UNH1.2, 13 para el prefijo en UNH1.1, 13 para el sufijo en UNH1.3 y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de control del conjunto de transacciones, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmento UNH.  
  
2.  Haga clic en el campo Editar asociado con el campo UNH1.  
  
3.  Defina el campo del centro del número de control de grupo (el número de referencia en UNH1.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.