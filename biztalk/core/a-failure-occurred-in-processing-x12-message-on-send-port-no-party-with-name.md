---
title: 'Se ha producido un error en el procesamiento de X12 mensaje en el puerto de envío: no existe ninguna entidad con nombre | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 817840dae0db408d4f78732f5d470605a05edf71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014797"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a>Se ha producido un error en el procesamiento de X12 mensaje en el puerto de envío: no existe ninguna entidad con nombre
## <a name="details"></a>Detalles  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  Nombre del producto   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| Versión del producto |                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    Identificador del evento     |                                               -                                               |
|  Origen del evento   |    EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
|    Componente    |                                          Motor EDI                                           |
|  Nombre simbólico  |                                               -                                               |
|  Texto del mensaje   | Se ha producido un error en el procesamiento de X12 mensaje en el puerto de envío {0}. No existe ninguna entidad con el nombre {1}. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio X12 porque BizTalk Server no pudo hacer coincidir el puerto de envío que se suscribió al intercambio con el puerto de envío asociado con una entidad. Esto se produce si no se promociona la propiedad DestinationPartyName ni las propiedades de calificador e identificador de remitente ni de calificador e identificador del receptor), por lo que no estarán disponibles para la resolución de la entidad del envío.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el puerto de envío que se ha suscrito al intercambio coincide con el puerto de envío asociado con una entidad.