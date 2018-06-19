---
title: 'Inicio de sesión único: Evento 11029 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f24cee6fcbe7db5ce0b4f31d458a5a29118c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277196"
---
# <a name="single-sign-on-event-11029"></a>Inicio de sesión único: Evento 11029
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11029|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_INFO_CASE_SENSITIVE|  
|Texto del mensaje|La base de datos de SSO distingue mayúsculas de minúsculas. El servidor de SSO se ejecutará en modo de distinción entre mayúsculas y minúsculas. Consulte la documentación de details.%r|  
  
## <a name="explanation"></a>Explicación  
 De forma predeterminada, el servidor de SSO no distingue mayúsculas de minúsculas. No obstante, la base de datos de SSO de SQL Server se configuró para que distinga mayúsculas de minúsculas, de manera que el servidor de SSO también se ejecutará en este modo.  
  
## <a name="user-action"></a>Acción del usuario  
 Tenga presente esto al especificar nombres de aplicación y de cuentas externas dado que ahora distinguen mayúsculas de minúsculas. Para obtener más información, consulte [servidor de SSO](../core/sso-server.md).