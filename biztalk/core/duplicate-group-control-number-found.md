---
title: Número de control de grupo se encuentra duplicado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1badc033-42fd-4992-ad36-b53047ba7817
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66fd37bbfc5be81f7a7301f6313745a29ec180de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001437"
---
# <a name="duplicate-group-control-number-found"></a>Se ha encontrado un número de control de grupo duplicado
## <a name="details"></a>Detalles  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                          Se ha encontrado un número de control de grupo duplicado                          |

## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar un intercambio entrante porque tenía el mismo número de control de intercambio, grupo o conjunto de transacciones que un intercambio recibido previamente. Esto provocará un error siempre que estén habilitadas las correspondientes comprobaciones de números de control duplicados.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  

- Asegúrese de que el intercambio enviado a BizTalk Server no tiene el mismo número de control de grupo que un intercambio previo, si está habilitada la correspondiente comprobación de número de control duplicado.  

- Deshabilite la comprobación de número de control duplicado. En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la entidad correspondiente y abra el cuadro de diálogo Propiedades de procesamiento de intercambio EDIFACT o bien Propiedades de procesamiento de intercambio X12 para la entidad como remitente del intercambio. Para deshabilitar una comprobación para un intercambio EDIFACT, desactive la propiedad Comprobar si hay duplicado de Número de control de grupo (UNG5) en el intercambio. Para deshabilitar una comprobación para un intercambio X12, desactive la propiedad Comprobar si hay duplicado de Número de control de grupo (GS6) en el intercambio.
