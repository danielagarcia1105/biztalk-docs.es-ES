---
title: 'De sesión único: Evento 11025 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c25dc80669b4524c7e9ce848e4b0e28f773f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015901"
---
# <a name="single-sign-on-event-11025"></a>De sesión único: Evento 11025
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                 Inicio de sesión único (SSO) empresarial                                                                                                  |
| Versión del producto |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    Identificador del evento     |                                                                                                           11025                                                                                                            |
|  Origen del evento   |                                                                                                           ENTSSO                                                                                                           |
|    Componente    |                                                                                                            N/D                                                                                                             |
|  Nombre simbólico  |                                                                                            SSO_WARN_INVALID_APP_TICKET_TIMEOUT                                                                                             |
|  Texto del mensaje   | Valor de tiempo de espera de vale no válido para actualización de aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Tiempo de espera de vale: %2 minutos %r<br /><br /> Tiempo de espera máximo de vale: %3 minutos %r<br /><br /> Código de error: %4 |
  
## <a name="explanation"></a>Explicación  
 El valor de tiempo de espera de vale no es válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información sobre los tiempos de espera de vale, consulte [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).