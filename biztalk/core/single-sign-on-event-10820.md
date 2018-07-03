---
title: 'De sesión único: Evento 10820 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b566c4dfe4437017b743228c9bae2631c79a00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011661"
---
# <a name="single-sign-on-event-10820"></a>De sesión único: Evento 10820
## <a name="details"></a>Detalles  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                  Inicio de sesión único (SSO) empresarial                                   |
| Versión del producto |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    Identificador del evento     |                                            10820                                             |
|  Origen del evento   |                                            ENTSSO                                            |
|    Componente    |                                             N/D                                              |
|  Nombre simbólico  |                                ENTSSO_E_REQUIRE_OLD_PASSWORD                                 |
|  Texto del mensaje   | Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior. |
  
## <a name="explanation"></a>Explicación  
 Esta aplicación está configurada para que el adaptador de sincronización de contraseñas deba proporcionar la contraseña anterior.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la configuración del adaptador de sincronización de contraseñas.