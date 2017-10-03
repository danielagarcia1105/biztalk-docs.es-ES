---
title: "Resolución de acuerdo basada en las propiedades de contexto de protocolo no ha podido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d74ad7aa4a73f4a0befcef32bc8051195cb080
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# Error en la resolución de acuerdo basada en las propiedades de contexto para el protocolo
## Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|AgreementResolutionContextPropertiesLookupFailed|  
|Texto del mensaje|Resolución del acuerdo se basa en las propiedades de contexto para {0} protocolo ha fallado.|  
  
## Explicación  
 Este evento de error,  indica que BizTalk Server no se pudo resolver en un acuerdo según las propiedades de contexto que proporciona el cliente.  
  
## Acción del usuario  
 Para resolver este error, proporcione las propiedades de contexto como parte del mensaje de BizTalk, de modo que la resolución del acuerdo pueda tener lugar.