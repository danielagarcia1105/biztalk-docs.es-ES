---
title: "No se puede crear el enlace de metadatos estándar para el esquema | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3228da0dfee18581c5fa8105ce3dd480380cc034
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a>No se puede crear el enlace de metadatos estándar para el esquema
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede crear el enlace de metadatos estándar para el esquema "{0}". Los esquemas admitidos son http, https, net.pipe y net.tcp|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio del que se intenta consumir los metadatos no es un esquema admitido.  
  
## <a name="user-action"></a>Acción del usuario  
 Publique los metadatos con un esquema válido y ejecute de nuevo el asistente, en la nueva ubicación de metadatos.  
  
 Para obtener más información sobre adaptadores y enlaces, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Adaptadores de WCF](../core/wcf-adapters.md)