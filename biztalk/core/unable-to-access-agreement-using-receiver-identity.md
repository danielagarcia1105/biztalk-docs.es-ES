---
title: No se puede obtener acceso al Acuerdo mediante la identidad del receptor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41b126ca0ebb96716f21381d2e1681ea59bd414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a>No se puede obtener acceso al acuerdo mediante la identidad del receptor
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|UnableToLocateAS2PartyByPartyNameError|  
|Texto del mensaje|No se puede obtener acceso al Acuerdo mediante la identidad del receptor: {0}|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que la canalización de envío no pudo determinar la entidad para un mensaje AS2 saliente porque no pudo hacer coincidir la propiedad de contexto AS2To del mensaje saliente o la propiedad AS2To de la propiedad de contexto Http.UserHttpheaders con el nombre de la entidad en la propiedad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, configure la propiedad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 en el nombre de entidad adecuado asociado con el mensaje AS2 que tiene un error.