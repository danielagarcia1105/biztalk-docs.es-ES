---
title: 'De sesión único: Evento 10850 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0430d5d7ea3ff2a0fabf9c9698acffe15b644f24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011365"
---
# <a name="single-sign-on-event-10850"></a>De sesión único: Evento 10850
## <a name="details"></a>Detalles  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  Nombre del producto   |                      Inicio de sesión único (SSO) empresarial                      |
| Versión del producto |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    Identificador del evento     |                                10850                                |
|  Origen del evento   |                               ENTSSO                                |
|    Componente    |                                 N/D                                 |
|  Nombre simbólico  |                 ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE                 |
|  Texto del mensaje   | No se puede crear una aplicación con el marcador "habilitado" especificado. |
  
## <a name="explanation"></a>Explicación  
 Antes de habilitar una aplicación, se debe crear la aplicación y, a continuación, especificar la información de campo de cada uno de sus campos (por ejemplo, Id. de usuario y Contraseña). No es posible crear una aplicación con el campo "habilitado" ya establecido.  
  
## <a name="user-action"></a>Acción del usuario  
 Vuelva a crear la aplicación (mediante la API de creación de aplicaciones o el Asistente para creación de nueva aplicación afiliada). Una vez completada la aplicación y rellenados los campos, habilítela.