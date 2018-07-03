---
title: 'De sesión único: Evento 11070 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 799e175f6425b91c98f6e96ec9f0bd73d8d0ebdf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994325"
---
# <a name="single-sign-on-event-11070"></a>De sesión único: Evento 11070
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                               Inicio de sesión único (SSO) empresarial                                                                                               |
| Versión del producto |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    Identificador del evento     |                                                                                                         11070                                                                                                         |
|  Origen del evento   |                                                                                                        ENTSSO                                                                                                         |
|    Componente    |                                                                                                          N/D                                                                                                          |
|  Nombre simbólico  |                                                                                             SSO_WARN_PS_MIIS_NOT_ALLOWED                                                                                              |
|  Texto del mensaje   | Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde MIIS. Use 'ssoconfig -allowPS MIIS yes' o la MMC de administración de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario cliente: %2 |
  
## <a name="explanation"></a>Explicación  
 Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde MIIS.  
  
## <a name="user-action"></a>Acción del usuario  
 Para permitir que los cambios de contraseña de Windows desde MIIS, en el **servidores complemento**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde MIIS.**  
  
 Para obtener más información, consulte [cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).