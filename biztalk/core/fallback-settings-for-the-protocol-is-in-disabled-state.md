---
title: "Configuración de reserva para el protocolo está en estado deshabilitado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9060dbe2bf3644310d862d4949d2cf944269105d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a>La configuración de reserva para el protocolo tiene el estado Deshabilitado
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|AgreementResolutionFallbackSettingsDisabled|  
|Texto del mensaje|La configuración de reserva para el protocolo {0} tiene el estado Deshabilitado.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta estaba en el estado deshabilitado para el protocolo en particular.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, habilite a la configuración de reserva para el protocolo en particular.