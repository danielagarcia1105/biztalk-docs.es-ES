---
title: 'Inicio de sesión único: Evento 10765 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0fbc04f4c8fc98a87de87a4cd48529a3ca7e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278420"
---
# <a name="single-sign-on-event-10765"></a>Inicio de sesión único: Evento 10765
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10765|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_NO_CREDENTIALS|  
|Texto del mensaje|No se establecieron credenciales para la asignación.|  
  
## <a name="explanation"></a>Explicación  
 Se solicitó GetCredentials en una asignación, pero la asignación especificada no tiene credenciales.  
  
## <a name="user-action"></a>Acción del usuario  
 Use la línea de comandos o el complemento MMC para establecer las credenciales de la asignación.