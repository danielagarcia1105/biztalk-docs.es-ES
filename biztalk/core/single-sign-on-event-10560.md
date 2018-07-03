---
title: 'De sesión único: Evento 10560 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82f9245b4eda9b6bf567aae1de2071d3e77aae04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967757"
---
# <a name="single-sign-on-event-10560"></a>De sesión único: Evento 10560
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                  Inicio de sesión único (SSO) empresarial                                                                                  |
| Versión del producto |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    Identificador del evento     |                                                                                            10560                                                                                            |
|  Origen del evento   |                                                                                           ENTSSO                                                                                            |
|    Componente    |                                                                                             N/D                                                                                             |
|  Nombre simbólico  |                                                                               SSO_ERROR_BACKUP_SECRET_FAILED                                                                                |
|  Texto del mensaje   | No se pudo realizar la copia de seguridad del secreto principal.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> MSID actual: %2 %r<br /><br /> MSID anterior: %3 %r<br /><br /> Usuario cliente: %4 %r<br /><br /> Código de error: %5 |
  
## <a name="explanation"></a>Explicación  
 Error al intentar realizar una copia de seguridad del secreto principal. Es posible que los permisos, la ruta de acceso o el directorio del usuario que intenta realizar esta copia de seguridad tenga sean incorrectos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener información sobre copias de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).