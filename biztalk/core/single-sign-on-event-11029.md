---
title: 'De sesión único: Evento 11029 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2825c8a3563ca9912f176bc3dc45c5350750fbd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992509"
---
# <a name="single-sign-on-event-11029"></a>De sesión único: Evento 11029
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                              Inicio de sesión único (SSO) empresarial                                               |
| Versión del producto |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                              |
|    Identificador del evento     |                                                        11029                                                         |
|  Origen del evento   |                                                        ENTSSO                                                        |
|    Componente    |                                                         N/D                                                          |
|  Nombre simbólico  |                                               SSO_INFO_CASE_SENSITIVE                                                |
|  Texto del mensaje   | La base de datos de SSO distingue mayúsculas de minúsculas. El servidor de SSO se ejecutará en modo de distinción entre mayúsculas y minúsculas. Consulte la documentación de details.%r |
  
## <a name="explanation"></a>Explicación  
 De forma predeterminada, el servidor de SSO no distingue mayúsculas de minúsculas. No obstante, la base de datos de SSO de SQL Server se configuró para que distinga mayúsculas de minúsculas, de manera que el servidor de SSO también se ejecutará en este modo.  
  
## <a name="user-action"></a>Acción del usuario  
 Tenga presente esto al especificar nombres de aplicación y de cuentas externas dado que ahora distinguen mayúsculas de minúsculas. Para obtener más información, consulte [servidor SSO](../core/sso-server.md).