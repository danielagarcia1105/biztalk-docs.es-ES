---
title: 'De sesión único: Evento 11008 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3a77dcfb89a3040cf6c1acb71a053d57393591
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983733"
---
# <a name="single-sign-on-event-11008"></a>De sesión único: Evento 11008
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                 Inicio de sesión único (SSO) empresarial                                                                 |
| Versión del producto |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    Identificador del evento     |                                                                           11008                                                                           |
|  Origen del evento   |                                                                          ENTSSO                                                                           |
|    Componente    |                                                                            N/D                                                                            |
|  Nombre simbólico  |                                                                   SSO_WARN_CHECK_GROUP                                                                    |
|  Texto del mensaje   | Error al comprobar pertenencia a grupos.%r<br /><br /> Nombre del grupo: %1 %r<br /><br /> Nombre de cuenta: %2 %r<br /><br /> Datos adicionales: %3 %r<br /><br /> Código de error: %4 |
  
## <a name="explanation"></a>Explicación  
 Las causas más probables del error son problemas de red, uso entre dominios o nivel combinado de controladores de dominio (por ejemplo, si el sistema usa controladores de dominio de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).  
  
## <a name="user-action"></a>Acción del usuario  
 Consulte al administrador de red para saber si existen problemas de red o si el sistema tiene uso entre dominios o nivel combinado de controladores de dominio.