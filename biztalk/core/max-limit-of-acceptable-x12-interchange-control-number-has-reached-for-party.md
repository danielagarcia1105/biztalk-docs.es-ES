---
title: El límite máximo aceptable X12 ha alcanzado el número de control de intercambio para la entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc49089-3c7b-4ce2-9fbc-68e582c3a822
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de22f059a720fdec999f495f38a6b21009469158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986309"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-party"></a>Se ha alcanzado el límite máximo permitido del número de control de intercambio X12 para la entidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| Versión del producto |                                                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    Identificador del evento     |                                                                                             -                                                                                             |
|  Origen del evento   |                                                  EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
|    Componente    |                                                                                        Motor EDI                                                                                         |
|  Nombre simbólico  |                                                                                  PartyX12IsaNumberError                                                                                   |
|  Texto del mensaje   | El límite máximo aceptable X12 ha alcanzado el número de control de intercambio para la entidad {0}. Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo ISA 13, del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de intercambio del campo ISA13 especificado en la configuración de la entidad era mayor que el valor máximo permitido. El número máximo de caracteres es nueve para el número de control de intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el número de control de intercambio tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmento ISA para la entidad como receptora del intercambio.  
  
2.  Haga clic en el campo Editar asociado con el campo ISA13.  
  
3.  Defina el número de control de intercambio en un valor nuevo, de modo que el campo tenga un número de dígitos aceptable.