---
title: 'Inicio de sesión único: Evento 10565 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d279491-dc0d-44c4-a77e-a67498a3481d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9567421210689d8615cf88e7fbd6493ef5749d02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271036"
---
# <a name="single-sign-on-event-10565"></a>Inicio de sesión único: Evento 10565
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10565|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_SECRET_VALIDATE_FAILED|  
|Texto del mensaje|No se pudo cargar el secreto desde el Registro. Es posible que se haya cambiado la cuenta de servicio para el servicio SSO o que el secreto esté dañado. Restaure el secreto desde el archivo de copia de seguridad.%r<br /><br /> MSID: %1|  
  
## <a name="explanation"></a>Explicación  
 Es probable que un administrador del sistema haya cambiado la cuenta del servicio SSO, lo que imposibilita el descifrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Busque a la persona que cambió la cuenta del servicio SSO y, después, restaure el secreto desde el archivo de copia de seguridad. Para obtener más información acerca de cómo restaurar el secreto, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).