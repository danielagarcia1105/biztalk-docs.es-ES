---
title: 'De sesión único: Evento 10808 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d4e6ab0f6a9ea10ef28440f5b8399778fbc93b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971405"
---
# <a name="single-sign-on-event-10808"></a>De sesión único: Evento 10808
## <a name="details"></a>Detalles  
  
|                 |                                                                  |
|-----------------|------------------------------------------------------------------|
|  Nombre del producto   |                    Inicio de sesión único (SSO) empresarial                     |
| Versión del producto |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    Identificador del evento     |                              10808                               |
|  Origen del evento   |                              ENTSSO                              |
|    Componente    |                               N/D                                |
|  Nombre simbólico  |                ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED                 |
|  Texto del mensaje   | El sistema SSO no está habilitado para Inicio de sesión único iniciado por host. |
  
## <a name="explanation"></a>Explicación  
 El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.  
  
## <a name="user-action"></a>Acción del usuario  
 Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host. Esto establecerá el marcador  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la información global.