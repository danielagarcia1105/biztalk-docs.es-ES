---
title: Falta un elemento de parte de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412b25d2f7ea027de53818b032b50562faab9865
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009445"
---
# <a name="message-part-missing-element"></a>Falta un elemento de parte de mensaje
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| Versión del producto |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    Identificador del evento     |                                                         0                                                          |
|  Origen del evento   |                                                         0                                                          |
|    Componente    |                                                         0                                                          |
|  Nombre simbólico  |                                                         0                                                          |
|  Texto del mensaje   | Falta un elemento de parte de mensaje. Corrija la descripción del servicio "{0}"tipo de mensaje"{1}"elemento"{2}" y vuelva a ejecutar el Asistente |
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio que se intenta consumir no tiene la etiqueta de elemento que identifica el tipo de mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir). En caso contrario, póngase en contacto con el proveedor de servicios.  
  
 Para obtener más información sobre mensajes, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Construcción de mensajes web](../core/constructing-web-messages.md)