---
title: Generación de confirmación; error de configuración de la entidad se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcbb6374-0403-42b0-892b-b35157a2c74a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b639f80d6ad203074e0542df6672f2d7b89aa2ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001349"
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-party-settings"></a>Error en la generación de confirmación; se ha alcanzado el límite máximo del número de control de conjunto de transacciones de Edifact para la configuración de la entidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                            |
| Versión del producto |                                                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                        |
|    Identificador del evento     |                                                                                                                    -                                                                                                                     |
|  Origen del evento   |                                                                                                            EDI de BizTalk Server                                                                                                            |
|    Componente    |                                                                                                                Motor EDI                                                                                                                |
|  Nombre simbólico  |                                                                                                                    -                                                                                                                     |
|  Texto del mensaje   | Generación de confirmación; error como el límite máximo de Edifact aceptable ha alcanzado el número de control de conjunto de transacciones para entidades {0}. Para restablecer el contador, vaya a Entidad, en la pantalla de función del remitente, en el campo UNH 1 del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio EDIFACT porque el número de control que especificó en el número de referencia del conjunto de transacciones (UNH1) de la confirmación es mayor que el valor máximo permitido para UNH1. En esta instancia, BizTalk Server usó las propiedades de entidad de EDI para crear la confirmación.  
  
 El valor máximo del número de referencia del conjunto de transacciones depende del número de dígitos usado para el número de referencia. El número máximo de caracteres es 14 para el número de referencia, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el campo de número de referencia (UNH1.2) del número de referencia del conjunto de transacciones (UNH1) en la página Definición de segmentos UNG y UNH en un valor inferior al límite máximo. Establezca esta propiedad en el cuadro de diálogo Propiedades de EDI en la consola de administración de BizTalk Server.