---
title: 'De sesión único: Evento 10590 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2ac48ecf1279c1a8347e8f1ab3bcd1367854ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006775"
---
# <a name="single-sign-on-event-10590"></a>De sesión único: Evento 10590
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10590                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |                  SSO_ERROR_OUT_OF_SERVICE                  |
|  Texto del mensaje   |        Inicio de sesión único empresarial se está desconectando.         |
  
## <a name="explanation"></a>Explicación  
 Por lo general, el sistema ENTSSO comprueba si existen actualizaciones en la base de datos de ENTSSO cada 30 segundos. Si la base de datos no está disponible durante un período especificado (normalmente cinco minutos), el sistema se desconecta solo. Si se encuentra en este estado, el sistema no responde a solicitudes de credenciales. No obstante, es posible llevar a cabo algunas actividades administrativas y sin conexión.  
  
## <a name="user-action"></a>Acción del usuario  
 Este error indica que la base de datos de ENTSSO está desconectada. Investigue la causa de inmediato.