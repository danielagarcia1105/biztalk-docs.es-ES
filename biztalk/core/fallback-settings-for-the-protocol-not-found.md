---
title: Configuración de reserva para el protocolo no se encontró | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b3f8ea35f4f29859f5156ff254137ea7a8f8db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245908"
---
# <a name="fallback-settings-for-the-protocol-not-found"></a>No se encuentra la configuración de reserva para el protocolo
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|AgreementResolutionFallbackSettingsNotFound|  
|Texto del mensaje|No se encuentra la configuración de reserva para el protocolo {0}.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta no se encontraba allí para el protocolo en particular.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, configure la configuración de reserva para el protocolo en particular.