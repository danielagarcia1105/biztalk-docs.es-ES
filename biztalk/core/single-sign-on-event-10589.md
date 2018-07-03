---
title: 'De sesión único: Evento 10589 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1f8dd6c8a6045f9e4e1678aa06faec8bb783c1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986189"
---
# <a name="single-sign-on-event-10589"></a>De sesión único: Evento 10589
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                     Inicio de sesión único (SSO) empresarial                                                                                                                     |
| Versión del producto |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    Identificador del evento     |                                                                                                                               10589                                                                                                                               |
|  Origen del evento   |                                                                                                                              ENTSSO                                                                                                                               |
|    Componente    |                                                                                                                                N/D                                                                                                                                |
|  Nombre simbólico  |                                                                                                                 SSO_ERROR_BACKUP_SECRET_REQUIRED                                                                                                                  |
|  Texto del mensaje   | No se ha realizado la copia de seguridad del secreto principal. Si pierde el secreto principal, toda la información almacenada en el sistema SSO se perderá de forma permanente y es posible que los sistemas no funcionen correctamente. Use las herramientas administrativas de SSO para realizar la copia de seguridad del secreto principal. |
  
## <a name="explanation"></a>Explicación  
 No se ha realizado la copia de seguridad del secreto principal. Si pierde el secreto principal, toda la información almacenada en el sistema SSO se perderá de forma permanente y es posible que los sistemas no funcionen correctamente.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener información sobre copias de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).