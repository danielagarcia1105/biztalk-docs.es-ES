---
title: "Inicio de sesión único: Evento 10762 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 487fbeb0f077950605432861a9118eacd93f2c89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10762"></a>Inicio de sesión único: Evento 10762
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10762|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_WRONG_THREAD|  
|Texto del mensaje|Se llamó al componente de cliente de SSO en el subproceso incorrecto. Actualmente, se encuentra bloqueado en un subproceso porque tiene una transacción.|  
  
## <a name="explanation"></a>Explicación  
 Los componentes sólo pueden ser multiproceso cuando no tienen una transacción. Este componente tiene una transacción y, por lo tanto, está bloqueado en un subproceso.  
  
## <a name="user-action"></a>Acción del usuario  
 Configure la aplicación para que no llame a componentes de cliente de SSO en varios subprocesos cuando usa transacciones.