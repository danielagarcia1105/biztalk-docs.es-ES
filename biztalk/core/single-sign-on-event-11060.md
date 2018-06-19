---
title: 'Inicio de sesión único: Evento 11060 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1423b7385e6c0b8f78fb815ec48b749556cd291f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276788"
---
# <a name="single-sign-on-event-11060"></a>Inicio de sesión único: Evento 11060
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11060|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_PS_MIIS_ACCESS_DENIED|  
|Texto del mensaje|Los cambios de contraseña de Windows de MIIS sólo se aceptarán desde una cuenta de servicio SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> El usuario cliente: %2 %r<br /><br /> Cuenta de servicio SSO: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 El servidor de ENTSSO recibió un cambio de contraseña de Microsoft Identity Integration Server (MIIS). No obstante, el servidor de ENTSSO sólo aceptará cambios de contraseña de MIIS si el usuario del cliente (usuario que llama) es la misma cuenta que la cuenta de servicio SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la configuración del usuario que llama para sincronización de contraseñas de MIIS. Para obtener más información, consulte [cómo configurar ENTSSO para la sincronización de contraseña de MIIS](../core/how-to-configure-entsso-for-miis-password-sync.md).