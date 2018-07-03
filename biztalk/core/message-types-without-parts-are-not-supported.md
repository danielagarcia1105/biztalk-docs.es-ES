---
title: Tipos de mensajes sin partes no se admiten | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60bb78e2bbf06ff80315bd9bbc2b33346ed18d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024170"
---
# <a name="message-types-without-parts-are-not-supported"></a>No se admiten los tipos de mensajes sin partes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| Versión del producto |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    Identificador del evento     |                                                             0                                                             |
|  Origen del evento   |                                                             0                                                             |
|    Componente    |                                                             0                                                             |
|  Nombre simbólico  |                                                             0                                                             |
|  Texto del mensaje   | No se admiten los tipos de mensajes sin partes. Corrija la descripción del servicio "{0}"tipo de mensaje"{1}" y vuelva a ejecutar el asistente. |
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio que se intenta consumir no tiene un tipo de mensaje definido.  
  
## <a name="user-action"></a>Acción del usuario  
 Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir). De lo contrario, póngase en contacto con el proveedor de servicio.  Para obtener más información sobre los mensajes, vea el siguiente recurso en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ayuda:  
  
-   [Construcción de mensajes web](../core/constructing-web-messages.md)