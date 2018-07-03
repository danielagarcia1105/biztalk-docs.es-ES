---
title: 'De sesión único: Evento 10575 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93ae664da9f4f9a36c82cdec2dea0edeeac6bdeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968565"
---
# <a name="single-sign-on-event-10575"></a>De sesión único: Evento 10575
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                     Inicio de sesión único (SSO) empresarial                                                                                     |
| Versión del producto |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    Identificador del evento     |                                                                                               10575                                                                                               |
|  Origen del evento   |                                                                                              ENTSSO                                                                                               |
|    Componente    |                                                                                                N/D                                                                                                |
|  Nombre simbólico  |                                                                                  SSO_INFO_CHANGED_SECRET_SERVER                                                                                   |
|  Texto del mensaje   | Se actualizó el nombre de servidor secreto.%r<br /><br /> Nuevo servidor secreto: %1 %r<br /><br /> Servidor secreto anterior: %2 %r<br /><br /> Id. de seguimiento: %3 %r<br /><br /> Equipo cliente: %4 %r<br /><br /> Usuario cliente: %5 |
  
## <a name="explanation"></a>Explicación  
 Este mensaje de información puede resultar útil para el seguimiento de eventos importantes relacionados con la seguridad que pueden producirse en el sistema SSO. Este mensaje indica que se ha actualizado el nombre del servidor secreto.  
  
## <a name="user-action"></a>Acción del usuario  
 No se requiere ninguna acción del usuario.