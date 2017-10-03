---
title: "Inicio de sesión único: Evento 10848 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9511d46a43180626a31f36c9f887b0ac532e088a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10848"></a>Inicio de sesión único: Evento 10848
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10848|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS|  
|Texto del mensaje|No se permite la sincronización directa de contraseñas de la aplicación porque sus campos son ambiguos.|  
  
## <a name="explanation"></a>Explicación  
 Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.