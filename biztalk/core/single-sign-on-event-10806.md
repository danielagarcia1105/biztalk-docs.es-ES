---
title: 'Inicio de sesión único: Evento 10806 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd3f432a408cffcbd1ccd27508550fd0888c5213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277180"
---
# <a name="single-sign-on-event-10806"></a>Inicio de sesión único: Evento 10806
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10806|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_APP_ASSIGNED_TO_ADAPTER|  
|Texto del mensaje|No se puede eliminar la aplicación porque actualmente está asignada a un adaptador.|  
  
## <a name="explanation"></a>Explicación  
 No se puede eliminar una aplicación si está asignada a un adaptador.  
  
## <a name="user-action"></a>Acción del usuario  
 Quite la asignación de la aplicación del adaptador y, a continuación, elimínela.