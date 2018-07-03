---
title: 'De sesión único: Evento 11060 | Microsoft Docs'
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
ms.openlocfilehash: 74fd521f2b2dab27a3a408e8459d5bb4113252d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022738"
---
# <a name="single-sign-on-event-11060"></a>De sesión único: Evento 11060
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                               Inicio de sesión único (SSO) empresarial                                                                                               |
| Versión del producto |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    Identificador del evento     |                                                                                                         11060                                                                                                         |
|  Origen del evento   |                                                                                                        ENTSSO                                                                                                         |
|    Componente    |                                                                                                          N/D                                                                                                          |
|  Nombre simbólico  |                                                                                            SSO_WARN_PS_MIIS_ACCESS_DENIED                                                                                             |
|  Texto del mensaje   | Los cambios de contraseña de Windows de MIIS sólo se aceptarán desde una cuenta de servicio SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario cliente: %2 %r<br /><br /> Cuenta de servicio SSO: %3 %r<br /><br /> Código de error: %4 |
  
## <a name="explanation"></a>Explicación  
 El servidor de ENTSSO recibió un cambio de contraseña de Microsoft Identity Integration Server (MIIS). No obstante, el servidor de ENTSSO sólo aceptará cambios de contraseña de MIIS si el usuario del cliente (usuario que llama) es la misma cuenta que la cuenta de servicio SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la configuración del usuario que llama para sincronización de contraseñas de MIIS. Para obtener más información, consulte [cómo configurar ENTSSO para la sincronización de contraseñas de MIIS](../core/how-to-configure-entsso-for-miis-password-sync.md).