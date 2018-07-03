---
title: El límite máximo aceptable Edifact que se ha alcanzado el número de control de conjunto de transacciones para entidades | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a64cc5d3-a845-4044-9c6e-879ecda15fce
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85fd53beb1484d1e9ffbddf1bbc4f4ac69ae1e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004541"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-party"></a>Se ha alcanzado el límite máximo permitido del número de control de conjunto de transacciones Edifact para la entidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| Versión del producto |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    Identificador del evento     |                                                                                                -                                                                                                 |
|  Origen del evento   |                                                      EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
|    Componente    |                                                                                            Motor EDI                                                                                            |
|  Nombre simbólico  |                                                                                   GlobalEdifactUnhNumberError                                                                                    |
|  Texto del mensaje   | El límite máximo aceptable Edifact que se ha alcanzado el número de control de conjunto de transacciones para entidades {0}. Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo UNH 1, del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio saliente porque el número de control del conjunto de transacciones en el campo UNH1 especificado en la configuración de la entidad, específicamente el número de referencia en el campo UNH1.2, era mayor que el valor máximo permitido. El valor máximo permitido para el número de control del conjunto de transacciones depende de los valores de los tres campos en UNH1. El número máximo de caracteres es 14 para el número de referencia en el campo UNH1.2, 13 para el prefijo en UNH1.1, 13 para el sufijo en UNH1.3 y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de control del conjunto de transacciones, tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmentos UNG y UNH.  
  
2.  Haga clic en el campo Editar asociado con el campo UNH1.  
  
3.  Defina el campo del centro del número de control del conjunto de transacciones (el número de referencia en UNH1.2) en un valor nuevo de modo que el campo tenga un número de dígitos aceptable.